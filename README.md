# Consumer Lending: From Loan to Trusted Number, and Where AI Fits

Part of the **AI-Assisted Domain Reviews** series: a repeatable way to build fast, credible fluency in an unfamiliar business domain, find where AI can realistically change its economics, and work out what governing that data and AI actually requires.

This entry unwinds **consumer lending data for reporting**: how a loan's data travels from application to the financial statements, how the bank proves those numbers are right, how it governs the data behind them, where AI helps, and how to model and implement it all on a modern data platform.

> **Nine decks · 213 slides.** Each deck stands alone and is written for mixed audiences: senior business leaders, data management professionals and architects. All examples are illustrative mock-ups of a mid-size US bank. They are not a specific production design.

---

## Why this matters to executives

Every number a bank reports is signed by an executive: loan balances, past-due amounts, the loss allowance, the regulatory filings. That signature is only as safe as the data behind it. The data passes through at least seven systems between the customer's application and the published report, and changes shape at every step.

This series answers the questions a leader should be able to ask:

1. **Where does the number come from?** The data flow, and how the books close.
2. **Who is accountable for it, and by what rules?** Governance, policies and the governance office.
3. **How do we know it's right?** Data quality checks, and how AI can scale them.
4. **How do we build a platform that makes all of this routine?** The data model and the implementation blueprint.

---

## The pattern

Like every domain in this series, Consumer Lending is unwound in three passes:

1. **Mechanics.** Map the end-to-end process: who does what, what data moves, and what the accounting looks like at each step.
2. **Governance and control.** Pair every hand-off with ownership, definitions, quality rules and controls, so the numbers can be trusted and signed.
3. **AI opportunity.** Identify where AI changes the cost, speed or reach of the work, specifically. Every AI capability ships with its control obligations.

Consumer Lending extends the pattern with a fourth pass: **build.** A complete reporting data model and a blueprint for implementing it at a real client, one use case at a time.

---

## Deliverables and suggested reading order

| # | Deck | Slides | The question it answers |
|---|---|---|---|
| **Part 1 · Understand the flow** ||||
| 1 | [`Consumer_Lending_Data_Flow_Overview.pptx`](./Consumer_Lending_Data_Flow_Overview.pptx) | 17 | How does a loan's data travel from application to the financial statements? |
| 2 | [`Subledger_to_GL_Reconciliation.pptx`](./Subledger_to_GL_Reconciliation.pptx) | 13 | How do loan-level records become the official books, and how are they proven to agree? |
| **Part 2 · Govern it** ||||
| 3 | [`Consumer_Lending_Data_Governance.pptx`](./Consumer_Lending_Data_Governance.pptx) | 18 | What makes lending data trustworthy enough to sign? |
| 4 | [`Data_Governance_Policies_Executive_Overview.pptx`](./Data_Governance_Policies_Executive_Overview.pptx) | 23 | What rules does the firm set, and how are they enforced? |
| 5 | [`Establishing_a_Data_Governance_Office.pptx`](./Establishing_a_Data_Governance_Office.pptx) | 27 | What organization runs governance, and how is it stood up? |
| **Part 3 · Make it trustworthy, at scale** ||||
| 6 | [`Consumer_Lending_Data_Quality_Checks.pptx`](./Consumer_Lending_Data_Quality_Checks.pptx) | 17 | What checks prove the data is right, and where should they run? |
| 7 | [`AI_for_Data_Quality_Operations.pptx`](./AI_for_Data_Quality_Operations.pptx) | 34 | Where can AI make data quality faster and wider-reaching, safely? |
| **Part 4 · Build it** ||||
| 8 | [`Consumer_Lending_Medallion_Data_Model.pptx`](./Consumer_Lending_Medallion_Data_Model.pptx) | 40 | What data model serves all the reporting, from raw source to certified report? |
| 9 | [`Claude_Client_Data_Model_Implementation_Blueprint.pptx`](./Claude_Client_Data_Model_Implementation_Blueprint.pptx) | 24 | How would we implement that model at a client, with AI assistance, safely? |

