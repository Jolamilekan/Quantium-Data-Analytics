# Quantium Retail Analytics: From Customer Insight to Validated Growth Strategy
### An End-to-End Retail Category Analytics Case Study

---

## 1. Project Title

**Primary title:**
**"From Customer Insight to Validated Growth Strategy: A Retail Chip Category Analytics Engagement"**

**Alternative titles:**
1. "Turning Loyalty Data Into a Chain-Wide Growth Strategy: A Retail Analytics Case Study"
2. "Data-Driven Category Strategy: Customer Segmentation, Causal Testing, and Executive Reporting for Retail"
3. "Beyond the Dashboard: A Three-Stage Retail Analytics Engagement from Segmentation to Boardroom"
4. "Who Buys, Why, and What Works: A Retail Chip Category Deep-Dive"
5. "From Raw Transactions to Strategic Recommendation: A Quantium Retail Analytics Case Study"

---

## 2. Executive Summary

**Business context:** A national supermarket chain's Category Manager for chips needed a data-driven foundation for the category's next half-year strategic plan — specifically, an understanding of who buys chips, why they buy them, and whether a proposed store layout change was worth rolling out chain-wide.

**Problem:** The client had a full year of loyalty transaction data and a recently completed store layout trial, but no structured analysis connecting either to a concrete strategic decision. The challenge was twofold: extract genuine, decision-relevant insight from messy, undocumented raw data, and then determine — rigorously, not anecdotally — whether the trial actually caused a measurable sales impact.

**Approach:** This engagement was run as three connected phases: (1) cleaning and profiling a year of transaction and customer data to understand purchasing behaviour by segment, (2) applying a matched control-store methodology with statistical significance testing to isolate the causal effect of a store layout trial, and (3) translating both technical workstreams into a structured, executive-ready report using the Pyramid Principle communication framework.

**Key findings:**
- Older and Young Families on Budget plans are the highest-value customer segments, driven by purchase *frequency* rather than basket size
- Chip pricing is essentially flat across Budget, Mainstream, and Premium customer tiers — "Premium" does not translate into higher per-unit spend in this category
- Kettle leads the category by revenue; Doritos demonstrates genuine brand pricing power despite lower sales volume
- The trialed store layout produced a statistically significant sales lift in one store, a promising-but-inconclusive trend in a second, and no measurable effect in a third — an inconsistent, but informative, result

**Final recommendations:** Prioritize frequency-based loyalty engagement for high-value family segments, protect shelf space and stock reliability for top-performing brands and pack sizes, and launch an expanded, longer second-phase trial before committing to a full chain-wide rollout of the new layout.

**Business impact:** This analysis gives the Category Manager an evidence-based foundation for the next half-year plan — replacing assumption-driven category decisions with segment-specific targeting, brand/stock prioritization backed by real pricing dynamics, and a disciplined, risk-managed path to validating a potentially valuable store format change before committing significant capital to a chain-wide rollout.

---

## 3. Business Background

**About Quantium:** Quantium is a data science and analytics company that partners with major retailers to convert transaction-level data into commercial strategy. Quantium's retail analytics teams frequently work in a "hybrid" analyst-consultant capacity — producing rigorous technical analysis while also being responsible for communicating it directly to non-technical business stakeholders.

**The retail environment:** Chips are a high-frequency, low-basket-size, impulse-adjacent grocery category. Unlike big-ticket categories, chip category strategy is shaped less by large individual purchase decisions and more by aggregate patterns across millions of small transactions — which segments buy, how often, which brands and pack sizes dominate, and how store-level experience (layout, placement) affects buying behaviour.

**The client:** Julia, Category Manager for chips at a major supermarket chain, responsible for building the category's strategic plan for the upcoming half-year, including decisions on promotional targeting, brand/shelf allocation, and whether to roll out a trialed store layout change more broadly.

**The business challenge:** Julia had access to a year of loyalty transaction data and the results of a completed in-store trial, but neither had been analyzed. Without structured analysis, category decisions risked being driven by anecdote or intuition rather than evidence — a particular risk given that a full chain-wide layout rollout represents a significant capital and operational commitment if the trial's apparent results didn't hold up to scrutiny.

