# WWGiles AI Transformation Platform - Complete PRD Package

## 📦 What's Included

This package contains the complete Product Requirements Document (PRD) and implementation guides for the WWGiles AI Transformation Platform project, synthesized from 6 months of strategic planning and consultation.

### Document Overview

```
📁 WWGiles PRD Package/
│
├── 📄 wwgiles-ai-transformation-prd.json (47 KB)
│   └─ Master PRD in schema.org-compliant JSON format
│      • Business context and problem statement
│      • Technical architecture (Supabase + Claude SDK)
│      • Complete data models and schemas
│      • MVP through full platform specifications
│      • Success metrics and risk management
│
├── 📄 wwgiles-technical-implementation-guide.md (42 KB)
│   └─ Detailed technical handbook for developers
│      • Environment setup and dependencies
│      • Supabase database schemas and migrations
│      • Claude Agent SDK implementation patterns
│      • Frontend architecture (React + Next.js)
│      • API specifications
│      • Deployment pipeline configuration
│      • Testing strategy
│      • Monitoring and observability
│
├── 📄 wwgiles-uiux-design-specification.md (41 KB)
│   └─ Complete design system and UI/UX guidelines
│      • Design system (colors, typography, spacing)
│      • Component library (shadcn/ui based)
│      • User personas and journeys
│      • Key interface mockups and layouts
│      • Interaction patterns
│      • Responsive design guidelines
│      • Accessibility standards (WCAG 2.1 AA)
│      • Figma design file structure
│
└── 📄 wwgiles-implementation-roadmap.md (43 KB)
    └─ Project execution plan with sprint-by-sprint breakdown
       • Team structure and roles
       • 5 phases over 12 months
       • Detailed sprint planning (30 sprints)
       • Budget breakdown (£400K total)
       • Risk management framework
       • Success metrics and KPIs
       • Go/no-go decision points
```

---

## 🚀 Quick Start Guide

### For Project Managers

**Start Here:**
1. Read **implementation-roadmap.md** sections 1-3
2. Review team structure and confirm resource availability
3. Set up kickoff meeting with steering committee
4. Approve MVP budget (£15K) and timeline (30 days)

**Next Steps:**
- Schedule weekly working group meetings
- Assign roles (Technical Lead, Full-Stack Dev, Data Engineer, UX Designer)
- Set up project tracking (Jira/Linear/etc)
- Create communication channels (Slack workspace)

### For Technical Leads

**Start Here:**
1. Read **technical-implementation-guide.md** sections 1-3
2. Review **prd.json** → productArchitecture → technicalStack
3. Set up development environment (instructions in guide)
4. Review Supabase database schemas

**Next Steps:**
- Create GitHub repository
- Set up Supabase project (development + staging + production)
- Initialize Next.js application with TypeScript
- Run database migrations
- Deploy "hello world" to Vercel to validate pipeline

### For UX Designers

**Start Here:**
1. Read **uiux-design-specification.md** sections 1-2
2. Review design system (colors, typography, spacing)
3. Familiarize with shadcn/ui component library
4. Review user personas and journeys

**Next Steps:**
- Set up Figma workspace
- Create component library in Figma
- Design GP Guardian dashboard (desktop + mobile)
- Design order detail view with 3-stage GP tracking
- Create interactive prototype for user testing

### For Developers

**Start Here:**
1. Read **technical-implementation-guide.md** sections 2-4
2. Follow environment setup instructions
3. Review database schema and understand data models
4. Review Claude Agent SDK implementation patterns

**Next Steps:**
- Clone repository
- Install dependencies (`pnpm install`)
- Run local development server
- Connect to Supabase dev environment
- Create your first database query
- Implement a simple component

### For Executives

**Start Here:**
1. Review **prd.json** → executiveSummary
2. Review **implementation-roadmap.md** → Executive Summary and Budget Breakdown
3. Review **roadmap** → Go/No-Go Decision Frameworks

**Key Decisions Required:**
- **Week 4**: Approve MVP results and proceed to pilot (£25K)
- **Week 12**: Approve pilot results and proceed to scale (£75K)
- **Week 22**: Approve full deployment and proceed to platform (£180K)

