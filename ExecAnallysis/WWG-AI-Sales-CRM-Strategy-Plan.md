# WWGiles AI-Powered Sales & CRM Strategy
## Integrated with GP Guardian for Source-to-Paid Optimization

---

## Executive Summary

This strategic plan outlines how WWGiles can leverage AI-powered CRM integration with GP Guardian to transform from industry-bottom-quartile margins (10.5%) to market-leading profitability (22%) by optimizing the complete **Source → Sold → Paid** lifecycle.

### The Core Problem
WWGiles loses **£450,000 annually** through the gap between "booked GP" (calculated assuming 4-day storage) and "realized GP" (actual profit after 12-day average storage plus payment delays). Current sales processes optimize for **volume**, not **profitability**, and CRM data doesn't inform customer targeting based on actual margin contribution or payment behavior.

### The Solution
An AI-powered system that:
1. **Matches aging inventory to optimal customers** who pay quickly at acceptable margins
2. **Tracks GP in real-time** through the complete lifecycle (Booked → Current → Realized)
3. **Prioritizes sales activities** based on customer profitability, not just revenue
4. **Optimizes the entire cash conversion cycle** from source to paid, not just source to sold

### Expected Outcomes
| Metric | Current | Target | Impact |
|--------|---------|--------|--------|
| Realized GP % | 10.5% | 22% | +£600K annual |
| Days Source to Paid | 52 | 35 | -£125K finance costs |
| Storage Cost Leak | £450K | £150K | +£300K annual |
| DSO (Days Sales Outstanding) | 40 | 25 | Better cash flow |

---

## Strategic Framework: BSC Strategy Map

### Financial Perspective (Outcomes)
- **Increase Realized GP to 22%** (from 10.5%)
- **Reduce Finance Costs by 30%** through faster cash conversion
- **Improve Working Capital** efficiency

### Customer Perspective (Value Proposition)
- **Target High-Value Customers** systematically using profitability scoring
- **Reduce DSO from 40 to 25 days** through customer selection
- **Improve Price Realization** from 88% to 95%

### Internal Process Perspective (Operational Excellence)
- **AI-Powered Inventory-Customer Matching** 
- **Real-time GP Tracking** through complete lifecycle
- **Dynamic Pricing Engine** based on inventory age and customer value
- **Source-Sold-Paid Pipeline** visibility and optimization

### Learning & Growth Perspective (Foundation)
- **AI Model Training** and continuous improvement
- **CRM Data Quality** improvement to 95%
- **Sales Team AI Adoption** from 20% to 80%

---

## System Architecture

### Five Integrated Modules

#### 1. Inventory Intelligence Layer
**Purpose:** Real-time visibility into stock position, age, and cost accumulation

**Components:**
- Real-time Stock Position by SKU and container
- Age Tracking per product (critical for margin erosion calculation)
- Cost Accumulation Engine (storage + finance costs)
- Margin Erosion Calculator (alerts when current GP falls below booked GP)

**Key Insight:** Every day beyond 4-day assumed storage erodes approximately £150/container in costs. At 12-day average, this represents £1,200 per container in hidden margin erosion.

#### 2. Customer Intelligence Layer
**Purpose:** Score and segment customers based on actual profitability, not just revenue

**Customer Profitability Score Components:**
| Factor | Weight | Description |
|--------|--------|-------------|
| Margin Contribution | 30% | Actual GP generated, not revenue |
| Payment Speed | 25% | Average DSO - fast payers more valuable |
| Volume Contribution | 20% | But weighted less than margin |
| Price Acceptance | 15% | Do they pay list price or negotiate hard? |
| Growth Potential | 10% | Expansion opportunity |

**Customer Tiers:**
- **Platinum (Score 85+):** Best pricing, dedicated account manager, priority service
- **Gold (Score 70-84):** Standard discount, regular contact
- **Silver (Score 50-69):** List price, automated nurture
- **Bronze (Score <50):** Review for improvement or managed exit

#### 3. AI Matching Engine
**Purpose:** Optimize profitability by matching aging inventory to the right customers

**How It Works:**
1. **Inventory with urgency** (age >10 days) is flagged
2. AI identifies customers who:
   - Have bought this product category before
   - Pay quickly (low DSO)
   - Accept reasonable prices
   - Have upcoming demand (based on patterns)
