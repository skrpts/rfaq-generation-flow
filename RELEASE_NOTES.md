# Release Notes

## v1.1.26
GH#863 Wave 1 — fix K-045 intent/output mismatch: wire the two uninvoked feeder prompts into the pipeline. Add execution steps for `rfaq-problem-framer` (new `problem-framing` skill, runs first) and `internal-faq-generator` (new `internal-faq-anticipation` skill), each with a distinct backing skill so `from_step` bindings resolve. The RFAQ assembler now consumes the problem framing, risk catalogue, customer FAQ, and internal FAQ via explicit `from_step` bindings (positional `{{steps.*}}` refs converted to `context_params` + `{{step.context.*}}`). Re-pin polish-language→1.0.6 and bind its `source` ← the assembled RFAQ so the output step polishes the real deliverable. Adds 2 skills (total 13→15).

## v1.1.25
GH#845 — republish with American English (en-US) content, completing the source-only GH#805 flip that never reached the Hub. Copy only — no functional or behaviour change.

## v1.1.24
GH#745 — declare per-step `output: {name, type}` on every execution step (risk_catalogue/text, faqs/list, rfaq/text, requirements/text, polished_rfaq/text, consistency_verdict/decision). Lights up the #744 rich flow-map. Content-only; no bindings or logic changes.

## v1.1.23
GH#645 Row 3b — migrate to K-037 dep-referenced schema. Strip 7 inline shared-content files and declare 7 hub-shared deps (UUID id + slug name + version + checksum from `gen-dep-checksums.mjs`). Closes pre-Step-3 inline-vendoring for this bundle.

## v1.1.22
Wave 2: re-signed with canonical engine signing pipeline.

## v1.1.21
Tags migrated inline into manifest (GH#586). tags.yaml retired.

## v1.1.20
Bundle re-signed with canonical engine signing pipeline (Wave 2 migration).

## v1.1.19
Signature fix — RELEASE_NOTES.md now included in integrity checksum.

## v1.1.18
Initial catalog release with full structural and content-quality validation. All scanner checks pass.
