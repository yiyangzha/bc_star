# Experiment Log

## 2026-06-20 Phase Tracking Initialized

Initial physics prompt is recorded in `prompt.md`. The prompt defines a CMS
Run-3 2024 search for `B_c^{*+} -> B_c^+ gamma` with
`B_c^+ -> J/psi mu^+ nu_mu X`, `J/psi -> mu^+ mu^-`, and converted
`gamma -> e^+ e^-`, using `Delta m = m(J/psi mu e^+e^-) - m(J/psi mu)`.

Mandatory phase pipeline:

- Phase 1: Strategy — executor + 4-bot review
- Phase 2: Exploration — executor + self-review
- Phase 3: Selection — executor + 1-bot review
- Phase 4a: Expected results — executor + note writer + typesetter + 4-bot+bib review
- Phase 4b: 10% data validation — executor + note writer + typesetter + 4-bot+bib review + human gate
- Phase 4c: Full data results — executor + note writer + 1-bot review
- Phase 5: Final documentation — executor + note writer + typesetter + 5-bot review

Current action: start Phase 1 strategy through the defined executor agent.
The prompt is a search/shape-fit analysis even though the phase template was
generated under a measurement label; Phase 1 must make and document the
analysis-technique choice explicitly.