3. **Sales team receives prioritized action list** with specific recommendations

**Example Output:**
> "URGENT: 2,400kg Striploin (Container AU-2847) at day 11. 
> Recommended targets: 
> 1. Premier Restaurants (DSO: 18 days, price acceptance: 94%)
> 2. Metro Hotels (DSO: 22 days, price acceptance: 91%)
> Suggested price: List minus 5% for immediate commitment"

#### 4. GP Guardian Integration
**Purpose:** Track GP through complete lifecycle with cost allocation

**Three GP Stages:**

| Stage | Calculation | When |
|-------|-------------|------|
| **Booked GP** | Sale price - Landed cost - (4 days × storage rate) | Order confirmation |
| **Current GP** | Sale price - Landed cost - Actual storage to date - Finance cost to date | Real-time during lifecycle |
| **Realized GP** | Payment received - All allocated costs | Payment received |

**Cost Allocation Rules:**
- **Storage Cost:** £150/day per container, allocated pro-rata by value
- **Finance Cost:** 8% annual on landed cost × days outstanding
- **Handling Cost:** £25 per movement, allocated per order line

#### 5. AI-Powered CRM
**Purpose:** Transform sales activities from volume-focused to profit-focused

**Key Features:**
- **Lead Prioritization:** Based on profitability potential, not just size
- **Customer Targeting:** Match inventory urgency to customer propensity
- **Action Recommendations:** AI-generated daily action list
- **Performance Dashboard:** Real-time visibility into GP protection metrics

---

## The Source-to-Paid Lifecycle

### Understanding the Cash Conversion Problem

**Current State:**
- Days from source to arrival: 21-28 days (vessel transit)
- Days in storage: 12 days average (should be 4)
- Days from sale to payment: 40 days average (DSO)
- **Total days source to paid: ~52 days**

**Target State:**
- Days from source to arrival: 21-28 days (fixed - vessel transit)
- Days in storage: 6 days (through better inventory-customer matching)
- Days from sale to payment: 25 days (through customer selection)
- **Total days source to paid: ~35 days**

**Financial Impact of 17-Day Reduction:**
At £53M annual revenue with 8% finance cost:
- Current finance cost: ~£580K annually
- Target finance cost: ~£380K annually
- **Savings: ~£200K annually** (plus storage cost savings)

---

## Detailed Process Flows

### Process 1: Daily Sales Prioritization

**Morning Routine (AI-Generated):**

1. **Inventory Urgency Report**
   - Products >10 days age with available quantity
   - Calculated margin erosion rate
   - Recommended action (sell now vs. hold)

2. **Customer Match List**
   - For each urgent product: top 5 customers to target
   - Customer profitability score and reasoning
   - Suggested pricing and approach

3. **GP Protection Alerts**
   - Orders where current GP has fallen >15% below booked GP
   - Payment overdue alerts with impact calculation
   - Pricing approval requests with margin analysis

### Process 2: Order Creation with GP Forecast

**Enhanced Quoting Process:**

1. **Customer Request Received**
2. **AI Pre-checks:**
   - Customer profitability tier and score
   - Customer payment behavior (average DSO)
   - Customer's price history for this product
3. **Inventory Selection Guidance:**
   - Which container to allocate from (oldest first for commodity, freshest for premium)
   - Calculated current cost including storage accumulated
4. **Pricing Recommendation:**
   - Suggested price based on customer tier and inventory age
   - Calculated booked GP vs. predicted realized GP
   - Approval routing if below margin floor
5. **Order Confirmation with GP Tracking Initiated**

### Process 3: GP Tracking Through Lifecycle

**Continuous Monitoring:**

```
Day 0 (Order):     Booked GP calculated → £2,500 (15% margin)
Day 3 (Storage):   Current GP → £2,400 (storage cost accumulating)
Day 5 (Delivery):  Current GP → £2,350 (handling cost added)
Day 12 (Invoice):  Current GP → £2,300 (still waiting for payment)
Day 25 (Payment):  Realized GP → £2,150 (finance cost deducted)
                   GP Erosion: £350 (14% of booked GP lost)
```