**Why this analysis matters:** Getting category strategy right compounds — correctly identifying high-value segments focuses limited marketing spend where it has the most impact, and correctly (not optimistically) validating the store trial avoids a costly rollout of a change that may not generalize. Both decisions needed to be made with real rigor, not surface-level pattern spotting.

---

## 4. Problem Statement

**Business problem:** Julia needs a defensible answer to two questions before finalizing the chip category's next half-year strategic plan: (1) which customers and products deserve the most strategic focus, and (2) did the recent store layout trial actually work, and does it justify wider rollout?

**Analytical problem:** This required two distinct analytical approaches. Question 1 is fundamentally *descriptive/exploratory* — segmenting and profiling purchasing behaviour across a large transaction dataset. Question 2 is fundamentally *causal* — isolating the effect of a specific intervention (the layout change) from all the other factors that naturally cause store sales to fluctuate over time, which required a control-group comparison methodology and formal statistical testing, not simple before/after observation.

**Success criteria:** Success meant delivering: (1) a validated, cleaned dataset with clear customer segment profiles and purchasing drivers; (2) a rigorously tested, statistically grounded verdict on the layout trial's effectiveness, store by store; and (3) both translated into a concise, non-technical executive report that gives Julia clear, actionable direction for her strategic plan — not just a technical analysis she would need to reinterpret herself.

---

## 5. Business Objectives

**Primary objectives:**
- Identify and profile the customer segments driving the most value in the chip category
- Determine, with statistical rigor, whether the store layout trial caused a genuine sales increase
- Deliver findings in a format immediately usable by a non-technical business stakeholder for strategic planning

**Secondary objectives:**
- Build a reusable, documented analytical methodology (particularly the control-store selection approach) that could be applied to future trials without rebuilding the logic from scratch
- Establish a clean, validated dataset that could support further analysis beyond this specific engagement

**Expected outcomes:**
- A clear segment-targeting strategy for promotional and loyalty spend
- A defensible, risk-aware recommendation on the layout trial rollout decision
- A client-ready report and cover communication suitable for direct executive use

---

## 6. Project Scope

**What was included:**
- One full year (July 2018 - June 2019) of loyalty transaction data across 272 stores
- Customer segmentation data (life stage and premium/mainstream/budget tier)
- A three-store layout trial (Stores 77, 86, 88) run during February-April 2019
- Full data cleaning, feature engineering, exploratory analysis, causal trial evaluation, and executive reporting

**What was excluded:**
- Categories outside chips (salsa dip products present in the raw data were explicitly identified and excluded as out of category scope)
- Analysis of non-loyalty (unidentified) customer transactions, which are not linkable to segment data
- Store-level operational factors outside the transaction data itself (e.g. staffing, local competition, marketing spend by store) that could also influence trial results but were not available in the dataset

**Assumptions:**
- The trial period (February-April 2019) and pre-trial baseline (July 2018-January 2019) were treated as the relevant comparison windows, based on visible inflection points in the data
- Control stores selected via the combined correlation/magnitude methodology are assumed to be reasonable, though imperfect, proxies for "what would have happened without the trial"
- A single commercial-scale loyalty account (200-unit bulk purchases with no other transaction history) was assumed to be a non-representative business account and excluded from analysis

**Constraints:**
- Only three stores were available for the trial, limiting the statistical power of the causal analysis and the ability to generalize findings across store types
- The trial period was short (three months), which affected the strength of statistical conclusions that could be drawn, particularly for borderline results

---

## 7. Dataset Description

**Sources:** Two primary datasets were provided, representing loyalty transaction records and customer segmentation data.

| Dataset | Grain | Records | Description |
|---|---|---|---|
| Transaction data | One row per product line per transaction | 264,836 (raw) → 249,667 (cleaned) | Store, loyalty card, product, quantity, and sales value for every chip-category transaction, July 2018-June 2019 |
| Customer behaviour data | One row per customer | 72,637 | Life stage (7 categories) and premium/mainstream/budget tier (3 categories) per loyalty card holder |

**Data relationships:** The two datasets share `LYLTY_CARD_NBR` (loyalty card number) as a join key, enabling a one-to-many merge (one customer to many transactions). A 100% match rate was confirmed between the two datasets after cleaning, rather than assumed.

**Data dictionary (key fields):**

