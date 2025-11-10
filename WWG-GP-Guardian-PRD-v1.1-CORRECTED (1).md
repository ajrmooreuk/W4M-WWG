# Product Requirements Document
## WWG GP Guardian: AI-Powered Margin Protection System

**VERSION:** 1.1 (CORRECTED)  
**DATE:** 2025-11-09  
**STATUS:** Ready for Implementation  

---

## 🚨 CRITICAL CORRECTIONS IN v1.1

### CORRECTION #1: Frontend Platform
- ❌ **INCORRECT (v1.0):** References to "Make.com" workflow automation
- ✅ **CORRECT (v1.1):** **Figma's Make** - Claude-powered design-to-code platform
  - Figma Make = Figma UI/UX Design + Claude AI + System Integration
  - Native Figma design system integration
  - Automated design-to-React code conversion
  - Built-in Supabase connection capabilities

### CORRECTION #2: Storage Cost Baseline
- ✅ **£450,000 annual storage cost** validated as baseline
- ✅ **Phased Allocation Approach:**
  - **MVP (30 days):** Order-level allocation (proportional by value)
  - **Phase 1 (60 days):** Customer + Supplier route allocation
  - **Phase 2 (90 days):** Product category + SKU-level tracking

---

## 1. Executive Summary

### The Problem
WWGiles operates at **10.5% gross margin** (bottom quartile) vs **15-20% industry average**. The core issue:

**Sales teams are compensated on "booked GP" (expected profit) but the company realizes significantly lower "actual GP" due to post-sale cost erosion.**

**The £450K Storage Cost Leak:**
- Sales assumes: **4-day storage** from vessel arrival to customer pickup
- Reality: **12-day average storage** (vessel delays + customer pickup timing)
- Result: **£450,000 annual storage cost** not captured in sales GP calculations
- Impact: Sales believes they're hitting margins while company hemorrhages profit

### The Solution
**GP Guardian** tracks three stages of GP realization:
1. **Booked GP:** What sales calculated (4-day assumption)
2. **Current GP:** Real-time adjustment based on actual vessel ETA and customer schedule
3. **Realized GP:** Final actual profit after delivery

**Enables proactive intervention** through:
- Risk-adjusted quotations (add buffer for unreliable routes)
- Early warning alerts when GP erosion detected
- Recommended actions to protect margins
- Sales compensation aligned with realized (not just booked) GP

### Success Metrics

| Metric | Current | 90-Day Target |
|--------|---------|---------------|
| Average Storage Days | 12 days | 4-6 days |
| Annual Storage Cost | £450K | £200K (-56%) |
| GP Tracking Accuracy | 75% | 95%+ |
| Margin Improvement | 10.5% | 11.5% (+100bps) |

**Financial Impact:**
- **Year 1:** £200K-£300K savings
- **ROI:** 1,900% over 3 years
- **Payback:** 4-5 months

---

## 2. Technical Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **Frontend/UI** | **Figma Make** | Claude-powered UI builder with Figma design system |
| **AI/Agent Layer** | **Claude 4 Sonnet + Agent SDK** | GP analysis, quotation advisor, intervention recommendations |
| **Database** | **Supabase PostgreSQL** | Real-time order tracking, GP stages, historical analysis |
| **Integration Hub** | **Supabase Edge Functions** | ERP, CRM, vessel tracking, warehouse APIs |
| **Hosting** | **Vercel + Supabase** | Frontend CDN, serverless backend |

---

## 3. Core Functional Requirements

### FR-1: Three-Stage GP Tracking

**Booked GP (Stage 1):**
- Calculated at order time with 4-day storage assumption
- Based on quote accepted by customer
- Used for initial sales commission calculation

**Current GP (Stage 2):**
- Real-time updates based on vessel ETA changes
- Adjusted for customer pickup schedule shifts
- Storage cost accumulation tracked daily
- Alerts triggered when erosion >5%

**Realized GP (Stage 3):**
- Final actual profit after delivery complete
- Actual storage days × actual storage cost
- Used for final commission calculation
- Feeds into historical model training

