# Awesome-SaaS-Subscription-Financial-Analytics

# Awesome SaaS & Subscription Financial Analytics

> A curated list of top SaaS and Subscription Financial Analytics platforms — both SaaS/Hosted commercial solutions and open-source alternatives for tracking MRR, churn, LTV, and the financial health of recurring-revenue businesses.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [ChartMogul](#chartmogul)
  - [Baremetrics](#baremetrics)
  - [ProfitWell Metrics](#profitwell-metrics)
  - [Chargebee Analytics](#chargebee-analytics)
  - [Stripe Sigma](#stripe-sigma)
  - [Maxio Insights](#maxio-insights)
- [Open-Source Software](#-open-source-software)
  - [saas-metrics](#saas-metrics)
  - [ChurnLens](#churnlens)
  - [Powernode Platform](#powernode-platform)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted SaaS and Subscription Financial Analytics platforms. These are not open-source but are included as reference points for feature comparison.

### ChartMogul
**Type:** Subscription analytics and CRM with standardized SaaS metrics  
ChartMogul connects to billing systems and consolidates subscription revenue, product usage, and marketing data into one platform, standardizing how metrics are calculated so every team works from the same numbers [citation:4]. Built-in reports cover MRR movements, churn, customer lifetime value, cohort retention, and more, with custom dashboards and the ability to send metrics to Slack, HubSpot, or data warehouses like Snowflake and BigQuery [citation:4]. It also functions as a CRM, giving sales and success teams a revenue-aware view of customers. Pricing scales with tracked revenue rather than seats, with a free tier for smaller ARR [citation:5].  
**Best for:** Teams wanting standardized SaaS metrics without manual reconciliation, particularly those needing to push trusted data into existing tools.

### Baremetrics
**Type:** Subscription analytics with payment recovery add-ons  
Baremetrics tracks over 28 subscription metrics including MRR, ARR, churn, upgrades, and downgrades, priced on tracked revenue rather than per seat [citation:5]. The free tier covers up to $180K ARR, with paid plans scaling to $409/month for larger businesses [citation:5]. Optional add-ons include **Payment Recovery** ($129/month or 10% of recovered revenue) and **Cancellation Insights** ($129/month) for churn feedback collection [citation:5]. The platform is known for its clean dashboards and accessible pricing for early-stage SaaS.  
**Best for:** Founders and finance teams wanting core subscription analytics with an accessible entry price and optional recovery tooling.

### ProfitWell Metrics
**Type:** Free subscription analytics with benchmarking  
ProfitWell Metrics is **free forever, regardless of business size**, offering growth, revenue, retention, and churn trends, unit economics, cohorts, and benchmarks from 15,000+ subscription companies [citation:6]. Setup is quick (5 minutes), with native integrations and APIs, enrichment via Clearbit and FullContact, and a mobile app with intelligent alerting [citation:6]. Paid add-ons include Retain (churn recovery), Recognized (revenue recognition), and Price Intelligently (pricing strategy) [citation:6]. The free tier makes it uniquely accessible for SaaS businesses at any stage.  
**Best for:** SaaS businesses wanting comprehensive free analytics with industry benchmarks, accepting that advanced recovery and recognition capabilities are paid add-ons.

### Chargebee Analytics
**Type:** Billing-native subscription analytics and reporting  
Chargebee's Analytics module provides 360° visibility into subscription health, with reports covering MRR movements, churn, trial conversion, deferred revenue, and custom cohort analysis [citation:3][citation:11]. The **Reports Explorer** provides instant access to predefined reports from acquisition to churn, while custom reports can be built without code using Chargebee's data sources [citation:11]. Churn alerts notify teams when rates exceed thresholds, and trial analytics track conversion from free to paid [citation:3]. Revenue recognition reports support GAAP-compliant analysis of recurring and non-recurring streams [citation:11].  
**Best for:** Existing Chargebee customers wanting analytics native to their billing data without a separate analytics vendor.

### Stripe Sigma
**Type:** SQL-based analytics layer within Stripe  
Stripe Sigma is a SQL-powered analytics layer built into the Stripe Dashboard, enabling custom queries against live payment and billing data [citation:7]. It includes pre-built templates for common SaaS questions (MRR trends, active subscriptions, churned customers, failed payments) and an **AI Assistant** that generates SQL from plain English [citation:7]. Sigma allows unlimited customization without fixed dashboards, with a 30-day free trial before paid subscription [citation:7]. **Trade-off:** Requires SQL knowledge for non-template queries, and it is limited to Stripe data only.  
**Best for:** Stripe-native businesses with SQL capability wanting maximum flexibility and no separate analytics vendor.

### Maxio Insights
**Type:** AI-powered financial analyst agents for billing data  
Maxio's AI agents include a **Financial Analyst** that explains ARR bridges, KPI deltas, and billing mix, tracing anomalies to their source [citation:8]. A **Pricing Analyst** correlates discounts against churn and measures tier performance, while a **Close Readiness** agent checks quote-to-cash blockers and logs clearances for audit [citation:8]. These agents work from unified billing, payments, revenue, and usage data, learning from approval/rejection feedback.  
**Best for:** Finance teams wanting AI-assisted explanation of revenue movements and close readiness, particularly within the Maxio billing ecosystem.

---

## 🟩 Open-Source Software

Self-hosted, community-driven SaaS and Subscription Financial Analytics tools. The open-source ecosystem is **early-stage**—available projects focus on metric calculation from CSV exports rather than full analytics platforms.

### saas-metrics
**Stack:** Python / Excel | **License:** Open Source (per PyPI)  
saas-metrics is an open reference implementation for computing SaaS revenue metrics from a raw billing export, with **written, tested definitions** for every metric [citation:10]. Key features include:
- A **revenue waterfall** exact to the cent (New, Reactivation, Expansion, Contraction, Churn)
- Net and gross revenue retention, logo churn, quick ratio, and ARR
- Cohort triangles, concentration, and tier migration
- **Service-period spreading** for annual/multi-month invoices (correcting the common error of counting invoices in the month billed)
- An **Excel workbook where every metric is a live formula** you can audit, with a Checks tab proving it matches the engine [citation:10]

It reads Stripe, Chargebee, ERP, or spreadsheet exports with column mapping. Pre-flight checks block errors (missing columns, unparseable dates) and warn on issues like periods with no billing [citation:10].  
**Best for:** Finance teams and developers wanting auditable, transparent SaaS metrics from their own billing data, with Excel output for stakeholder review.

### ChurnLens
**Stack:** Python / Docker | **License:** Source-available (per GitHub)  
ChurnLens is a self-hosted tool that calculates MRR, customer churn rate, and LTV from a CSV file listing subscription sign-ups, upgrades, cancellations, and plan changes . It produces month-by-month breakdowns of revenue growth or shrinkage, running entirely on your own computer or server with no account, third-party service, or monthly fee . Single-purpose and scriptable, it outputs in table, JSON, or SARIF formats and can gate CI on findings . Available as source-available (not OSI-approved) with ports in Python, JavaScript, Go, and Rust.  
**Best for:** Founders and finance teams wanting a simple, self-hosted CSV-based metric calculator without a SaaS subscription, accepting source-available licensing.

### Powernode Platform
**Stack:** Rails 8 / React / PostgreSQL / Stripe / PayPal | **License:** Open Source (per GitHub)  
Powernode is a full-stack subscription management platform with **MRR/ARR calculations, churn analysis, and customer insights** built in . It includes Stripe and PayPal integration with PCI compliance, JWT authentication, background job processing via Sidekiq, and a React dashboard with charts . The platform claims 100% test coverage across 628+ tests and is described as production-ready . **Trade-off:** It is a subscription platform rather than a standalone analytics tool—analytics are one feature within a broader billing system.  
**Best for:** Teams wanting an open-source subscription platform with built-in financial analytics, accepting a more comprehensive (and heavier) stack than a pure analytics tool.

---

## 📊 Comparison at a Glance

| Software | License | Stack | MRR/Churn | Excel Export | Self-Hosted | Best For |
|----------|---------|-------|-----------|--------------|-------------|----------|
| **ChartMogul** | Proprietary | Cloud | ✅ Standardized | (Check) | ❌ | Cross-system metric consistency |
| **Baremetrics** | Proprietary | Cloud | ✅ 28+ metrics | (Check) | ❌ | Accessible core analytics |
| **ProfitWell** | Proprietary | Cloud | ✅ Free forever | (Check) | ❌ | Free + benchmarks |
| **Chargebee** | Proprietary | Cloud | ✅ Billing-native | (Check) | ❌ | Existing Chargebee users |
| **Stripe Sigma** | Proprietary | Cloud | ✅ SQL custom | (Check) | ❌ | Stripe-native SQL flexibility |
| **saas-metrics** | Open Source | Python/Excel | ✅ Auditable | ✅ Live formulas | ✅ | Transparent metric definitions |
| **ChurnLens** | Source-available | Python | ✅ CSV-based | ❌ | ✅ | Simple self-hosted calculator |
| **Powernode** | Open Source | Rails/React | ✅ Built-in | ❌ | ✅ | Subscription platform + analytics |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source SaaS or Subscription Financial Analytics tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source (or clearly note if it is source-available but not OSI-approved, as with ChurnLens). Note that the open-source ecosystem for **dedicated SaaS financial analytics** is **very limited**. **saas-metrics** is the most rigorous open-source effort, providing tested metric definitions and an auditable Excel workbook [citation:10]. **ChurnLens** offers a simpler CSV-based approach , while **Powernode** embeds analytics within a full subscription platform . Commercial platforms like ChartMogul and ProfitWell remain significantly more capable for multi-source metric standardization, benchmarking, and workflow integration.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
