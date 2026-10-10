# Case Study: From Internal Tool to SaaS Product

## Context

An enterprise-scale renewable fleet analytics platform (GenE + OpsReport) had been built and adopted internally — 700+ sites, 300+ daily active users, system of record for $2.4B in annual generation revenue. The platform solved a problem that every renewable asset owner faces: classifying why generation fell below expectations and connecting those classifications to financial accountability.

The question: could this become an external product?

## My Role

Senior Product Manager — I identified the commercialization opportunity, built the business case, defined the product strategy for external customers, and drove the initial GTM framework. This was not assigned to me — I saw the opportunity and made the case.

## The Opportunity

### Why This Product Has External Value

Every renewable energy operator — not just our company — faces the same problem:
- Solar and wind assets underperform their theoretical output
- The gap between expected and actual generation represents lost revenue
- Classifying why losses occurred (curtailment, equipment fault, degradation, soiling, weather) determines the financial and operational response
- Most operators rely on spreadsheets, manual analysis, or expensive consultants to do this

Our platform already does this at scale: 10,000+ per-device ML models, automated loss classification, month-end close workflows, curtailment tracking with financial attribution. The technology exists. The question was whether the product could be packaged for external customers.

### Market Signal

- Third-party asset owners, IPPs (Independent Power Producers), and YieldCos manage renewable portfolios without the engineering resources to build this capability in-house
- Existing solutions are either (a) expensive consulting engagements that produce point-in-time reports or (b) generic BI tools that require heavy customization
- The asset performance management software market is growing but lacks solutions with our depth of ML-driven classification
- Google Cloud partnership (from GCP migration) created GTM alignment and co-selling opportunities

## The Business Case I Built

### Revenue Model

| Component | Approach |
|-----------|---------|
| **Pricing** | Per-site subscription, tiered by site capacity (MW) |
| **Target market** | Mid-size IPPs and YieldCos (50-500 site portfolios) |
| **Entry point** | Solar fleet classification + OpsReport dashboards |
| **Expansion** | Wind classification, curtailment analytics, month-end close, DTE management |
| **Delivery** | Multi-tenant SaaS on GCP (leveraging the migration already in progress) |

### Value Proposition to External Customers

"You're leaving money on the table every day your fleet operates without automated loss classification. Our platform processes billions of telemetry data points across your entire portfolio and tells you exactly where generation is being lost, why, and what it's worth — automatically, continuously, and at a granularity your current tools can't match."

### What Had to Be True

For commercialization to work, several conditions needed to be met:

1. **Multi-tenancy** — Data isolation between customers, configurable per-tenant. (Already built for internal business unit separation.)
2. **Self-service onboarding** — New sites provisioned without custom engineering. (Partially exists — site configuration is semi-automated.)
3. **GCP hosting** — Enterprise SaaS customers expect cloud-native. (Migration already underway.)
4. **Configurable OpAs** — Each customer's operational assumptions differ. (Framework exists; needs UI for external admin.)
5. **Pricing model** — Value-based pricing tied to fleet size and recovered revenue. (New; required market research.)
6. **Support model** — Cannot scale support with the internal team. (Requires self-serve documentation, tiered support.)

## Key Decisions

### Start with Solar, Expand to Wind

**Decision:** Launch with solar classification first, then add wind.

**Rationale:** Solar classification is more standardized across operators (similar inverter types, similar loss categories). Wind has more site-specific variation (turbine OEMs, terrain effects, curtailment signal differences). Starting with solar reduces customization burden for early customers while we learn the external product motion.

### Platform Play, Not Consulting Play

**Decision:** Sell the platform (SaaS subscription), not analysis services (consulting engagements).

**Rationale:** Consulting doesn't scale and creates a per-customer cost floor. The platform's value is that it runs continuously and automatically. Packaging it as SaaS means the marginal cost of each new customer is configuration, not custom analysis. This is the difference between a service business and a product business.

### Leverage Google GTM

**Decision:** Align the SaaS launch with the Google Cloud partnership from the GCP migration.

**Rationale:** Google has existing relationships with energy companies and an active co-selling program. Being a GCP-native energy analytics SaaS aligns us with their GTM motion, provides marketplace visibility, and potentially unlocks co-marketing budget. The GCP migration was already justified on cost savings ($96K/yr) — SaaS revenue is an additional upside.

### Don't Fork the Codebase

**Decision:** Build external features on the same codebase as the internal product, not as a separate product.

**Rationale:** A forked codebase means maintaining two products with the same core logic. Multi-tenancy, access controls, and configuration already exist for internal use. External customers get the same product with a different tenant configuration. This keeps engineering velocity high and prevents the "internal vs. external" feature divergence that kills platform products.

## Challenges & Risks

| Challenge | How I Addressed It |
|----------|-------------------|
| **IP concerns** — Is the company willing to expose internal capability externally? | Built the business case showing revenue potential. Positioned as "monetizing an existing asset" not "giving away secrets." The algorithms are the value, not the implementation details. |
| **Support burden** — Internal users have direct access to the engineering team. External users can't. | Proposed tiered support model: self-serve docs + community for base tier, dedicated CSM for enterprise tier. Required investment in documentation and monitoring. |
| **Data sensitivity** — External customers' generation data is commercially sensitive. | Multi-tenant architecture with strict data isolation already exists. Added tenant-level encryption and audit logging requirements to the roadmap. |
| **Regulatory** — Some generation data may have contractual restrictions on third-party hosting. | Proposed compliance review as a gating milestone before external launch. Identified customer contract templates that address data hosting. |
| **Cannibalization fear** — "If competitors use our tool, does it reduce our competitive advantage?" | Our advantage is in operating the assets, not in the monitoring software. Better fleet analytics across the industry actually increases market transparency, which benefits the largest operator. |

## What This Demonstrates

### Business Model Innovation
This is the single strongest "Principal PM" signal in my portfolio. A Senior PM ships features. A Principal PM creates businesses. Identifying that an internal operations tool could become an external revenue stream — and building the case for it — is a fundamentally different kind of product thinking.

### Strategic Thinking at Company Level
The decision to commercialize touches:
- **Revenue** — new revenue line for a Fortune 200 company
- **Cloud strategy** — justifies GCP migration beyond internal cost savings
- **Competitive positioning** — transforms a cost center into a market-facing product
- **Partnership** — creates Google co-selling opportunity
- **Talent** — "we build products that compete in the market" is a stronger recruiting pitch than "we build internal tools"

### Architecture Foresight
The multi-tenant architecture, configurable OpAs framework, and GCP migration were originally justified on internal grounds. But they're also exactly what's needed for SaaS commercialization. Whether this was foresight or fortunate design, the architecture supports the business model transition without re-engineering.

## Current Status

The business case has been built and presented. The GCP migration (a prerequisite) is in progress. The multi-tenant architecture is proven internally. The next milestones are:
1. Complete GCP migration for GenE core platform
2. Build self-service site onboarding
3. Define external pricing model with market validation
4. Compliance review for data hosting
5. Pilot with 1-2 external customers (lighthouse accounts)

## Lessons

1. **Look for the SaaS inside every internal tool.** If you built something that solves a problem unique to your company, it's an internal tool. If you built something that solves an industry-wide problem, it might be a business.

2. **Architecture decisions compound.** Multi-tenancy, configurability, and cloud-native hosting were built for internal reasons. They created an option for commercialization that would have cost millions to retrofit.

3. **The PM who identifies the opportunity is the PM who should own it.** Don't wait for leadership to notice. Build the case, present the thesis, and ask for the mandate. That's how Senior PMs become Principal PMs.