| Field | Type | Description |
|---|---|---|
| `DATE` | Date | Transaction date |
| `STORE_NBR` | Integer | Store identifier |
| `LYLTY_CARD_NBR` | Integer | Customer loyalty identifier (join key) |
| `TXN_ID` | Integer | Transaction identifier |
| `PROD_NAME` | Text | Raw product name (brand, flavor, pack size combined) |
| `PROD_QTY` | Integer | Units purchased in that line item |
| `TOT_SALES` | Numeric | Dollar value of that line item |
| `LIFESTAGE` | Categorical | Customer life stage segment |
| `PREMIUM_CUSTOMER` | Categorical | Customer price-tier segment |
| `BRAND` | Categorical (engineered) | Standardized brand name |
| `PACK_SIZE` | Numeric (engineered) | Pack weight in grams |
| `PRICE_PER_UNIT` | Numeric (engineered) | Sales value divided by quantity |
| `SEGMENT` | Categorical (engineered) | Combined life stage × price tier label |

**Data quality issues identified and resolved:** Excel serial date formatting requiring conversion; one exact duplicate transaction row; seven mislabeled non-chip (salsa dip) products present in a chip-category dataset; one non-representative outlier customer account; 28 inconsistent brand name spellings/abbreviations requiring standardization into 20 accurate brand labels. Full detail in Section 10.

---

## 8. Tools and Technologies

| Tool | Purpose in this engagement |
|---|---|
| **R** | Primary language for data cleaning, feature engineering, statistical analysis, and visualization — chosen for its strength in statistical testing (t-tests) and the tidyverse ecosystem's readability for reproducible data pipelines |
| **tidyverse (dplyr, ggplot2, stringr)** | Data manipulation, aggregation, and chart generation; dplyr's `group_by`/`summarise` pattern underpins nearly all exploratory and trial analysis in this project |
| **R Markdown** | Reproducible reporting — combining code, output, and narrative into a single, self-contained document that regenerates the full analysis from raw data on demand, rather than relying on manual, error-prone copy-paste reporting |
| **Regular expressions** | Extracting structured features (pack size) from unstructured product name text |
| **PowerPoint** | Client-facing report construction, applying the Pyramid Principle communication framework for a non-technical executive audience |
| **Git / GitHub** | Version control and professional presentation of the full project as a public portfolio artifact |

---

## 9. Methodology

This engagement followed a structured, three-phase workflow, with each phase building directly on the last:

**Phase 1 — Business & Data Understanding:** Clarified the client's actual decisions at stake (segment targeting, layout rollout) before any code was written, then thoroughly inspected both datasets — column-by-column meaning, types, relationships, and likely issues — before attempting any cleaning.

**Phase 2 — Data Cleaning & Feature Engineering:** Corrected data types, removed duplicates and out-of-scope products, investigated and excluded a non-representative outlier account, standardized inconsistent brand naming, and engineered analytical features (brand, pack size, price per unit, combined segment) needed for downstream analysis.

**Phase 3 — Exploratory Data Analysis & Segmentation:** Quantified purchasing behaviour across customer segments, brands, and pack sizes, testing hypotheses about pricing and value drivers rather than assuming them, and identifying the specific segments and behaviours most relevant to category strategy.

**Phase 4 — Causal Trial Evaluation:** Built a reusable, parameterized methodology to select a statistically matched control store for each of the three trial stores (combining trend correlation and magnitude-of-scale matching), then applied Welch's t-test to determine whether each trial store's sales lift was statistically credible, decomposing any effect into its underlying drivers (customer count vs. purchase frequency).

**Phase 5 — Executive Communication:** Synthesized both technical workstreams into a single, non-technical business narrative using the Pyramid Principle — leading with the governing recommendation, structured around three supporting pillars, and delivered as a client-ready report and cover communication.

This phased structure reflects a deliberate escalation in analytical sophistication — from descriptive profiling, to statistically rigorous causal inference, to business communication — mirroring the full skill range expected of a professional retail analytics engagement, rather than a single isolated technical exercise.

---

## 10. Data Cleaning

Raw transaction data arrived undocumented and required six distinct interventions before it could support reliable analysis. Each is presented below with its business rationale, not just its technical fix.