**Data Model:**
```sql
CREATE TABLE gp_tracking (
  id UUID PRIMARY KEY,
  order_id UUID REFERENCES orders(id),
  
  -- Stage 1: Booked
  booked_gp DECIMAL(10,2) NOT NULL,
  storage_days_assumed INTEGER DEFAULT 4,
  booked_at TIMESTAMPTZ NOT NULL,
  
  -- Stage 2: Current
  current_gp DECIMAL(10,2) NOT NULL,
  storage_days_estimated INTEGER,
  vessel_eta TIMESTAMPTZ,
  updated_at TIMESTAMPTZ NOT NULL,
  
  -- Stage 3: Realized
  realized_gp DECIMAL(10,2),
  storage_days_actual INTEGER,
  delivered_at TIMESTAMPTZ,
  
  -- Variance
  gp_erosion DECIMAL(10,2) GENERATED ALWAYS AS 
    (booked_gp - COALESCE(realized_gp, current_gp)) STORED
);
```

### FR-2: £450K Storage Cost Allocation

**MVP Allocation (Order-Level):**
```python
ANNUAL_STORAGE_COST = 450_000  # £450K baseline
DAILY_COST = 450_000 / 365  # £1,233/day
AVG_CONTAINERS = 350
COST_PER_CONTAINER_DAY = 1_233 / 350  # £3.52/day

def allocate_storage_mvp(order):
    container_share = order.value / order.container.total_value
    daily_cost = 3.52 * container_share
    total_cost = daily_cost * storage_days
    return total_cost
```

**Phase 1 Allocation (Customer + Route):**
- Top 20 customers identified by storage cost contribution
- Supplier routes ranked (Australia vs NZ vs Iceland)
- Customer behavioral metrics (avg pickup delay)

**Phase 2 Allocation (SKU-Level):**
- Product category tracking (beef/lamb/pork/poultry)
- Top 50 SKUs by volume
- SKU-specific storage requirements (space, temperature)

**Reporting Views:**
```sql
-- Top customers driving storage costs
SELECT 
  customer_name,
  COUNT(*) AS order_count,
  SUM(total_storage_cost) AS total_cost,
  AVG(storage_days) AS avg_days,
  SUM(cost_overrun) AS overrun
FROM storage_cost_allocation
GROUP BY customer_name
ORDER BY overrun DESC
LIMIT 20;
```

### FR-3: AI-Powered Quotation Assistant

**Claude Agent analyzes:**
- Supplier reliability (historical on-time % for route)
- Customer pickup behavior (avg delay for this customer)
- Seasonal factors (holiday periods, weather)

**Recommends storage buffer:**
```typescript
// Example: NZ route quote
{
  "supplier_reliability": 62,  // 62% on-time
  "customer_punctuality": 75,  // Customer usually +2 days
  "seasonal_risk": 40,         // December holidays
  "overall_risk_score": 59,
  "recommended_buffer_days": 4,
  "recommended_buffer_cost": 42,  // £3.52/day × 4
  "confidence": 78,
  "reasoning": "NZ route 38% delay rate (avg +3 days when late). Customer ABC typically +2 days beyond schedule. December adds moderate risk. Recommend 4-day buffer."
}
```

### FR-4: Proactive Intervention System

**Alert Levels:**
| Level | Erosion % | Recipients | SLA |
|-------|-----------|------------|-----|
| Level 1: Warning | 5-15% | Sales Rep, Ops | 24 hours |
| Level 2: Urgent | 15-25% | + Manager | 4 hours |
| Level 3: Critical | >25% | + CFO/COO | 1 hour |

**AI-Generated Action Plans:**
```typescript
// Example intervention for 15% erosion
{
  "priority": "urgent",
  "recommended_actions": [
    {
      "action": "Contact customer immediately",
      "owner": "Sarah (Sales Rep)",
      "due": "Today 5pm",
      "expected_impact": "£280 saved"
    },
    {
      "action": "Offer pickup incentive (3% next order)",
      "owner": "Sales Manager",
      "due": "Today 5pm",
      "expected_impact": "£180 net savings"
    }
  ]
}
```