**Expected Outcomes:**
- **Year 1**: 10.5% → 15.0% margins (+£2.39M GP)
- **Year 2**: 15.0% → 18.5% margins (+£1.86M GP)
- **Year 3**: 18.5% → 22.0% margins (+£1.86M GP)
- **3-Year Total**: +11.5 points, £6.1M cumulative GP improvement

---

## 🎯 The Core Problem We're Solving

### Current State: £450K Annual Margin Leak

WWGiles operates with a **critical blind spot** in their sales operations:

```
Sales Process (What Sales Sees):
┌─────────────────────────────────────────────────┐
│ 1. Customer requests quote                      │
│ 2. Calculate price using:                       │
│    • Product cost                                │
│    • Expected 4-day storage                      │
│ 3. Book order with "booked GP"                  │
│ 4. Sales rep gets commission on booked GP ✅    │
└─────────────────────────────────────────────────┘

Reality (What Actually Happens):
┌─────────────────────────────────────────────────┐
│ 1. Vessel delayed (supplier only 62% on-time)  │
│ 2. Storage accumulates for 12 days avg         │
│ 3. Customer pickup delays (15 day avg)         │
│ 4. Storage costs: £3.52/day × 8 extra days     │
│ 5. "Realized GP" is £28 less per order         │
│ 6. Company loses £450K annually 📉             │
└─────────────────────────────────────────────────┘
```

### The Impact

- **Margin erosion:** 0.85% of revenue (£450K on £53M revenue)
- **Bottom quartile performance:** 10.5% margins vs 15-20% industry average
- **EBITDA impact:** 21% of current EBITDA lost to this leak
- **Sales compensation misalignment:** Reps paid on phantom profit, not real profit

### Our Solution: GP Guardian

**Three-Stage GP Tracking:**
```
Stage 1: Booked GP (At Order Booking)
└─ What sales expects: £5,000 GP
   Based on 4-day storage assumption

Stage 2: Current GP (Live During Transit)
└─ What we expect now: £4,750 GP
   Based on vessel ETA + customer pickup pattern
   Updates daily as vessel moves

Stage 3: Realized GP (After Delivery)
└─ What actually happened: £4,650 GP
   Based on actual storage days
   Used for commission adjustment
```

**Expected Results:**
- Reduce average storage from 12 → 6 days
- Recover £225K-£300K annually (50-67% of leak)
- Improve margins by 0.42-0.57 points
- Align sales incentives with actual profitability

---

## 📊 Project Phases & Timeline

### Phase 1: MVP (30 Days) - £15K

**Objective:** Validate the business case with historical data

**What We'll Build:**
- Historical data analysis of 12 months orders
- GP erosion calculation and validation
- Supplier/customer/route intelligence
- Business case report with ROI projection
- Interactive dashboard for scenario modeling

**Success Criteria:**
- ✅ Validate £200K-£300K annual savings opportunity
- ✅ Model accuracy >85%
- ✅ Clear identification of root causes

**Deliverable:** Go/no-go decision package

---

### Phase 2: Pilot (60 Days) - £25K

**Objective:** Prove the system works with live data

**What We'll Build:**
- Real-time GP tracking for 20 orders
- Web dashboard for sales team
- Vessel tracking integration
- Automated alerts and notifications
- ERP integration (one-way)

**Success Criteria:**
- ✅ Model accuracy >85% on live orders
- ✅ Sales adoption >80%
- ✅ Projected annual savings >£150K

**Deliverable:** Production-ready GP Guardian

---

### Phase 3: Scale (90 Days) - £75K

**Objective:** Full deployment + sales excellence foundations

**What We'll Build:**
- All orders tracked automatically
- CRM bidirectional integration
- Sales compensation integration
- Lead scoring
- Email automation
- Meeting prep automation
- BSC scorecard (basic version)

**Success Criteria:**
- ✅ 100% order coverage
- ✅ >90% sales adoption
- ✅ Measurable margin improvement visible

**Deliverable:** Full GP Guardian + Sales Excellence v1

---

