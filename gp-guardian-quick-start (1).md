# GP Guardian MVP - 30-Day Quick Start Guide

## 🎯 Mission: Prove £300K Annual Savings in 30 Days

**Goal:** Validate GP Guardian concept through historical simulation + live pilot  
**Investment:** £25K development  
**Timeline:** 30 days to pilot launch → 60 days to go/no-go decision  
**Expected ROI:** 10x return (£250K+ annual savings)

---

## 📊 The Business Problem

| Current State | Cost Impact | MVP Solution |
|---------------|-------------|--------------|
| Storage costs allocated generically (not per order) | £450K annual waste | Track actual storage days per order |
| Quotes based on 4-day assumption | 33% of orders take 12+ days | Risk-adjusted pricing with AI advisor |
| GP erosion discovered at invoice time | 2.1% margin loss (£100K+ annual) | Real-time alerts when costs escalate |
| No visibility into vessel reliability | Repeated delays on same routes | Historical pattern recognition |

**Bottom Line:** WWG is pricing orders assuming 4-day storage, but reality is 12 days. This £300K/year margin leak is preventable with AI-powered forecasting and real-time tracking.

---

## 🚀 MVP Scope: What We're Building

### ✅ IN SCOPE (MVP)

1. **Historical Simulation Engine**
   - Import 12 months of order data (350+ orders)
   - Calculate vessel reliability by route
   - Predict storage days for each historical order
   - Measure accuracy (MAPE target: <15%)
   - Generate "what if we had this system" savings report

2. **Live GP Tracker Dashboard**
   - Order list view (status, booked GP, current GP, variance)
   - Order detail view (GP waterfall chart)
   - Basic analytics (KPIs, charts)
   - Manual data entry forms for pilot orders

3. **Claude AI Quotation Advisor**
   - Analyzes vessel reliability + customer history
   - Recommends risk-adjusted pricing
   - Calculates storage buffer (4, 6, 8, or 10 days)
   - Warns if quote below 18% margin floor

4. **Email Alert System**
   - Watch (>1% variance) → Daily digest to rep
   - Concern (>3% variance) → Immediate to rep + manager
   - Critical (>5% variance or <18% margin) → Escalation to exec team

5. **Pilot with 20 Orders**
   - 2 sales reps + 1 manager + 1 ops coordinator
   - 60 days of live tracking
   - Measure GP saved through interventions

### ❌ DEFERRED TO V2

- Real-time vessel tracking API (MarineTraffic)
- Automated ERP/CRM/logistics integrations
- Mobile PWA app
- Multi-agent orchestration (full Agent SDK)
- Commission calculation automation
- Advanced intervention workflows
- What-if scenario planning

**MVP Philosophy:** Manual is OK. CSV imports are OK. Prove the concept before automating everything.

---

## 📅 30-Day Sprint Plan

### Week 1-2: Historical Simulation (PROOF OF CONCEPT)

**Objective:** Prove predictive model works on 12 months of historical data

**Tasks:**

| Day | Task | Owner | Hours | Deliverable |
|-----|------|-------|-------|-------------|
| 1-2 | Set up Supabase project + database schema | Dev | 12 | DB with orders, vessels, simulation tables |
| 3-5 | Collect & clean historical data (350 orders) | Data Analyst | 24 | Clean CSV ready for import |
| 6-7 | Build CSV import tool | Dev | 12 | Import script + validation |
| 8-10 | Build simulation engine | Dev | 16 | Storage day prediction algorithm |
| 11-12 | Run simulation + accuracy analysis | Dev + Analyst | 8 | MAPE report |
| 13-14 | Review results + refine model if needed | Team | 4 | Go/no-go on simulation accuracy |

**Success Criteria:**
- ✅ MAPE <15% on storage day predictions
- ✅ 80%+ accuracy identifying orders with >3% GP erosion
- ✅ Estimated £200K+ annual savings if alerts acted on

**Checkpoint:** If accuracy too low, iterate model. Budget 3 extra days buffer for refinement.

---

### Week 3-4: Dashboard + AI Agent (BUILD MVP)

**Objective:** Build functional dashboard with Claude advisor ready for UAT

**Tasks:**