---

## The decks, summarized

### 1 · Consumer Lending Data Flow for Reporting
**The big picture.** A loan's data passes through **seven stages in three zones**:
- **Operational:** origination and decisioning, loan boarding, loan servicing.
- **Accounting:** the subledger, the GL mapping layer, the GL accounting engine.
- **Reporting:** financial reporting.

The deck walks each stage: what happens there, what data it creates, and which systems are involved. It then follows **one loan through the whole flow**. It shows what each regulatory filing and management metric needs, and marks where breaks usually start: unmapped transaction codes, failed interface files, timing differences, and manual adjustments without support.

**Executive takeaway:** detail collapses at every hand-off, from individual loans to accounting entries to totals. Trust in the final number therefore depends on reconciliation and controlled mappings at each step.

### 2 · Subledger → Journal Entry → General Ledger
**How the books close.** A plain-language walk through the record-to-report cycle:
1. The daily posting cycle: subledger → accounting engine → journal entries → general ledger.
2. The period-end close: trial balance → adjusting entries → financial statements.

The deck covers daily subledger-to-GL reconciliation (and what to investigate when it doesn't balance), the Group Controller's oversight role, and the five links that must hold for the statements to be trustworthy.

**Executive takeaway:** every link in the chain is a control point. Daily reconciliation prevents month-end surprises.

### 3 · Data Governance for Consumer Lending Reporting
**Making numbers signable.** A governance framework of **seven disciplines**, resting on policy, people and technology:
- critical data elements (CDEs)
- lineage
- data quality
- controls and reconciliation
- metadata and glossary
- issue management
- KPI measurement

It includes an operating model (owners, stewards, custodians), **ten example lending CDEs** with the reports that depend on each, and lineage traced from a Call Report number back to source. It also covers key controls at each hand-off, a governance scorecard, a reference architecture, a RACI and a three-phase roadmap.

**Executive takeaway:** fund governance by risk. Filings and financial statements come first, and leaders should ask for the scorecard, not anecdotes.

### 4 · Data Governance Policies: Executive Overview
**The rules of the road.** How policies, standards, procedures and guidelines relate. The framework is **one umbrella Data Governance Policy plus seventeen supporting policies in five families**:
- **Manage:** quality, CDEs, metadata, lineage, reference data.
- **Protect:** classification, access, privacy, retention.
- **Use:** models and AI, spreadsheets, regulatory reporting, data sharing.
- **Operate:** issues, change management, exceptions.
- **Oversee:** monitoring and compliance.

The deck covers who does what, the policy lifecycle, exceptions handled openly, and how compliance is measured. It traces **one data element (days past due) through every policy**. Five appendices provide finished example documents: a policy, a standard, two procedures and a guideline.

**Executive takeaway:** good policy doesn't make governance bureaucratic. It makes accountability clear. Start with the minimum set that protects regulatory reporting.

### 5 · Establishing a Data Governance Office
**Who runs it.** A practical guide to standing up a Data Governance Office (DGO):
- **Structure:** mission and mandate, guiding principles, what the office owns and what it doesn't, where it should sit, and three operating models (centralized, federated, hub-and-spoke).
- **People:** forums, roles, a capability model with maturity signals, sizing and staffing.
- **Tooling:** a tooling reference architecture with the data catalog as the hub, and how to sequence tool selection.
- **Governance of the office:** two RACIs, a maturity assessment, and success measures across five lenses.
- **Delivery:** a roadmap from charter (first 90 days) to proving value (3–12 months) to scale (12–24 months), and the decisions needed from leadership.

**Executive takeaway:** start with one domain and one painful problem, prove value, then scale. Governance works when the business owns its data and leaders can see results every month.

### 6 · Data Quality Checks in Consumer Lending
**How data is proven right.**
- **The anatomy of a check:** a rule, plus a threshold, severity, owner and action on failure.
- **Four check catalogs:** record-level, business-rule, cross-system, and timeliness, volume and anomaly.
- **Complex logic:** checks for filters, joins and transformations.
- **Worked SQL examples:** reconciliation, uniqueness, referential integrity and more.
- **Where checks run:** "shift left", catching problems as early as possible, with hard (blocking) versus soft (warning) checks.
- **Scoring:** a DQ score by criticality tier.
- **Practice:** failure handling, best practices and pitfalls.

**Executive takeaway:** good data quality isn't the absence of errors. It's knowing about them first and fixing them where they start.

### 7 · AI for Data Quality Operations
**Where AI helps, and what keeps it safe.** The deck compares **four kinds of automation**: rules, machine learning, generative AI and agentic AI. It shows how to measure data health, and where AI fits in the data quality lifecycle:
- anomaly detection
- alert triage
- root-cause analysis
- remediation
- auto-generating rules and controls, with a worked example for days past due

It defines **autonomy levels L1–L4**. The default is L2, "recommend, a human approves", for anything touching critical data. It adds a controls framework, model-risk validation, ways to measure whether the AI works, a reference architecture, a RACI, **ten best practices**, common pitfalls, and a three-phase roadmap (observe → assist → act). Appendices explain every technical term in plain language.

**Executive takeaway:** AI makes data quality operations faster and wider-reaching. Controls make it trustworthy, and governance makes it possible.

### 8 · Consumer Lending Medallion Data Model
**The data model behind all of it.** A complete Bronze → Silver → Gold reporting model:

| Scope | Count |
|---|---|
| Source systems | **11**: origination, credit bureaus, customer master, servicing, card platform, payments, collections, collateral valuation, CECL engine, general ledger, reference data |
| Bronze tables (raw, as received) | **23** |
| Silver tables (cleansed, integrated) | **22** |
| Gold tables (certified, report-ready) | **13**: 4 facts, 8 dimensions, 1 bridge |
| Reporting use cases | **10**: portfolio performance, delinquency, CECL losses, exposure (EAD), Call Report RC-C/RC-N/RC-L, HMDA/fair lending, origination funnel, vintage, collections, GL tie-out |

The deck combines **two lenses**:
- the **lifecycle lens**: origination through servicing
- the **exposure lens**, integrated from a separate credit-warehouse schema: facilities, credit limits, exposure at default, funded and unfunded loss allowance

It shows which lens each use case needs, and the naming rules that give every attribute exactly one home. It includes:
- **Diagrams:** entity-relationship diagrams with primary and foreign keys and cardinality spelled out, plus a relationship catalog.
- **Dictionary:** a column-by-column data dictionary giving definition, type, source and data classification.
- **Lineage:** at table and column level, with three report numbers traced end to end.
- **Data quality:** checks built into each layer.

**Executive takeaway:** every reported number traces to one certified dataset and back to a named source system. That gives one version of balance, exposure, delinquency and loss.

### 9 · Implementing the Medallion Data Model with Claude
**How to build it at a client.** A platform-neutral blueprint:
- **Delivery in vertical slices:** each use case is built end to end, starting with an easy proof of concept (the origination funnel) and growing continuously.
- **An 8-step gated lifecycle per slice:** scope, discover, design, build, test, deploy, operate, document.
- **Gold certification:** objects are formally certified as **fit for a named purpose**.
- **Rollback at every level:** design, build, release and certification.

It also covers **how to use AI safely on a client engagement**:
- which Claude account types keep client data and firm IP protected
- sharing only metadata, code and aggregates, never customer records
- which AI model suits which task
- an honest comparison with Microsoft Copilot, ChatGPT and Gemini

**Executive takeaway:** start small, certify every Gold object for a named use, keep client material in a client-controlled account, and version everything so every step is reversible.

---

## One thread through every deck: Days Past Due

Following a single data element, **Days Past Due (DPD)**, shows how the nine decks connect:

| Deck | What happens to DPD |
|---|---|
| Data Flow | Created in **loan servicing** when a payment is missed; drives delinquency status and past-due reporting |
| Subledger → GL | Charge-offs and interest on late loans post as journal entries that must reconcile to the GL |
| Governance | Designated a **tier-1 critical data element**, with an owner, a definition, lineage and quality rules |
| Policies | Traced through **every policy**: owner, definition, 99.9% quality threshold, lineage, access, change control |
| DQ Checks | Validity and consistency checks; a weekly **DQ score tracked against its threshold** |
| AI for DQ Ops | Worked example: **AI drafts DPD quality rules**, which people back-test and approve |
| Data Model | Modeled in Silver (`loan_balance_daily`), bucketed in Gold (`dim_delinquency_status`), traced to **Call Report RC-N** |
| Blueprint | Built and **certified** in an early slice (delinquency and roll rates) before any regulatory use |

---

## Themes across the series

- **Every hand-off is a control point.** Reconciliation, lineage and controlled mappings are what make a number signable.
- **Accountability before technology.** Owners, definitions and policies come first; tools make them routine.
- **Start where the risk is.** Regulatory filings and financial statements first, then expand.
- **Measure, don't assert.** Scorecards, thresholds and trends replace anecdotes.
- **AI adds reach, not authority.** AI detects, drafts and summarizes; people approve, certify and sign.
- **Build it in, don't bolt it on.** Quality checks, lineage and certification live inside the data platform.

---

## Key terms, in plain language

| Term | Meaning |
|---|---|
| **GL (general ledger)** | The bank's official books; the source of the financial statements |
| **Subledger** | The detailed, loan-by-loan accounting record that rolls up into the GL |
| **CDE (critical data element)** | One of the few data points that matter most, e.g., principal balance or days past due |
| **Data lineage** | The documented path a number takes from source system to report |
| **DPD (days past due)** | How late the oldest unpaid payment is |
| **CECL** | Current Expected Credit Loss: the accounting standard for the loan loss allowance |
| **EAD (exposure at default)** | Drawn balance plus the part of an unused credit line expected to be drawn |
| **Call Report (RC-C, RC-N, RC-L)** | Quarterly regulatory filing: loans by type, past-due loans, unused commitments |
| **HMDA** | Home Mortgage Disclosure Act: public reporting used to assess fair lending |
| **Medallion architecture** | Layering data as Bronze (raw), Silver (cleansed and integrated) and Gold (certified, report-ready) |
| **RACI** | Who is Responsible, Accountable, Consulted and Informed for each activity |

---

## How this was built

Built conversationally with **Claude (via Claude Code)**. The domain mechanics, governance design, data model and AI analysis were developed through iterative Q&A, then generated directly as PowerPoint decks with `python-pptx`, using one shared visual system so the set reads as a series. Decks were checked for structure and rendered for visual review before publishing. There was no manual slide-building: each deck is produced by a script from the analysis, so it can be regenerated and extended consistently.

---

## Where this fits in the repository

```
AI-Assisted-Domain-Reviews-for-AI-Opportunities/
├── Card-Overview/                 ← first domain: card transaction lifecycle
└── Consumer-Lending-Overview/             ← this entry
    ├── README.md
    ├── Consumer_Lending_Data_Flow_Overview.pptx
    ├── Subledger_to_GL_Reconciliation.pptx
    ├── Consumer_Lending_Data_Governance.pptx
    ├── Data_Governance_Policies_Executive_Overview.pptx
    ├── Establishing_a_Data_Governance_Office.pptx
    ├── Consumer_Lending_Data_Quality_Checks.pptx
    ├── AI_for_Data_Quality_Operations.pptx
    ├── Consumer_Lending_Medallion_Data_Model.pptx
    └── Claude_Client_Data_Model_Implementation_Blueprint.pptx
```

## What's next

Future domains follow the same passes: mechanics, governance and control, AI opportunity, and, where it adds value, a build-ready data model and implementation blueprint.