**Alerts Generated:**
- Day 7: "Storage cost alert - customer hasn't collected"
- Day 20: "Payment overdue - finance cost accumulating"
- Day 30: "Escalation required - significant GP erosion"

---

## AI Models and Algorithms

### Model 1: Customer Profitability Scorer

**Algorithm:** Gradient Boosting Classifier

**Features:**
- Historical revenue (12 months)
- Historical margin contribution (12 months)
- Average payment days (DSO)
- Price realization rate (% of list price achieved)
- Order frequency and consistency
- Growth trajectory (comparing recent 3 months to prior 9 months)
- Service/complaint history

**Output:** Score 0-100, updated daily

**Training Data:** 24 months of order and payment history

### Model 2: Inventory-Customer Matcher

**Algorithm:** Collaborative Filtering + Business Rules

**Process:**
1. Calculate product urgency score based on age and margin erosion velocity
2. Filter customers who have purchased this product category
3. Score each customer on:
   - Likelihood to buy (based on purchase patterns)
   - Payment speed (DSO history)
   - Price acceptance (historical realization)
   - Current inventory needs (based on their order patterns)
4. Rank and present top 5-10 matches to sales team

### Model 3: Dynamic Pricing Engine

**Algorithm:** Rule-Based with ML Optimization

**Base Rules:**
| Condition | Price Adjustment |
|-----------|------------------|
| Inventory age 0-4 days | List price |
| Inventory age 5-8 days | List - 2% |
| Inventory age 9-12 days | List - 5% |
| Inventory age 13-15 days | List - 8% |
| Inventory age >15 days | List - 12% |

**Modifiers:**
| Condition | Modifier |
|-----------|----------|
| Customer tier Platinum | Best available |
| Customer tier Gold | Standard discount |
| Customer tier Silver | List price |
| High demand forecast | +2% |
| Low demand forecast | -3% |

**ML Optimization:** Reinforcement learning adjusts base rules based on actual outcomes (did the recommended price result in a sale with acceptable margin?)

### Model 4: Payment Predictor

**Algorithm:** Time Series ML (Prophet + Features)

**Features:**
- Customer's historical payment pattern
- Invoice amount (larger invoices may take longer)
- Day of week/month invoice sent
- Economic indicators
- Customer's recent cash flow signals (if available)

**Output:** Predicted payment date with confidence interval

**Use Case:** Calculate expected realized GP at point of order, factoring in predicted payment timing and associated finance cost.

---

## Implementation Roadmap

### Phase 1: Foundation (Weeks 1-4) - £15,000

**Week 1-2: Data Foundation**
- CRM data audit and cleanup
- Customer profitability baseline calculation
- Inventory data integration verification
- Basic GP tracking setup

**Week 3-4: Basic AI Deployment**
- Customer profitability scorer (v1)
- Basic inventory aging reports
- GP tracking for new orders
- Dashboard for visibility

**Success Metrics:**
- CRM data quality >80%
- All active customers scored
- Real-time inventory visibility established

### Phase 2: Intelligence Layer (Weeks 5-10) - £35,000

**Week 5-6: AI Model Development**
- Advanced profitability model training
- Payment predictor model development
- Inventory-customer matching algorithm

**Week 7-8: Integration**
- GP Guardian full integration
- Dynamic pricing rules engine
- Alert and notification system

**Week 9-10: Testing & Refinement**
- Model validation with historical data
- User acceptance testing
- Performance tuning

**Success Metrics:**
- Profitability model accuracy >85%
- Payment prediction accuracy >80%
- Real-time GP tracking fully operational

### Phase 3: Optimization (Weeks 11-18) - £42,000

**Week 11-12: Advanced Features**
- Inventory-customer matching engine live
- Automated action recommendations
- Approval workflow automation

**Week 13-14: Training & Adoption**
- Sales team training program
- Process documentation
- Change management support

**Week 15-18: Continuous Improvement**
- Model refinement based on feedback
- Performance optimization
- Expanded feature set

**Success Metrics:**
- AI recommendation adoption >60%
- Measurable GP improvement >2%
- DSO reduction >5 days

---

## Key Performance Indicators

### Weekly Dashboard Metrics

**Financial:**
| Metric | Current | Target | Week Trend |
|--------|---------|--------|------------|
| Realized GP % | 10.5% | 22% | ↑↓ |
| Average Days Source to Paid | 52 | 35 | ↑↓ |
| GP Erosion (Booked vs Realized) | 25% | 10% | ↑↓ |