### Phase 4: Intelligence (90 Days) - £100K

**Objective:** Add predictive capabilities and advanced intelligence

**What We'll Build:**
- Advanced forecasting (75% → 95% accuracy)
- Win probability calculator
- Dynamic pricing engine
- Churn prediction system
- Customer health scoring
- Whitespace analysis
- Route risk modeling
- Demand forecasting

**Success Criteria:**
- ✅ Forecast accuracy >90%
- ✅ Churn prediction >70% accuracy
- ✅ Margin improvement 10.5% → 15%+

**Deliverable:** Full intelligence suite

---

### Phase 5: Platform (90 Days) - £180K

**Objective:** Multi-tenant SaaS for vertical market

**What We'll Build:**
- Multi-tenant architecture
- Module marketplace
- White-label capabilities
- Public API
- Developer portal
- Marketing website
- Beta customer program (3-5 customers)

**Success Criteria:**
- ✅ 3+ beta customers onboarded
- ✅ Platform stable and scalable
- ✅ Positive customer feedback

**Deliverable:** SaaS platform ready for general availability

---

## 💰 Investment & Returns

### Budget Summary

| Phase | Duration | Investment | Cumulative |
|-------|----------|-----------|------------|
| MVP | 30 days | £15K | £15K |
| Pilot | 60 days | £25K | £40K |
| Scale | 90 days | £75K | £115K |
| Intelligence | 90 days | £100K | £215K |
| Platform | 90 days | £180K | £395K |
| **Total Year 1** | **12 months** | **£395K** | **£395K** |

### ROI Projection

**Year 1:**
- Investment: £70K (MVP + Pilot + Scale)
- Margin improvement: 10.5% → 15.0% (+4.5 points)
- Additional GP: £2.39M
- ROI: 3,300%

**Year 2:**
- Investment: £150K (Intelligence + maintenance)
- Margin improvement: 15.0% → 18.5% (+3.5 points)
- Additional GP: £1.86M
- Cumulative ROI: 1,773%

**Year 3:**
- Investment: £180K (Platform + growth)
- Margin improvement: 18.5% → 22.0% (+3.5 points)
- Additional GP: £1.86M
- Cumulative ROI: 1,425%

**3-Year Totals:**
- Total Investment: £400K
- Total GP Improvement: £6.1M
- Cumulative ROI: 1,425%
- Payback Period: 2 months

---

## 🎨 Design System Overview

### Core Principles

1. **Data Clarity First** - Financial data must be immediately comprehensible
2. **Action-Oriented** - Every view should make the next action obvious
3. **Progressive Disclosure** - Show essentials first, details on demand
4. **Trust Through Transparency** - Show methodology, not just results
5. **Mobile-First for Executives** - Key metrics accessible on-the-go

### Key Components

**Metric Cards:**
```
┌──────────────────────┐
│ £450,000             │  ← Large, bold number
│ Total GP Erosion     │  ← Clear label
│                      │
│ +12% vs last period  │  ← Trend indicator
│ ━━━━━━━━━━━━━━━━━   │  ← Progress bar
└──────────────────────┘
```

**Three-Stage GP Tracking:**
```
┌─────────────┐  ┌─────────────┐  ┌─────────────┐
│ 💚 Booked   │  │ 🟡 Current  │  │ 🔴 Realized │
│   £5,000    │  │   £4,750    │  │   £4,650    │
│  (Expected) │  │ (Predicted) │  │   (Actual)  │
└─────────────┘  └─────────────┘  └─────────────┘
```

**Risk Indicators:**
- 🔴 High Risk (>70%): Immediate action required
- 🟡 Medium Risk (40-70%): Proactive intervention
- 🟢 Low Risk (<40%): Monitor

### Accessibility

All designs meet **WCAG 2.1 Level AA** standards:
- Color contrast ratios: 4.5:1 minimum for text
- Keyboard navigation fully supported
- Screen reader compatible
- Touch targets: 44×44px minimum

---

## 🔧 Technical Architecture

### Core Stack