### FR-5: Historical Simulation (MVP)

**Validate model with 12 months of historical data:**
- Replay 1,200 orders (Jan-Dec 2024)
- Calculate: predicted storage days vs actual
- Measure accuracy: MAE, RMSE, error bands
- Target: >85% accuracy (within ±15% error)

**Business Case Output:**
- Total erosion: £450K validated
- Root causes: Vessel delays (52%), Customer delays (38%), Other (10%)
- Addressable opportunity: £300K annual (67% recoverable)
- Model confidence: 89.5% of orders within ±20% error

---

## 4. Figma Make Platform Architecture

**How Figma Make Works:**

```
┌─────────────────────────────────────────────────────────┐
│                   Figma Make Workflow                   │
├─────────────────────────────────────────────────────────┤
│                                                         │
│ 1. DESIGN IN FIGMA                                      │
│    Designer creates GP Guardian dashboard               │
│    with interactive prototypes                          │
│    ↓                                                    │
│                                                         │
│ 2. CLAUDE ANALYZES DESIGN                               │
│    • Identifies components (buttons, cards, charts)     │
│    • Maps to shadcn/ui component library                │
│    • Extracts design tokens (colors, spacing, fonts)    │
│    • Understands interaction flows                      │
│    ↓                                                    │
│                                                         │
│ 3. AUTO-GENERATE CODE                                   │
│    • React components (TypeScript)                      │
│    • Tailwind CSS styles                                │
│    • Zustand store (state management)                   │
│    • Supabase API integration                           │
│    ↓                                                    │
│                                                         │
│ 4. DEVELOPER CUSTOMIZATION                              │
│    • Add business logic                                 │
│    • Connect Claude Agents                              │
│    • Implement error handling                           │
│    ↓                                                    │
│                                                         │
│ 5. ONE-CLICK DEPLOY                                     │
│    • Automatic build on git push                        │
│    • Preview URLs for every PR                          │
│    • Production deployment to Vercel                    │
└─────────────────────────────────────────────────────────┘
```

**Key Benefits:**
- Design-code sync (changes in Figma → auto-generate PR)
- WCAG 2.1 AA accessibility built-in
- Responsive breakpoints from Figma designs
- Native Supabase connection (auth, database, storage)

---

## 5. Implementation Roadmap

### Phase 0: MVP - Historical Validation (30 Days)
**Budget:** £15,000  
**Goal:** Validate model with 12 months of data, prove £450K erosion, secure go/no-go

**Deliverables:**
- [ ] 1,200 historical orders imported to Supabase
- [ ] Simulation Agent functional (Claude + Agent SDK)
- [ ] Business case report (executive summary + interactive dashboard)
- [ ] Model accuracy >85% validated
- [ ] Steering committee approval

### Phase 1: Pilot - Live Tracking (60 Days)
**Budget:** £25,000  
**Goal:** Deploy live GP tracking for 20 orders, validate 90%+ accuracy, achieve 80%+ adoption

**Deliverables:**
- [ ] Figma Make application deployed (executive, ops, sales dashboards)
- [ ] Three Claude Agents operational (Quotation, Monitoring, Intervention)
- [ ] ERP integration (daily order sync)
- [ ] Vessel tracking integration (4-hour polling)
- [ ] 20 pilot orders tracked end-to-end
- [ ] >3 successful interventions (GP recovered)

### Phase 2: Scale - Full Deployment (90 Days)
**Budget:** £75,000  
**Goal:** 100% order coverage, CRM integration, commission alignment, SKU-level allocation

**Deliverables:**
- [ ] All orders (~100/month) automatically tracked
- [ ] CRM bidirectional sync (GP risk scores in sales workflow)
- [ ] Sales compensation integration (70% booked + 30% realized)
- [ ] SKU-level cost allocation (top 50 SKUs)
- [ ] Mobile PWA deployed (iOS/Android)
- [ ] £200K+ annual savings validated

---

## 6. Budget & ROI Summary