**Customer:**
| Metric | Current | Target | Week Trend |
|--------|---------|--------|------------|
| Average DSO | 40 | 25 | ↑↓ |
| Price Realization % | 88% | 95% | ↑↓ |
| High-Profit Customer Revenue % | 60% | 80% | ↑↓ |

**Operational:**
| Metric | Current | Target | Week Trend |
|--------|---------|--------|------------|
| Average Storage Days | 12 | 6 | ↑↓ |
| Inventory >10 Days % | 35% | 15% | ↑↓ |
| AI Recommendation Adoption | 20% | 80% | ↑↓ |

### Monthly Business Review Focus

1. **GP Bridge Analysis:** Booked GP → Current GP → Realized GP with variance explanation
2. **Customer Profitability Distribution:** Revenue and margin by tier
3. **Inventory Performance:** Age distribution, turnover, storage cost impact
4. **Payment Performance:** DSO by customer segment, aging analysis
5. **AI Model Performance:** Accuracy metrics, adoption rates, impact measurement

---

## ROI Analysis

### Investment Summary
| Phase | Investment | Duration |
|-------|------------|----------|
| Phase 1: Foundation | £15,000 | 4 weeks |
| Phase 2: Intelligence | £35,000 | 6 weeks |
| Phase 3: Optimization | £42,000 | 8 weeks |
| **Total** | **£92,000** | **18 weeks** |

### Annual Benefits
| Benefit Category | Conservative | Expected | Optimistic |
|------------------|--------------|----------|------------|
| Storage Cost Reduction | £200,000 | £300,000 | £350,000 |
| Finance Cost Reduction | £80,000 | £125,000 | £160,000 |
| Margin Improvement | £180,000 | £280,000 | £350,000 |
| **Total Annual Benefit** | **£460,000** | **£705,000** | **£860,000** |

### ROI Metrics
| Metric | Value |
|--------|-------|
| Total Investment | £92,000 |
| Expected Annual Benefit | £705,000 |
| Payback Period | 8 weeks |
| Year 1 ROI | 666% |
| 3-Year NPV (10% discount) | £1,650,000 |

---

## Risk Mitigation

### Key Risks and Mitigations

| Risk | Likelihood | Impact | Mitigation |
|------|------------|--------|------------|
| Data quality issues | Medium | High | Phase 1 data cleanup, ongoing validation |
| Low user adoption | Medium | High | Training program, quick wins focus, change management |
| Model accuracy | Low | Medium | Historical validation, continuous learning |
| Integration complexity | Low | Medium | Phased approach, proven tech stack |
| Market conditions | Medium | Medium | Sensitivity analysis, adaptive models |

### Decision Gates

**Gate 1 (End of Phase 1):**
- Is CRM data quality >80%?
- Are all customers scored?
- Is inventory tracking operational?
→ Decision: Proceed to Phase 2 / Remediate

**Gate 2 (End of Phase 2):**
- Are AI models meeting accuracy targets?
- Is GP tracking operational?
- Is sales team engaged?
→ Decision: Proceed to Phase 3 / Adjust approach

**Gate 3 (End of Phase 3):**
- Is measurable GP improvement achieved?
- Is AI adoption >60%?
- Are KPIs trending toward targets?
→ Decision: Scale and optimize / Course correct

---

## Conclusion

This AI-powered Sales CRM integration with GP Guardian represents a transformational opportunity for WWGiles to move from reactive, volume-focused sales to proactive, profit-optimized operations. By tracking the complete Source-to-Paid lifecycle and using AI to match inventory to the right customers at the right time, WWGiles can:

1. **Protect and grow margins** from 10.5% to 22%
2. **Reduce working capital requirements** by accelerating cash conversion
3. **Build sustainable competitive advantage** through data-driven operations
4. **Create the foundation** for scalable SaaS platform development

The investment of £92,000 is expected to generate £705,000 in annual benefits, with payback in approximately 8 weeks. This positions WWGiles not just as a more profitable business, but as a potential design partner for industry-wide transformation.

---

*Document Version: 1.0*
*Last Updated: December 2025*
*Classification: Strategic - Internal*