**Issue 1 — Incorrect date format.** `DATE` was stored as an Excel serial integer rather than a usable date type. *Solution:* converted using the standard Excel epoch (30 December 1899). *Business importance:* without this, no time-based analysis (seasonality, trial period definition) would have been possible.

**Issue 2 — Duplicate transaction row.** One exact duplicate row was identified and removed. *Business importance:* an uncaught duplicate silently inflates revenue and unit totals — a small error here compounds into a materially wrong headline number if left unchecked.

**Issue 3 — Out-of-scope products.** Seven salsa dip products were present in what was meant to be a chips-only dataset. *Solution:* these were identified precisely by product name (not a broad keyword filter, which was tested and found to incorrectly also remove legitimate salsa-*flavoured chip* products) and excluded. *Business importance:* mixing a different product category into "chip category" metrics would have misrepresented brand performance, segment value, and total category size to the client.

**Issue 4 — Non-representative outlier account.** One loyalty card showed two 200-unit, $650 purchases with no other transaction history across the full year. *Solution:* investigated (confirmed no other purchase behaviour existed for this account) and excluded as a likely commercial/bulk buyer rather than a genuine household customer. *Business importance:* segment-level averages are highly sensitive to single extreme outliers; leaving this account in would have distorted per-customer spend calculations used throughout the engagement.

**Issue 5 — Inconsistent brand naming.** Free-text product names yielded 28 distinct "brand" tokens that actually represented only 20 real brands (e.g. `RRD`/`Red` both meaning Red Rock Deli; `WW` meaning Woolworths). *Solution:* standardized via an explicit mapping table. *Business importance:* brand-level insights (e.g. brand popularity, pricing power) are only meaningful if a brand's sales aren't artificially split across multiple spelling variants.

**Issue 6 — Unvalidated dataset merge.** Transaction and customer datasets were joined on loyalty card number without assuming the join would be clean. *Solution:* explicitly verified a 100% match rate (zero unmatched transactions) after merging, rather than trusting the join silently. *Business importance:* an unvalidated merge risks silent data loss that would understate segment-level metrics without any visible error.

**Result:** 264,836 raw transaction rows were reduced to 249,667 validated, in-scope, analysis-ready rows.

---

## 11. Feature Engineering

Four features were engineered beyond the raw dataset, each created to answer a specific class of business question:

| Feature | Derivation | Business value |
|---|---|---|
| `BRAND` | Extracted and standardized from free-text product names | Enables brand-level revenue, volume, and pricing analysis |
| `PACK_SIZE` | Extracted via regex from product names (digit sequence preceding "g"/"G") | Enables analysis of pack-size preference and shelf/stock prioritization by segment |
| `PRICE_PER_UNIT` | `TOT_SALES ÷ PROD_QTY` | Isolates price from purchase volume — critical for correctly interpreting whether a segment's higher spend reflects paying more, or buying more |
| `SEGMENT` | Combined `LIFESTAGE` × `PREMIUM_CUSTOMER` label | Enables analysis across the full 21-way combined customer segmentation rather than each dimension in isolation, revealing combinations (e.g. "Older Families - Budget") invisible to either dimension alone |

A fifth engineered field, `YEARMONTH`, was introduced specifically to support Task 2's time-series aggregation, collapsing daily transaction dates into monthly buckets for store-level trend comparison.

---

## 12. Exploratory Data Analysis

Analysis proceeded in layers, from headline category metrics down to segment-specific behaviour, with each step designed to answer a specific business question rather than simply describing the data.

**Headline metrics.** Objective: establish the scale of the category before any deeper analysis. Method: aggregate sums and distinct counts across the cleaned dataset. Result: $1.82M total category sales across 71,517 customers and 248,156 transactions. Business insight: chips are a low-frequency, low-basket category (average ~1.9 units per transaction) — a lever like "encourage bigger baskets" is less promising here than growing purchase frequency or shifting customer value mix.

**Brand and pack size popularity.** Objective: identify which products carry the most commercial weight. Method: grouped revenue and volume totals by brand and by pack size. Result: Kettle leads by revenue; Doritos, despite lower unit sales than Smiths, generates more total revenue due to a ~26% higher price per unit — genuine brand pricing power, not just shelf presence. 175g is the dominant pack size, accounting for the majority of customer purchases. Business insight: brand strategy and pricing decisions should account for demonstrated pricing power, not just volume; pack-size stocking priorities should protect the single dominant SKU.