| Day | Task | Owner | Hours | Deliverable |
|-----|------|-------|-------|-------------|
| 15-16 | Set up Next.js + shadcn/ui | Dev | 4 | Frontend foundation |
| 17-18 | Build order list view (filters, sorting) | Dev | 12 | Functional order list |
| 19-20 | Build order detail view (GP waterfall) | Dev | 12 | Order detail page |
| 21-22 | Build analytics dashboard (KPIs + charts) | Dev | 16 | Analytics tab |
| 23-24 | Integrate Claude API + tool functions | AI Specialist | 16 | Quotation advisor working |
| 25-26 | Build agent UI component | Dev | 8 | "Get AI Recommendation" button |
| 27 | Build email alert system | Dev | 12 | Alert emails sending |
| 28 | Build data entry forms | Dev | 8 | Manual order entry |
| 29 | User acceptance testing (3 reps) | Product Owner | 8 | Feedback doc |
| 30 | Bug fixes from UAT | Dev | 12 | MVP ready for pilot |

**Success Criteria:**
- ✅ Dashboard loads <2 seconds
- ✅ Claude agent responds <5 seconds
- ✅ Users can complete order entry in <5 minutes
- ✅ No critical bugs blocking pilot

**Deliverable:** Functional MVP deployed to staging environment

---

### Week 5-6: Live Pilot (VALIDATE IN PRODUCTION)

**Objective:** Track 20 real orders through full lifecycle, measure GP protection

**Pilot Team:**
- 2 sales reps (use Claude advisor for all new quotes)
- 1 sales manager (review alerts weekly)
- 1 operations coordinator (update vessel/delivery status)
- Product owner (weekly check-ins, monitor usage)

**Pilot Process:**

**Sales Rep Workflow:**
1. Customer requests quote for product
2. Click "Get AI Quote Recommendation" in dashboard
3. Enter: customer, product, quantity, origin, vessel, base cost
4. Claude analyzes vessel reliability + customer history
5. Recommends price with storage buffer (e.g., "£12.95/kg with 6-day buffer")
6. Rep adjusts if needed, sends quote to customer
7. If order booked, enter into GP Guardian dashboard

**Operations Workflow:**
1. When vessel departs, update status to "In Transit"
2. When vessel arrives, enter actual arrival date
3. When goods delivered, enter delivery date
4. System calculates actual storage days + cost
5. Alert triggered if GP variance >threshold

**Manager Workflow:**
1. Review alert emails (watch/concern/critical)
2. Assess mitigation options with rep
3. Document intervention actions taken
4. Weekly meeting to review GP at risk

**Pilot Success Metrics:**

| Metric | Target | How Measured |
|--------|--------|--------------|
| Orders tracked | 20 | Count in dashboard |
| GP erosion detected | 5-8 orders (25-40%) | Alert history log |
| Successful interventions | 50%+ of alerts | Manual tracking during pilot |
| Alert accuracy (precision) | 80%+ | True positives / all alerts |
| User engagement | 80%+ check weekly | Dashboard access logs |

**Weekly Check-ins:**
- Review new orders entered
- Discuss alerts triggered
- Document intervention outcomes
- Address usability issues

---

### Week 7-8: Evaluation & Go/No-Go Decision

**Objective:** Analyze pilot results and decide whether to invest in full rollout

**Evaluation Tasks:**

| Task | Owner | Output |
|------|-------|--------|
| Calculate actual GP saved | Analyst | £X saved on 20 orders |
| Extrapolate to annual savings | Analyst | Projected £200K+ annual |
| Measure alert accuracy | Analyst | Precision/recall metrics |
| Analyze false positives/negatives | Analyst | Root cause analysis |
| Conduct user interviews | Product Owner | Usability feedback doc |
| Document lessons learned | Product Owner | Improvement recommendations |
| Create executive summary | Product Owner | 1-page go/no-go brief |
| Present to leadership | Sponsor | Decision made |

**Go/No-Go Criteria:**

**✅ GO if:**
- MAPE <15% on historical simulation ✓
- 50%+ of at-risk orders had successful intervention ✓
- Alert precision >80% ✓
- User feedback positive (no major blockers) ✓
- Clear path to £200K+ annual ROI ✓

**→ Actions if GO:**
- Budget £75K for v2 development (3 months)
- Plan API integrations (ERP, CRM, vessel tracking)
- Roll out to full sales team (10 reps)
- Scale infrastructure for 350+ orders/year
- Set v2 launch date