```
┌─────────────────────────────────────────────────┐
│              Frontend (Vercel)                  │
│  Next.js 13+ | React 18 | TypeScript | Tailwind│
│  shadcn/ui components | Recharts | TanStack    │
└───────────────────┬─────────────────────────────┘
                    │
                    ↓
┌─────────────────────────────────────────────────┐
│            Backend (Supabase)                   │
│  PostgreSQL 15+ | Row Level Security | Realtime│
│  Edge Functions | Storage | PostgREST API      │
└───────────────────┬─────────────────────────────┘
                    │
                    ↓
┌─────────────────────────────────────────────────┐
│          AI Layer (Anthropic)                   │
│  Claude Sonnet 4.5 | Agent SDK | Tool Calling  │
│  GP Analysis Agent | Sales Intelligence Agent  │
└─────────────────────────────────────────────────┘
```

### Key Integrations

1. **ERP System** → Orders, inventory, costs
2. **CRM System** → Opportunities, accounts, activities
3. **Vessel Tracking API** → Real-time location, ETA updates
4. **Email/Slack** → Notifications and alerts

### Data Models

**Core Entities:**
- `orders` - Sales orders with 3-stage GP tracking
- `customers` - Customer profiles with health scores
- `suppliers` - Supplier profiles with reliability scores
- `vessels` - Vessel tracking and performance history
- `opportunities` - Sales pipeline with AI scoring
- `ai_insights` - AI-generated recommendations

**Key Calculations:**
```sql
-- GP Erosion Formula
gp_erosion = booked_gp - realized_gp

-- Where:
booked_gp = sale_price - landed_cost - (£3.52 × 4 days)
realized_gp = sale_price - landed_cost - (£3.52 × actual_days)

-- Customer Health Score (weighted average)
health_score = 
  (order_frequency × 0.25) +
  (order_value_trend × 0.20) +
  (payment_history × 0.20) +
  (nps_normalized × 0.15) +
  (service_quality × 0.10) +
  (engagement × 0.10)
```

---

## 📋 Implementation Checklist

### Before You Start

- [ ] Read all 4 documents
- [ ] Confirm team availability
- [ ] Secure budget approval (£15K for MVP)
- [ ] Get ERP admin access for data export
- [ ] Set up Anthropic account (API key)
- [ ] Set up Supabase account

### Week 1 Tasks

- [ ] Create GitHub repository
- [ ] Initialize Next.js project
- [ ] Set up Supabase project (dev + staging + prod)
- [ ] Run database migrations
- [ ] Extract 12 months historical data from ERP
- [ ] Import data to Supabase
- [ ] Validate data quality (>95% completeness)

### Week 2 Tasks

- [ ] Implement GP Analysis Agent (Claude SDK)
- [ ] Create calculation logic for GP erosion
- [ ] Build query tools for agent
- [ ] Test agent on historical data
- [ ] Validate calculations (spot-check 20 orders)

### Week 3 Tasks

- [ ] Calculate supplier reliability scores
- [ ] Analyze route-specific patterns
- [ ] Identify seasonal trends
- [ ] Build risk scoring model
- [ ] Create data visualizations (Recharts)

### Week 4 Tasks

- [ ] Generate comprehensive business case report
- [ ] Build interactive dashboard
- [ ] Implement scenario modeling
- [ ] Create executive presentation
- [ ] Schedule steering committee demo
- [ ] Get go/no-go decision

---

## ⚠️ Common Pitfalls & How to Avoid Them

### 1. "The Data Quality Trap"

**Problem:** Spending weeks cleaning data before starting development.

**Solution:**
- Accept 95% completeness as "good enough" for MVP
- Start with subset of high-quality data if needed
- Parallelize: clean data while building system
- Use data quality issues to inform v2 requirements

### 2. "The Perfect Dashboard Syndrome"

**Problem:** Over-designing UI before validating core value.

**Solution:**
- MVP dashboard can be basic (tables + simple charts)
- Focus on calculations being correct
- Iterate on UX after proving business case
- Remember: executives care more about insights than pretty charts

### 3. "The Integration Rabbit Hole"

**Problem:** Spending months on ERP/CRM integration.

