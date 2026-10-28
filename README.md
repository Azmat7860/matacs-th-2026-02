# AI Proposal Triage Design

**Candidate:** Azmat Ullah Khan  
**Assessment reference:** MATACS-TH-2026-02  
**Time spent:** TODO — enter the actual time spent before submission.

This design describes a small application that extracts proposal facts with AI, checks mandatory requirements and calculates a reproducible weighted ranking with ordinary application code. A human reviewer retains authority over corrections, overrides and the final award.

## Deliverables

- [Process flow diagram](diagram/process-flow.png)
- [Assessment write-up](WRITEUP.md)
- [Proposed AI prompts](PROMPTS.md)
- [Sample proposal ranking](ranking.json)

Read the scoring assumptions and missing-evidence rules in `WRITEUP.md` before interpreting the scores. `ranking.json` contains provisional ranks only for proposals with confirmed mandatory eligibility and enough evidence to score all five weighted criteria.

## AI use disclosure

AI assisted drafting and the diagram and prompt design. In this draft, Proposal B is left unscored and flagged because the brief requires the bidder to hold the Ontario electrical licence, while B says its subcontractor will be confirmed after award; Proposal D is also left unscored because it states no schedule. **TODO: Azmat must personally verify these interpretations, complete the actual time spent, and confirm this disclosure before publishing.**
