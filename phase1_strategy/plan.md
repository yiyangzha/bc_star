# Phase 1 Strategy Execution Plan

## Role and source limitations

I am executing the defined Phase 1 executor work. The required files `agents/executor.md`, `methodology/03-phases.md`, `methodology/03a-orchestration.md`, `methodology/05-artifacts.md`, `methodology/06-review.md`, `methodology/07-tools.md`, and `conventions/search.md` are not present under the analysis workspace or nearby parent paths searched from this checkout. I will therefore use the explicit instructions in `prompt.md`, `phase1_strategy/CLAUDE.md`, `AGENTS.md` as provided in the orchestration prompt, and the project-level requirements embedded in the user request. This limitation will be logged.

## Literature and external-source queries

I will query and cite:

1. ATLAS `B_c^{*+}` observation: arXiv/INSPIRE record for arXiv:2605.16228, with the decay topology, observable, and statistical treatment used as the closest reference.
2. ATLAS LHCP 2026 public material by Semen Turchikhin and Anna Sfyrla if accessible through web search, for context only unless enough technical detail is public.
3. CMS public Run-3 data/condition documentation relevant to 2024 data, luminosity certification, NanoAOD/MiniAOD content, and HLT menus where official pages are accessible.
4. Statistical references for local/global significance, profile likelihood, and asymptotic formulae.
5. Reference analyses for similar CMS/ATLAS B-physics spectroscopy or quarkonium-plus-soft-object searches, emphasizing systematics and background modelling.

## DAS queries to run

I will run `dasgoclient` queries for data and MC discovery, recording exact commands and any failures:

1. 2024 data datasets containing `ParkingDoubleMuonLowMass`, `ParkingDoubleMuon`, `DoubleMuon`, `Muon`, `Jpsi`, `LowMass`, or `TripleMuon` across NANOAOD, MINIAOD, AOD, and RAW-RECO tiers.
2. 2024 BPH or custom NanoAOD availability by querying dataset names containing `BPH`, `NanoAOD`, and candidate parking streams.
3. Run-3 MC background samples for `Jpsi`, `BToJpsi`, `Bc`, `BuToJpsiK`, `Bstar`, inclusive `B` hadron, and heavy-flavour samples at 13.6 TeV.
4. Signal sample discovery for `BcStar`, `Bcst`, `Bc*`, `BcToJpsiMuNu`, and related names.

## CMS HLT and data-product questions to answer

1. Which 2024 primary datasets and HLT paths provide three-muon or low-mass dimuon events with enough bandwidth for semileptonic `B_c^+` candidates?
2. Does central NanoAOD or BPH NanoAOD preserve the low-pT conversion track information needed for `gamma -> e^+e^-`, including track pT below standard electron thresholds and conversion vertex quantities?
3. If NanoAOD is insufficient, which tier, likely MINIAOD or AOD, is needed for conversions, low-pT tracks, displaced vertices, and trigger object matching?
4. Which certified luminosity JSON applies to the selected 2024 run range?

## Applicable convention choice

The analysis is a search/significance/shape-fit analysis, not an unfolded or extraction measurement. I will apply the search convention described in the orchestration instructions and enumerate the required search-convention sources as binding Phase 4 commitments. Where the actual `conventions/search.md` file is unavailable locally, I will make the enumeration explicit and mark the missing file as a limitation.

## Intended `STRATEGY.md` structure

1. Scope, technique decision, and binding labels.
2. Physics motivation and observable definition.
3. Source inventory and evidence log, including missing methodology/conventions files.
4. DAS sample inventory: data, MC backgrounds, signal, and open gaps.
5. NanoAOD/MiniAOD conversion-track feasibility plan.
6. Trigger and primary-dataset strategy.
7. Reconstruction and object definitions.
8. Two selection strategies: cut-based baseline and MVA/category strategy.
9. Background taxonomy and relative importance.
10. Background estimation, control regions, validation regions, and blinding.
11. Fit and statistical model.
12. Systematic uncertainty plan and search-convention enumeration.
13. Reference-analysis comparison table.
14. Flagship figures and downstream deliverables.
15. Phase 1 self-check and open issues.

## Verification

The phase is complete when `phase1_strategy/outputs/STRATEGY.md` is self-contained, `experiment_log.md` is appended, a session log exists in `phase1_strategy/logs/`, and the Phase 1 executor changes are committed without unrelated files.