**🛑 NO-GO if:**
- Model accuracy consistently below target
- Multiple critical usability issues
- Sales reps don't see value
- ROI unclear or too low

**→ Actions if NO-GO:**
- Document specific failure points
- Decide: Iterate MVP vs. pivot approach
- Preserve code for potential future use

---

## 🛠️ Technical Architecture (Simplified)

```
┌─────────────────────────────────────────────────────────────┐
│  FRONTEND (Next.js + shadcn/ui)                             │
│  ┌──────────────────┐  ┌──────────────────┐  ┌───────────┐ │
│  │  Order List      │  │  Order Detail    │  │ Analytics │ │
│  │  - Filters       │  │  - GP Waterfall  │  │ - KPIs    │ │
│  │  - Sorting       │  │  - Timeline      │  │ - Charts  │ │
│  │  - Alert badges  │  │  - AI Insights   │  │           │ │
│  └──────────────────┘  └──────────────────┘  └───────────┘ │
└──────────────────────────┬──────────────────────────────────┘
                           │ Next.js API Routes
┌──────────────────────────▼──────────────────────────────────┐
│  BACKEND (Supabase)                                          │
│  ┌────────────────────────────────────────────────────────┐ │
│  │  PostgreSQL Database                                   │ │
│  │  - orders (historical + live)                          │ │
│  │  - vessel_performance                                  │ │
│  │  - alerts                                              │ │
│  │  - simulation_results                                  │ │
│  └────────────────────────────────────────────────────────┘ │
│  ┌────────────────────────────────────────────────────────┐ │
│  │  Edge Functions (Serverless)                           │ │
│  │  - Simulation engine                                   │ │
│  │  - GP calculation                                      │ │
│  │  - Alert triggers                                      │ │
│  │  - Email notifications                                 │ │
│  └────────────────────────────────────────────────────────┘ │
└──────────────────────────┬──────────────────────────────────┘
                           │ API Calls
┌──────────────────────────▼──────────────────────────────────┐
│  AI AGENT (Claude 4 Sonnet via Anthropic API)               │
│  ┌────────────────────────────────────────────────────────┐ │
│  │  Quotation Advisor Agent                               │ │
│  │  Tools:                                                │ │
│  │  - get_vessel_reliability(route)                       │ │
│  │  - get_customer_history(customer_name)                 │ │
│  │  - calculate_risk_buffer(vessel_rate, pickup_days)     │ │
│  │  - generate_quote(cost, buffer_days, target_margin)    │ │
│  └────────────────────────────────────────────────────────┘ │
└─────────────────────────────────────────────────────────────┘
```

**Key Design Decisions:**

1. **Supabase over custom backend:** Built-in auth, real-time, storage. PostgreSQL for complex queries. Free tier covers MVP.

2. **Next.js + shadcn/ui over Figma design:** Faster to build. Production-quality components out of box. Vercel deployment instant.

3. **Lightweight agent over Agent SDK:** Direct Claude API + function calling simpler for MVP. Upgrade to full SDK in v2.

4. **CSV import over API integrations:** Get historical data in days, not weeks. Manual entry OK for 20 pilot orders.

5. **Email alerts over complex workflows:** SendGrid integration straightforward. Advanced intervention workflows in v2.

---

## 📦 Data Requirements

### Historical Data for Simulation (CSV Import)

**Required Fields:**

```csv
order_id,order_date,customer,product,quantity_kg,origin,vessel_name,
expected_arrival,actual_arrival,actual_delivery,
booked_landed_cost,booked_price,actual_total_cost,actual_revenue
```

**Example Row:**

```
ORD-2024-001,2024-01-15,ABC Restaurant,Australian Ribeye,8000,Australia,MV Pacific Star,
2024-02-20,2024-02-25,2024-03-08,
8.20,12.50,72500,100000
```

**Data Quality Checks:**
- No nulls in critical fields (order_id, dates, costs, revenue)
- Dates in logical order (order < arrival < delivery)
- Costs and prices are positive
- Actual arrival date present for completed orders

**Estimated Volume:** 350 orders over 12 months

**Source:** ERP export or Excel spreadsheet from finance

---

### Pilot Data Entry (Manual Forms)