**Solution:**
- Start with CSV exports (manual is fine for MVP)
- Prove value first, then automate
- Use webhooks for real-time in pilot phase
- Budget for integration specialist if needed

### 4. "The Scope Creep Monster"

**Problem:** Adding "just one more feature" to MVP.

**Solution:**
- Ruthlessly prioritize: what do we NEED to prove the business case?
- Everything else is v2
- Use "now/next/later" framework
- If not in MVP scope, say "great idea for v2!"

### 5. "The Sales Adoption Challenge"

**Problem:** Building it but sales team won't use it.

**Solution:**
- Involve sales champions from day 1
- Make it EASIER than current process, not harder
- Show quick wins (commission protection, better forecasts)
- Gamify adoption (leaderboards, recognition)
- Train, train, train

---

## 📞 Support & Resources

### Internal Contacts

- **Executive Sponsor:** CEO/COO
- **Project Manager:** [To be assigned]
- **Technical Lead:** [To be assigned]
- **Sales Champion:** Sales Director

### External Resources

- **Supabase Documentation:** https://supabase.com/docs
- **Anthropic Claude Documentation:** https://docs.anthropic.com
- **Next.js Documentation:** https://nextjs.org/docs
- **shadcn/ui Components:** https://ui.shadcn.com
- **Recharts Documentation:** https://recharts.org

### Support Channels

- **GitHub Issues:** For bugs and feature requests
- **Slack #wwg-ai-project:** For team communication
- **Weekly Office Hours:** For Q&A and troubleshooting
- **Monthly Steering Committee:** For strategic decisions

---

## 🎯 Success Criteria Summary

### MVP Success (Week 4)
- ✅ £200-300K annual savings validated
- ✅ Model accuracy >85%
- ✅ Executive-ready business case

### Pilot Success (Week 12)
- ✅ Model accuracy >85% on live orders
- ✅ Sales adoption >80%
- ✅ Projected savings >£150K

### Full Deployment (Week 22)
- ✅ Margin improvement visible in P&L
- ✅ 100% order coverage
- ✅ >90% sales adoption

### Year 1 Target
- ✅ 10.5% → 15.0% margins
- ✅ £2.39M additional GP
- ✅ 3,300% ROI

---

## 🚦 Next Steps

### Immediate (This Week)

1. **Executive Sponsor:** Review documents and approve MVP budget
2. **Project Manager:** Schedule kickoff meeting
3. **Technical Lead:** Set up development environment
4. **UX Designer:** Start Figma workspace
5. **Sales Director:** Identify sales champions

### Week 1

1. Kickoff meeting with full team
2. GitHub repository created
3. Supabase project set up
4. Historical data extraction begins
5. Design system work begins

### Week 4

1. MVP demo to steering committee
2. Business case presentation
3. Go/no-go decision
4. If GO: Plan pilot phase
5. If NO-GO: Analyze issues and decide next steps

---

## 📚 Document Change Log

| Date | Version | Author | Changes |
|------|---------|--------|---------|
| 2025-11-09 | 1.0 | Amanda + Claude | Initial PRD package created |

---

## ✅ Approval Sign-Off

**For MVP Commencement:**

- [ ] CEO / Executive Sponsor
- [ ] COO
- [ ] CFO
- [ ] Sales Director
- [ ] Technical Lead

**Date:** _____________

**Next Review:** After MVP completion (Week 4)

---

## 💡 Final Thoughts

This is an ambitious project that will transform WWGiles from bottom-quartile margins to top-quartile performance. The key to success is:

1. **Start small** - Validate the business case with MVP before scaling
2. **Move fast** - 30-day sprints keep momentum
3. **Measure everything** - Data-driven decisions at every stage
4. **Involve users early** - Sales champions are critical
5. **Celebrate wins** - Show value quickly to build momentum

The £450K margin leak is real and validated. GP Guardian is the solution. The technology is proven (Supabase + Claude). The team is capable. The business case is compelling.

**Let's build this.**

---

**Questions?** Contact the project manager or technical lead.

**Ready to start?** Jump to the implementation roadmap, Week 1 tasks.

**Need approval?** Review the Executive Summary section of the PRD.