**Segment-level sales and spend.** Objective: identify where category value actually concentrates. Method: grouped total sales, customer counts, and average spend per customer across life stage, price tier, and the combined segment label. Result: Older Families - Budget is the single highest-value combined segment, both in total sales and average spend per customer; the effect is driven by purchase *frequency* (up to 4.76 transactions/customer/year), not larger baskets. Business insight: reveals that segment value is being driven by a different mechanism (repeat visits) than might be assumed (bulk buying), directly shaping the *type* of promotion likely to work.

**Pricing behaviour by tier.** Objective: test the assumption that "Premium" customers pay more for chips specifically. Method: compared average price per unit across Budget, Mainstream, and Premium tiers. Result: price per unit is nearly flat (~$3.79-$3.86) across all three tiers — Budget customers' higher average spend is driven by buying *more* units, not paying more per unit. Business insight: this directly overturned an initial hypothesis, and is a stronger, more specific finding than the assumption it replaced — a reminder that segment labels describing overall shopping identity don't necessarily predict category-specific price sensitivity.

---

## 13. Customer Segmentation

**Method:** Quantium's existing two-dimensional segmentation was used as the analytical backbone — `LIFESTAGE` (7 life-stage categories) combined with `PREMIUM_CUSTOMER` (3 price-tier categories), producing 21 possible combined segments, all of which were present and analyzed in the dataset.

**Segment characteristics and purchasing behaviour:**
- **Older Families - Budget** and **Young Families - Budget**: highest average spend per customer, driven by high purchase frequency rather than basket size
- **Young Singles/Couples - Mainstream** and **Retirees - Mainstream**: largest customer populations, generating high total revenue primarily through volume of customers rather than per-head value
- **New Families** (across all price tiers): smallest, lowest-value segment by every measure tested — total sales, customer count, and average spend

**Commercial implications:** the family-budget segments represent the highest-value, most frequency-driven customer base — best suited to loyalty and repeat-visit incentives. The large mainstream/singles segments represent reach and volume rather than premium value — better suited to broad awareness plays than intensive per-customer investment. New Families represent either an underdeveloped opportunity or a genuinely low-priority segment, worth a dedicated follow-up analysis beyond this engagement's scope.

---

## 14. Key Insights

**Insight 1 — Family-Budget segments are the category's highest-value customers, driven by frequency.**
*Evidence:* Older Families - Budget: $158k total sales, $34.30 average spend/customer, 4.76 transactions/customer/year (well above category average).
*Business implication:* Standard "buy more, save more" bulk promotions are mismatched to how this segment actually shops.
*Recommended action:* Shift promotional design toward frequency/loyalty-based incentives for these segments specifically.

**Insight 2 — "Premium" customers do not pay a premium for chips.**
*Evidence:* Average price per unit is flat (~$3.79-$3.86) across Budget, Mainstream, and Premium tiers; Budget customers' higher spend is volume-driven.
*Business implication:* Premium-tier marketing built around price-based positioning is likely to underperform in this specific category.
*Recommended action:* Reframe Premium-tier chip promotions around volume incentives rather than price premiums.

**Insight 3 — Doritos demonstrates real, quantifiable pricing power.**
*Evidence:* ~26% higher average price per unit than Smiths, despite lower unit sales volume, while still generating more total revenue.
*Business implication:* Not all brand value is volume-driven; some brands can sustain higher margins independent of shelf share.
*Recommended action:* Evaluate modest price increase testing on Doritos variants specifically.

**Insight 4 — The store layout trial's effect was real but inconsistent across stores.**
*Evidence:* Store 88 showed a statistically significant sales lift (p = 0.040); Store 77 showed a borderline, promising trend (p = 0.054); Store 86 showed no credible effect (p = 0.127).
*Business implication:* A uniform "yes/no" rollout verdict is not supported by the evidence — store-level factors likely moderate the layout's effectiveness.
*Recommended action:* Investigate store-level characteristics predicting a positive response before committing to a chain-wide rollout.

---

## 15. Visualizations

