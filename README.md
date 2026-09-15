# # Using AI to unwind, clarify, and structure complex business and technical domains and outline AI opportunities.


Part of an ongoing **Domain Unwind** series — a repeatable pattern for building fast, credible fluency in an unfamiliar business domain, then identifying where AI can realistically change its economics, and what governing that AI actually requires.

This entry unwinds the **card transaction lifecycle**: authorization, settlement/clearing, interchange & network fees, chargebacks/disputes, and issuer-side reporting & GL accounting.

## The pattern

Every domain in this series is unwound in three passes:

1. **Mechanics** — map the end-to-end process stage by stage: who does what, what data moves, what the accounting/economics look like at each hop.
2. **AI opportunity** — for each stage, ask where AI plausibly changes the cost, speed, or accuracy of that step — and be specific about the mechanism, not just "AI could help here."
3. **Governance** — pair every opportunity with its risk and control counterpart, and go one level deeper: which controls are *themselves* AI-driven, what AI capability powers them (RAG, classification, anomaly detection, XAI, NLP/NER), and which piece stays a human-owned gate.

Each pass ships as its own deck so the mechanics, the opportunity case, and the control story can be read (and challenged) independently.

## Deliverables

| File | What it covers |
|---|---|
| [`AI_Card_Lifecycle_Opportunities.pptx`](./AI_Card_Lifecycle_Opportunities.pptx) | Stage-by-stage map of where AI creates efficiency across the card lifecycle |
| [`Card_AI_Governance_Considerations.pptx`](./Card_AI_Governance_Considerations.pptx) | The governance risk and control counterpart to each AI opportunity |
| [`Card_AI_Capability_Map.pptx`](./Card_AI_Capability_Map.pptx) | Which controls are AI-driven vs. human-owned, and the specific AI capability behind each one |

## Card lifecycle, summarized

**Parties:** Consumer → Merchant → Acquirer → Network (Visa/Mastercard/Amex) → Issuer

| Stage | Mechanics | Issuer-side GL |
|---|---|---|
| 01 · Authorization | Real-time approval/decline; hold placed on available balance | Memo hold only — no P&L entry yet |
| 02 · Settlement | Batch clearing; funds actually move issuer → network → acquirer → merchant | Dr. Loan Receivable / Cr. Cash-Due-to-Network |
| 03 · Interchange & Fees | Acquirer pays issuer interchange; both sides pay the network assessment/switch fees | Cr. Interchange Revenue / Dr. Network Fee Expense |
| 04 · Chargebacks | Cardholder disputes; issuer reverses and pursues the acquirer/merchant | Dr. Chargeback Reserve Liability |
| 05 · Reporting | Finance closes the books, explains variances, answers ad hoc questions | GL commentary, reconciliation, variance analysis |

## AI opportunity map

| Stage | AI Use Case | Primary Benefit |
|---|---|---|
| Authorization | Real-time fraud scoring & dynamic approval thresholds | Fewer false declines, lower fraud loss, faster decisioning |
| Settlement | Reconciliation anomaly detection & predictive cash positioning | Fewer manual exceptions, faster close |
| Interchange | Fee-classification audit against network rate tables | Direct, recurring revenue recovery |
| Chargebacks | NLP dispute classification, predictive representment, GenAI drafting | Weeks → days cycle time, higher win rate |
| Reporting | LLM-generated GL commentary, natural-language warehouse query | Analyst productivity, faster finance close |

## Governance & AI capability map

| Stage | AI-Driven Component | AI Capability | Human Gate Retained |
|---|---|---|---|
| Authorization | Bias testing & reason-code explainability | XAI (SHAP/LIME) + statistical bias detection | Independent model validation & sign-off |
| Settlement | Exception detection & root-cause triage | Anomaly detection + grounded LLM summarization | Data lineage & SOX change control |
| Interchange | Fee-leakage / misclassification detection | Predictive classification vs. rate-table rules | Recovery-claim review gate |
| Chargebacks | Representment package drafting | RAG (retrieval-augmented generation) + NLP/NER | Final submission approval |
| Reporting | GL commentary & natural-language query | RAG (retrieval-augmented generation) | Entitlement inheritance & sign-off |

**Takeaway:** AI drives detection, drafting, and retrieval. Humans keep validation, review, and sign-off authority — every AI opportunity above ships with an explicit control obligation, not an implicit one.

## How this was built

Built conversationally with Claude (Sonnet 5, via Claude Code): the lifecycle mechanics and AI/governance analysis were developed through iterative Q&A, then rendered directly into the three decks above (`python-pptx`, one shared visual system across all three so they read as a set). No manual slide-building — the deck generation was scripted end-to-end from the analysis.

## What's next

This is the first entry in the Domain Unwind series. Future domains follow the same three-pass structure (mechanics → AI opportunity → governance/capability), each shipping as its own folder with the same three-deck pattern.

```
domain-unwinds/
├── card-payments/          ← this entry
│   ├── README.md
│   ├── AI_Card_Lifecycle_Opportunities.pptx
│   ├── Card_AI_Governance_Considerations.pptx
│   └── Card_AI_Capability_Map.pptx
└── <next-domain>/
    ├── README.md
    └── ...
```
