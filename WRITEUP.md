# AI Proposal Triage Design

## Scoring assumptions used for this sample

The brief defines criteria and weights, not numeric bands. These are proposed assumptions, applied consistently, not Matacs rules. Check mandatory gates first: affirmative failure means `ineligible`; missing or unclear proof means `flagged` for clarification. The licence must be held by the bidder, so B's post-award subcontractor plan does not establish a pass. Keep B unranked and unscored pending review; mark it ineligible if the bidder cannot meet the gate.

Score only after mandatory eligibility and all weighted evidence are confirmed. Flag missing or contradictory evidence for clarification; withhold total and rank until resolved. A supported result at the bottom of a scale may score zero. D is flagged and unranked because its schedule is undetermined. Scores are provisional, not award recommendations.

Experience counts documented commercial installs ≥100 kW completed in five years: 10+ = 100; 8–9 = 80; 5–7 = 60; 3–4 = 40; 1–2 = 20; none = 0. Price = 100 × (ceiling − bid) ÷ (ceiling − lowest eligible, complete bid), clamped to 0–100. Exclude ineligible, flagged and over-budget bids from the reference. Over budget scores 0; the ceiling is not a mandatory gate in this scenario. Timeline: ≤10 weeks = 100; 11–12 = 80; 13–14 = 60; 15–16 = 40; >16 = 0. Missing schedule is unresolved, not zero.

Warranty is the mean of panel and workmanship scores, each capped at 100: <5 years = 0; 5–7 = 50; 8–9 = 70; 10–11 = 90; ≥12 = 100. Team/approach totals: named lead (25), crew of ≥5 (15), documented qualifications (10), safety plan (20), project-specific delivery plan (roof review, permits, utility connection or progress reporting; 15), and post-install monitoring (15). Missing subcomponents score zero and appear in the breakdown; contradictions are flagged. Apply `criterion score × weight / 100`, sum, then round to one decimal. Rank by unrounded total; ties share rank.

Applying these assumptions gives A 95.5, E 81.4 and C 72.9. The eligible, fully scored bids establish the price reference; flagged bids B and D are excluded until resolved. B remains flagged at the licence gate and D remains flagged for missing timeline evidence. The five weights total 100%. C's appendix instruction is untrusted proposal text and has no effect on facts, eligibility, points or order. E's 12-year workmanship warranty scores 100 in that component; its 24 months of monitoring is noted as evidence of a monitoring plan, not an extra scored criterion.

## Question 1: AI vs. rules

Ordinary application code authenticates users, validates upload type and size, stores files with restricted access, records a file hash, extracts document text, validates structured output, checks mandatory gates, applies configured weights, sorts totals and enforces permissions. AI is used only to turn unstructured proposal text into candidate facts, quotations and page references, and to label ambiguity or contradictions. AI cannot set numeric scores, change criteria, determine eligibility, rank bids or approve an award. This boundary keeps interpretation useful while making consequential decisions reproducible.

## Question 2: Consistency and explainability

Each category has an immutable criteria version: mandatory tests, definitions, weights, scoring bands, tie rule and effective date. The application rejects negative weights, missing criteria and totals other than 100%. A scoring run stores the criteria version, source-file hash, extracted facts, evidence locations, reviewer corrections, scoring-code version and full criterion breakdown. The same inputs and versions therefore produce the same result. Reviewers can open each cited quotation/page, correct a fact, see the recalculated criterion and total, and inspect why missing evidence was flagged. Model name/version and prompt version are recorded because extraction may vary; results are rerun only after a reviewed extraction change, while numeric scoring remains deterministic.

## Question 3: Human in the loop

A reviewer confirms category and submission, resolves unclear mandatory evidence, and checks low-confidence or contradictory extractions before scoring. The results screen shows evidence and points per criterion; authorized reviewers can correct extracted facts or enter a reasoned override. A separate human makes and records the final award decision. Append-only audit events capture actor, timestamp, action, prior and new values, reason, file hash, criteria/prompt/model versions, scores and overrides. A changed fact triggers recalculation and a new result revision rather than erasing the earlier one.

## Question 4: Changing criteria

Admins draft and validate a new criteria version; an authorized second person approves and publishes it. Existing runs retain their original version and scores. Do not silently rescore active proposals after a change. If policy permits a criteria change during an open competition, record approval, notify reviewers and bidders as appropriate, then rescore every proposal in that competition under the same new version. Preserve both result sets and identify which version governs the decision.

## Question 5: Risks

Validate strict JSON and every quoted page reference; flag uncertainty for human confirmation and never pass unsupported mandatory facts. Treat documents as untrusted data to contain prompt injection. Versioned weights, formulas and tie rules keep arithmetic consistent. Reduce bias with job-related published criteria, masking irrelevant identity details where feasible, outcome checks and reviewer challenge. Limit malicious-file risk with type/size limits, malware scanning, sandboxed extraction and restricted storage. Minimize, encrypt and time-limit retained data; restrict model-provider access. Control cost with page/token limits, one extraction pass and file-hash caching. Results are advisory: an authorized human decides and overrides are logged. Extraction/model failures stop for retry or review, never a guessed ranking.