**New Order Form (Sales Rep):**
- Customer name (dropdown from historical data)
- Product (dropdown)
- Quantity (kg)
- Origin country (dropdown)
- Vessel name (text)
- Expected arrival date (date picker)
- Booked landed cost per kg (£)
- Booked price per kg (£)

**System Calculates Automatically:**
- Booked storage days (default 4, or from AI recommendation)
- Booked storage cost
- Booked GP %
- Booked GP £

**Status Update Forms (Operations):**

**When vessel departs:**
- Order ID (dropdown)
- Vessel departed date

**When vessel arrives:**
- Order ID
- Actual arrival date
- Customs clearance date

**When goods delivered:**
- Order ID
- Actual delivery date
- Actual costs (if different from booked)

**System Calculates:**
- Actual storage days
- Actual storage cost
- GP variance
- Alert level (watch/concern/critical)

---

## 🎯 Success Metrics Dashboard

### Historical Simulation Report

```
╔══════════════════════════════════════════════════════════════╗
║  GP GUARDIAN HISTORICAL SIMULATION RESULTS (12 MONTHS)       ║
╠══════════════════════════════════════════════════════════════╣
║  Orders Analyzed:                                        358  ║
║                                                               ║
║  STORAGE DAY PREDICTION ACCURACY                             ║
║  ├─ MAPE (Mean Absolute % Error):                      12.3% ║
║  ├─ Average Predicted Storage Days:                      7.2  ║
║  ├─ Average Actual Storage Days:                         8.1  ║
║  └─ Correlation (R²):                                    0.89 ║
║                                                               ║
║  GP EROSION DETECTION ACCURACY                               ║
║  ├─ Orders with >3% GP Erosion (Actual):                 87  ║
║  ├─ Correctly Flagged (True Positives):                  71  ║
║  ├─ Missed (False Negatives):                            16  ║
║  ├─ False Alarms (False Positives):                      23  ║
║  ├─ Precision (TP / TP+FP):                             75%  ║
║  └─ Recall (TP / TP+FN):                                82%  ║
║                                                               ║
║  FINANCIAL IMPACT ANALYSIS                                   ║
║  ├─ Total GP Erosion (Actual):                        £315K  ║
║  ├─ GP Erosion on Flagged Orders:                     £240K  ║
║  ├─ Estimated Savings (50% intervention success):     £120K  ║
║  └─ Potential Annual Savings (full rollout):          £200K+ ║
║                                                               ║
║  VESSEL RELIABILITY INSIGHTS                                 ║
║  ├─ Australia Route On-Time Rate:                       72%  ║
║  ├─ New Zealand Route On-Time Rate:                     85%  ║
║  ├─ Iceland Route On-Time Rate:                         91%  ║
║  └─ Average Delay When Late:                         4.5 days║
║                                                               ║
║  ✅ RECOMMENDATION: PROCEED TO PILOT                         ║
║  Model accuracy exceeds target. Estimated ROI: 8x            ║
╚══════════════════════════════════════════════════════════════╝
```

### Pilot Performance Dashboard (Week 5-6)

```
╔══════════════════════════════════════════════════════════════╗
║  GP GUARDIAN PILOT - LIVE TRACKING (20 ORDERS)               ║
╠══════════════════════════════════════════════════════════════╣
║  PILOT STATUS                                                ║
║  ├─ Orders Tracked:                                20 / 20  ║
║  ├─ Quotes with AI Advisor:                        18 / 20  ║
║  ├─ Completed Orders:                                    14  ║
║  └─ In Progress:                                          6  ║
║                                                               ║
║  GP PROTECTION METRICS                                       ║
║  ├─ Alerts Triggered:                                      8  ║
║  │   ├─ Watch (>1%):                                      3  ║
║  │   ├─ Concern (>3%):                                    4  ║
║  │   └─ Critical (>5%):                                   1  ║
║  ├─ Interventions Taken:                                   5  ║
║  ├─ Successful Mitigation:                                 4  ║
║  └─ GP Saved from Interventions:                      £12.5K║
║                                                               ║
║  ALERT ACCURACY (Completed Orders Only)                     ║
║  ├─ True Positives:                                        5  ║
║  ├─ False Positives:                                       1  ║
║  ├─ Precision:                                           83% ║
║  └─ Meets Target (>80%):                                  ✅  ║
║                                                               ║
║  USER ADOPTION                                               ║
║  ├─ Weekly Dashboard Checks (Avg):                      85% ║
║  ├─ AI Advisor Usage Rate:                              90% ║
║  └─ Manual Entry Compliance:                            95% ║
║                                                               ║
║  EXTRAPOLATED ANNUAL IMPACT (if scaled to 350 orders)       ║
║  ├─ Projected GP Saved:                                £218K ║
║  ├─ System Cost (v2 development):                       £75K ║
║  └─ Net Annual Benefit:                                £143K ║
║                                                               ║
║  ✅ PILOT SUCCESS - RECOMMEND V2 INVESTMENT                  ║
╚══════════════════════════════════════════════════════════════╝
```

