# From Internal Tool to SaaS Product

## The Business Problem

An enterprise-scale renewable fleet analytics platform (GenE + OpsReport) had been built and adopted internally: 700+ sites, 300+ daily active users, system of record for $2.4B in annual generation revenue. The platform solved a problem every renewable asset owner faces: classifying why generation fell below expectations and connecting those classifications to financial accountability.

**The strategic question:** How do you turn a cost-center internal tool into an external revenue-generating business?

## My Role

Senior Product Manager. I identified this opportunity, built the business case, defined the external product strategy, and drove the initial GTM framework. This was not assigned to me. I saw the market gap and made the case.

## The Market Opportunity

Every renewable energy operator faces the same problem:
- Generation assets underperform their theoretical output
- The gap between expected and actual generation represents lost revenue
- Classifying why losses occur determines the financial and operational response
- Most operators rely on spreadsheets, consultants, or generic BI tools

Our platform already does this at scale: 10,000+ per-device ML models, automated loss classification, month-end close workflows, curtailment tracking with financial attribution. The technology exists. The question was whether the product, market, and business model aligned.

**Market signals:** Third-party asset owners, IPPs, and YieldCos manage renewable portfolios without engineering resources to build this capability in-house. The asset performance management software market lacks solutions with this depth of ML-driven classification. A Google Cloud partnership from our GCP migration created co-selling alignment.

## The Business Case

| Component | Approach |
|-----------|---------|
| **Pricing** | Per-site subscription, tiered by capacity (MW) |
| **Target market** | Mid-size IPPs and YieldCos (50-500 site portfolios) |
| **Entry point** | Solar fleet classification + dashboards |
| **Expansion** | Wind, curtailment analytics, month-end close, DTE management |
| **Delivery** | Multi-tenant SaaS on GCP |

## The Key Decisions

### 1. Solar first, then wind

Solar classification is more standardized across operators (similar inverter types, similar loss categories). Wind has more site-specific variation. Starting with solar reduces customization burden while we learn the external product motion.

### 2. Platform, not consulting

Consulting doesn't scale and creates a per-customer cost floor. The platform runs continuously and automatically. SaaS means the marginal cost of each new customer is configuration, not custom analysis. This is the difference between a service business and a product business.

### 3. Google Cloud GTM partnership

Google has existing energy company relationships and an active co-selling program. Being a GCP-native energy analytics SaaS aligns with their GTM motion and potentially unlocks co-marketing budget. The GCP migration was already justified on $96K/yr cost savings. SaaS revenue is additional upside.

### 4. Same codebase, not a fork

A forked codebase means maintaining two products with the same core logic. Multi-tenancy, access controls, and configuration already exist for internal use. External customers get the same product with a different tenant configuration. This keeps engineering velocity high and prevents the internal-vs-external feature divergence that kills platform products.

## Preconditions I Validated

| Requirement | Status |
|------------|--------|
| Multi-tenant data isolation | Already built for internal business unit separation |
| Self-service site onboarding | Partially automated, needs UI investment |
| Cloud-native hosting | GCP migration underway |
| Configurable operational assumptions | Framework exists, needs external admin UI |
| Value-based pricing model | Requires market validation |
| Scalable support model | Requires self-serve docs and tiered support |

## Risk Management

| Risk | How I Addressed It |
|------|-------------------|
| **IP exposure** | Positioned as "monetizing an existing asset." The algorithms are the value, not the implementation. |
| **Support burden** | Tiered model: self-serve + community (base), dedicated CSM (enterprise). |
| **Data sensitivity** | Multi-tenant architecture with strict isolation. Added encryption and audit requirements. |
| **Cannibalization fear** | Our advantage is operating assets, not monitoring software. Industry transparency benefits the largest operator. |

## What This Demonstrates

**This is the strongest Principal PM signal in the portfolio.**

A Senior PM ships features. A Principal PM creates businesses. Identifying that an internal operations tool could become an external revenue stream, building the business case, defining the product strategy, and driving it forward is a fundamentally different kind of product work.

The decision touches every dimension of company strategy:
- **Revenue**: new line of business for a Fortune 200 company
- **Cloud strategy**: justifies GCP migration beyond internal cost savings
- **Competitive positioning**: transforms a cost center into a market-facing product
- **Partnership**: creates Google co-selling opportunity
- **Talent**: "we build products that compete in the market" is a stronger recruiting pitch than "we build internal tools"

The multi-tenant architecture, configurable framework, and GCP migration were originally justified on internal grounds. They also happen to be exactly what's needed for SaaS. Whether that's foresight or fortunate design, the architecture supports the business model transition without re-engineering.