| Chart | Purpose | Business value |
|---|---|---|
| Sales by Customer Segment (ranked bar chart) | Identify which of the 21 combined segments drives the most category revenue | Directly informs which segments deserve promotional priority |
| Sales by Brand (ranked bar chart) | Compare brand-level revenue contribution | Informs shelf space and brand negotiation priorities |
| Price Per Unit by Customer Tier (grouped bar chart) | Test whether price sensitivity genuinely differs by declared customer tier | Prevents a flawed pricing strategy built on an incorrect assumption |
| Trial vs. Control Store Comparison (faceted line chart, all 3 trials) | Visualize each trial store's sales trend against its matched control, before and during the trial period | The single most persuasive visual in the engagement — makes the inconsistency across trial outcomes immediately legible to a non-technical reader |

*(Chart image files are available in the repository's `/visualizations` folder.)*

---

## 16. Recommendations

**Recommendation 1 — Prioritize frequency-based engagement for Older and Young Families (Budget tier).**
*Evidence:* Highest total sales and average spend per customer in the category, driven by visit frequency.
*Expected impact:* Higher retention and repeat-purchase rate among the category's most valuable existing customers.
*Risks:* Risk of over-indexing marketing spend on an already-loyal segment at the expense of growth segments; monitor incremental lift versus baseline behaviour.
*Next steps:* Pilot a loyalty/frequency-based promotion targeted at these segments, with a measured control group to validate incremental impact.

**Recommendation 2 — Reframe Premium-tier marketing around volume, not price.**
*Evidence:* Flat price-per-unit across all customer tiers.
*Expected impact:* Improved promotional relevance and conversion for Premium-tier customers in this specific category.
*Risks:* This finding is category-specific (chips); it should not be assumed to generalize to other categories without separate testing.
*Next steps:* Test volume-based (multi-buy) offers with Premium-tier customers and measure uptake versus historical baseline.

**Recommendation 3 — Protect shelf space and stock reliability for Kettle, Doritos, and 175g packs; test a Doritos price increase.**
*Evidence:* Kettle's revenue leadership, Doritos' demonstrated pricing power, and 175g's category-wide dominance including among top-value segments.
*Expected impact:* Reduced stock-out risk on highest-revenue-at-risk SKUs; potential margin uplift from Doritos pricing test.
*Risks:* A price increase test carries volume-loss risk if price elasticity is higher than the current data suggests; recommend a small, monitored test rather than a blanket change.
*Next steps:* Implement inventory priority rules for top SKUs; design a controlled price test for Doritos in a limited store sample.

**Recommendation 4 — Do not commit to an immediate chain-wide layout rollout; run an expanded second-phase trial.**
*Evidence:* Inconsistent statistical results across the three trial stores (one significant, one borderline, one null).
*Expected impact:* Avoids a potentially costly chain-wide rollout of a change that may not generalize across all store types, while preserving the option to scale a change that does show promise.
*Risks:* Delaying rollout carries an opportunity cost if the layout genuinely works broadly; this must be weighed against the risk of a poorly-targeted, capital-intensive rollout.
*Next steps:* Design a larger, longer (6+ month) second-phase trial across a more diverse set of stores, explicitly designed to test which store characteristics predict a positive response.

---

## 17. Business Impact

**How the recommendations would help the client:** These findings replace assumption-driven category decisions with an evidence base Julia can defend directly to her own stakeholders. Rather than guessing which segments matter or trusting an unvalidated trial result, the strategic plan can now cite specific, tested figures for segment value, pricing behaviour, and trial outcomes.

**Revenue opportunities:** Frequency-based engagement with the highest-value family segments targets the category's largest existing revenue base with a mechanism (repeat visits) that matches how they actually behave, rather than a generic promotion likely to underperform. The validated Store 88 layout result represents a concrete, evidence-backed growth lever worth expanding carefully rather than either dismissing or over-committing to prematurely.

**Marketing implications:** The finding that price sensitivity is flat across customer tiers directly changes how Premium-tier marketing should be framed in this category — a real, actionable pivot away from a plausible-but-incorrect default assumption.

**Customer targeting opportunities:** The 21-segment combined view surfaces specific high-value combinations (e.g. Older Families - Budget) that neither life-stage nor price-tier analysis alone would have revealed — a more precise targeting unit than the client's existing broad segment categories.

---

## 18. Challenges

**Technical challenges:**
- A naive keyword-based product filter (matching "salsa" in product names) initially removed legitimate salsa-*flavoured chip* products alongside genuine salsa dip products — caught only by manually verifying the filter's actual output before trusting it, reinforcing that text-based cleaning rules must always be checked against real results, not assumed correct.
- R Markdown documents execute in an isolated environment separate from the console session used during development — meaning objects and libraries loaded interactively do not carry over automatically. This required rebuilding the full data pipeline inside each report document itself to guarantee reproducibility, a lesson that recurred (and was correctly self-diagnosed with decreasing help) across multiple points in the engagement.

**Data issues:**
- One customer account showed extreme, non-representative purchase volumes (200 units per transaction, twice, with no other purchase history) — required judgment to investigate and justify exclusion rather than either ignoring it or applying an arbitrary cap.
- One candidate control store returned an undefined correlation coefficient due to zero variance in its pre-trial customer counts — required understanding *why* a statistical function can fail gracefully, rather than treating the resulting warning as an error to suppress.

**Analytical challenges:**
- An initial hypothesis (that Premium-tier customers pay more per unit for chips) was disproven by the data. Rather than discarding this as a failed test, the actual finding — flat pricing, volume-driven spend differences — was recognized as a more specific and more useful insight than the original assumption.
- A borderline statistical result (p = 0.054 for Store 77) required precise, calibrated language in the final reporting — neither overstating it as a confirmed effect nor dismissing it as a null result, but accurately representing what a small trial-period sample size does and doesn't allow you to conclude.

**Lessons learned:** The most valuable lessons in this engagement were less about R syntax and more about analytical judgment — investigating before deleting data, verifying transformations rather than trusting them, and reporting uncertainty honestly rather than smoothing it over for a cleaner-sounding conclusion.

---

## 19. Skills Demonstrated

**Technical skills:**
`Data Cleaning & Validation` · `Data Wrangling (dplyr/tidyverse)` · `Feature Engineering` · `Regular Expressions` · `Statistical Hypothesis Testing (Welch's t-test)` · `Control Group / Causal Analysis Design` · `Custom Function Development (R)` · `Data Visualization (ggplot2)` · `Time-Series Aggregation` · `R Markdown Reproducible Reporting` · `Git / GitHub Version Control`

**Business skills:**
`Critical Thinking & Hypothesis Testing` · `Problem Framing & Scoping` · `Stakeholder-Ready Communication` · `Business Storytelling (Pyramid Principle)` · `Risk-Aware Recommendation Design` · `Executive Presentation Development` · `Commercial Judgment Under Uncertainty`

---

## 20. Portfolio Reflection

This engagement pushed my analytical thinking well beyond running code to produce charts — the real work was in the judgment calls: deciding whether a filtered-out row genuinely belonged outside the analysis, recognizing when a naive text filter had over-corrected, and choosing how to report a statistical result that was real but not clean-cut.

The most significant growth came from being wrong in a useful way. My initial assumption — that Premium-tier customers would pay more per unit for chips — didn't hold up, and the actual finding (flat pricing, volume-driven spend) turned out to be more specific and more commercially useful than my original assumption would have been. Learning to treat a disproven hypothesis as a stronger finding, rather than a failed test, was a genuine shift in how I approach analysis.

I also learned the practical discipline of reproducibility the hard way — hitting the same "works in my session but not standalone" failure mode more than once before internalizing why R Markdown documents need to be fully self-contained, and why "it ran once" is a different bar from "it's reproducible."

If I were to improve this engagement further, I would extend the trial analysis with a longer observation window and a larger store sample, specifically to strengthen the borderline and null results rather than leaving them as final answers — three months and three stores is a real statistical power constraint worth being upfront about, not just a footnote.

The key takeaway: technical execution is necessary but not sufficient. The actual value in this work came from asking "does this number mean what I think it means" at every step, and being willing to report an honest, sometimes messy answer rather than a falsely tidy one.

---

*[Sections 21-24 — GitHub README, Resume Entry, LinkedIn Post, and Interview Preparation — to be delivered as separate standalone files/deliverables, per the approved roadmap.]*