---

## 💰 Business Case Summary

### Investment Required

| Phase | Cost | Timeline |
|-------|------|----------|
| **MVP Development** | £25K | 30 days |
| Historical simulation | £8K | Week 1-2 |
| Dashboard + agent build | £15K | Week 3-4 |
| Pilot execution | £2K | Week 5-8 |
| **V2 Development (if go)** | £75K | 3 months |
| API integrations | £30K | |
| Advanced AI agents | £25K | |
| Mobile PWA | £15K | |
| Infrastructure scale | £5K | |
| **Total Investment** | **£100K** | **4 months** |

### Expected Return

| Metric | Current | With GP Guardian | Improvement |
|--------|---------|------------------|-------------|
| **Storage Days (Avg)** | 12 days | 4-6 days | -50% to -67% |
| **Annual Storage Cost** | £450K | £150K-£225K | -£225K to -£300K |
| **Gross Margin** | 18% | 18.5%-19% | +0.5% to +1% |
| **EBITDA** | £1.4M | £1.6M-£1.7M | +£200K to +£300K |

**Year 1 ROI:**  
- Investment: £100K  
- Return: £200K-£300K  
- Net Benefit: £100K-£200K  
- ROI: **100%-200%**

**Year 2-3 (No Additional Investment):**  
- Annual Benefit: £250K-£300K  
- NPV (3 years): **£500K-£675K**

---

## 🚨 Risk Management

### Top 5 Risks & Mitigation

| Risk | Probability | Impact | Mitigation |
|------|------------|--------|------------|
| **1. Historical data incomplete/inaccurate** | Medium | High | ▸ Week 1 data discovery assessment<br>▸ Define minimum viable dataset (80% coverage)<br>▸ Budget for manual cleanup<br>▸ Fallback: Use 6 months if 12 not viable |
| **2. Model accuracy below target (MAPE >15%)** | Medium | High | ▸ Week 2 checkpoint to review accuracy<br>▸ 1-week buffer for model refinement<br>▸ Add more predictive factors if needed<br>▸ Proceed to pilot with lower accuracy but document limitations |
| **3. Sales reps don't adopt during pilot** | Low | High | ▸ Involve reps in UAT (build buy-in)<br>▸ Keep data entry <5 min per order<br>▸ Show immediate value (AI recommendations)<br>▸ Sales manager enforces usage<br>▸ Gamify: Celebrate GP saves |
| **4. Claude agent takes too long to build** | Low | Medium | ▸ Use lightweight approach (not full SDK)<br>▸ Defer complex workflows to v2<br>▸ Developer experienced with Claude API<br>▸ Weekly sprint reviews catch blockers early |
| **5. Pilot reveals major usability issues** | Medium | Medium | ▸ UAT in Week 4 surfaces issues early<br>▸ Budget for bug fixes before pilot<br>▸ Iterate weekly based on feedback<br>▸ Accept some rough edges for MVP |

---

## ✅ Pre-Launch Checklist

### Before Week 1

- [ ] **Leadership buy-in secured**
  - [ ] CEO/CFO approved £25K MVP budget
  - [ ] CRO committed sales team for pilot
  - [ ] COO committed operations support

- [ ] **Team assembled**
  - [ ] Full-stack developer identified (40 hrs/week)
  - [ ] AI integration specialist identified (20 hrs/week)
  - [ ] Data analyst identified (16 hrs/week)
  - [ ] Product owner (Amanda) available for oversight

- [ ] **Data access confirmed**
  - [ ] Historical order data (12 months) available
  - [ ] ERP export access granted
  - [ ] Finance willing to clean/validate data

- [ ] **Pilot participants committed**
  - [ ] 2 sales reps volunteered
  - [ ] 1 sales manager agreed to weekly reviews
  - [ ] 1 operations coordinator assigned