### Total Investment
| Phase | Duration | Budget |
|-------|----------|--------|
| MVP | 30 days | £15K |
| Pilot | 60 days | £25K |
| Scale | 90 days | £75K |
| **TOTAL Year 1** | **180 days** | **£115K** |

### Financial Projections (Base Case)
| Year | Investment | Savings | Net Benefit | ROI |
|------|------------|---------|-------------|-----|
| Year 1 | £115K | £243K | £128K | 111% |
| Year 2 | £30K | £285K | £255K | 850% |
| Year 3 | £30K | £304K | £274K | 913% |

**Payback Period:** 5.7 months  
**3-Year NPV (10% discount):** £489,000

---

## 7. Success Metrics

### North Star Metric
**GP Realization Rate:** (Realized GP / Booked GP) × 100  
**Target:** 95%+ by Month 6

### Key Performance Indicators

**Financial:**
- Gross Margin: 10.5% → 11.5% (+100bps)
- EBITDA: £1.4M → £1.7M (+21%)
- Storage Cost: £450K → £200K (-56%)

**Operational:**
- Average Storage Days: 12 → 5 days
- GP Forecast Accuracy: 75% → 95%
- Proactive Interventions: 0 → 200+/year

**Adoption:**
- CRM Data Quality: >95% complete
- Sales Team Usage: >90% weekly active
- Alert Response Rate: >85% within SLA

---

## 8. Risk Assessment

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Sales adoption <80% | Medium | High | Executive sponsorship, commission alignment |
| Model accuracy degrades | Low | High | Continuous monitoring, monthly recalibration |
| Data quality issues | Medium | Medium | Validation layer, manual override capability |
| Customer pricing pushback | Medium | Medium | Transparent communication, value demonstration |

---

## 9. Go/No-Go Decision Framework

### After MVP (Day 30):
✅ **GO if:**
- Model accuracy >85%
- £450K erosion validated (±10%)
- Addressable opportunity £200K-£300K clear
- Steering committee approval

❌ **NO-GO if:**
- Model accuracy <75%
- Data quality too poor to validate
- Business case unclear or ROI <100%

### After Pilot (Day 90):
✅ **GO if:**
- Live accuracy >90%
- Sales adoption >80%
- ≥3 successful interventions
- System uptime >99%

❌ **NO-GO if:**
- Accuracy <85% on live orders
- Sales resistance strong
- Technical reliability issues

---

## 10. Next Steps

### Immediate (Week 1):
1. **Secure executive approval** - CEO/CFO sign-off on MVP budget (£15K)
2. **Allocate resources** - Data Engineer, Claude Developer, BA (part-time)
3. **Initiate data export** - Request 12 months of order data from ERP team
4. **Set up Supabase project** - Create database, configure auth, initialize tables

### Week 2-4:
5. **Import historical data** - 1,200 orders into Supabase
6. **Build Simulation Agent** - Claude 4 Sonnet + Agent SDK
7. **Run full simulation** - Validate £450K erosion, measure accuracy
8. **Generate business case** - Executive report + interactive dashboard

### Week 5 (Decision Point):
9. **Present findings** to steering committee
10. **Secure approval** for Pilot Phase (£25K)
11. **Kick off live system development** if approved

---

## Appendices

### A. Data Schema Reference
See full database schema in technical implementation guide (separate document)

### B. API Specifications
See API endpoint documentation (separate document)

### C. Claude Agent Prompts
See agent prompt templates (separate document)

### D. Figma Design Files
Access Figma Make project: [URL to be provided after setup]

---

**Document Owner:** Amanda (AI/BI Consultant)  
**Technical Lead:** [TBD]  
**Business Sponsor:** CEO/CFO WWGiles  
**Last Updated:** 2025-11-09  
**Version:** 1.1 (CORRECTED)

---

## Document Approval

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Product Owner | Amanda | | |
| Technical Lead | [TBD] | | |
| Business Sponsor | CEO/CFO | | |
| Finance Director | [TBD] | | |
| Sales Director | [TBD] | | |

---

**END OF DOCUMENT**