- [ ] **Technical infrastructure ready**
  - [ ] Supabase account created
  - [ ] Anthropic API key obtained
  - [ ] SendGrid account for email alerts
  - [ ] Vercel account for frontend hosting

### Before Week 3 (UAT)

- [ ] **Historical simulation complete**
  - [ ] MAPE <15% achieved
  - [ ] Simulation report generated
  - [ ] Go decision made based on accuracy

- [ ] **Development environment set up**
  - [ ] Next.js project initialized
  - [ ] Supabase database schema deployed
  - [ ] Claude API integration tested
  - [ ] CI/CD pipeline configured

### Before Week 5 (Pilot Launch)

- [ ] **MVP features complete**
  - [ ] Dashboard functional (order list, detail, analytics)
  - [ ] Claude advisor working
  - [ ] Email alerts sending
  - [ ] Data entry forms ready

- [ ] **UAT passed**
  - [ ] 3 sales reps tested system
  - [ ] Critical bugs fixed
  - [ ] Feedback documented

- [ ] **Pilot onboarding complete**
  - [ ] Training session conducted
  - [ ] User accounts created
  - [ ] Weekly meeting schedule set

### Before Week 7 (Evaluation)

- [ ] **Pilot data collected**
  - [ ] 20 orders tracked
  - [ ] Alert history logged
  - [ ] Intervention outcomes documented
  - [ ] User feedback gathered

---

## 📞 Getting Started

### Immediate Next Steps (This Week)

1. **Review this PRD with leadership team**
   - Schedule 60-minute review meeting
   - Present business case (£200K+ ROI)
   - Secure budget approval (£25K)

2. **Assemble core team**
   - Identify developer + AI specialist
   - Confirm data analyst availability
   - Set kickoff meeting for Week 1 Day 1

3. **Initiate data discovery**
   - Request ERP export of last 12 months orders
   - Assess data completeness
   - Identify any gaps requiring manual entry

4. **Set up technical accounts**
   - Create Supabase project
   - Get Anthropic API key
   - Set up SendGrid for emails

5. **Recruit pilot participants**
   - Identify 2 enthusiastic sales reps
   - Secure sales manager commitment
   - Confirm operations coordinator support

---

## 🎯 Why This Will Work

### Proven Components

✅ **Claude 4 Sonnet:** Industry-leading reasoning for complex analysis  
✅ **Supabase:** Battle-tested platform, 1M+ developers  
✅ **Next.js + shadcn/ui:** Production-ready, Fortune 500 companies use it  
✅ **Historical simulation:** Validate before building (de-risk investment)  
✅ **Small pilot scope:** 20 orders = manageable, low risk

### Unique Advantages

🚀 **First-mover in meat wholesale:** No competitors have AI-powered GP tracking  
🚀 **Proprietary data moat:** Vessel/customer intelligence compounds over time  
🚀 **Self-reinforcing:** Better data → better predictions → better margins  
🚀 **Aligned incentives:** Sales reps benefit from protecting their commissions  
🚀 **Tangible ROI:** Not "AI for AI's sake" - real £200K+ annual savings

### Low Risk, High Reward

- ✅ £25K MVP investment vs. £200K+ annual return = 8x ROI
- ✅ 30 days to proof of concept (fail fast if doesn't work)
- ✅ Manual processes OK for pilot (no big tech debt)
- ✅ Go/no-go decision after 60 days (not locked into long project)
- ✅ If successful, v2 scales to full operation

---

## 📄 Appendix: Key Documents

1. **GP Guardian PRD (Full Version):** See `wwg-gp-guardian-prd.md` for complete product spec
2. **Business Case Analysis:** Original £300K savings calculation
3. **Sales SOP Template:** Context on sales process and W4M BAIV framework
4. **Database Schema:** Detailed schema in Supabase DDL format
5. **Agent Prompt Library:** Claude agent system prompts and tool definitions

---

**Document Version:** 1.0  
**Last Updated:** 2025-11-08  
**Author:** Amanda (AI/BI Consultant)  
**Status:** Ready for Leadership Review

---

**LET'S BUILD THIS! 🚀**

_The first £300K is just the beginning. GP Guardian becomes the data engine powering AI transformation across WWG's entire operation._
