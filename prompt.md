# Analysis Title: Search for the B_c^{*+} Meson with CMS Run-3 2024 Data

You are performing a search for the lightest excited B_c meson, B_c^{*+}, using CMS Run-3 2024 proton-proton collision data at √s = 13.6 TeV. The target decay chain is

B_c^{*+} → B_c^+ γ,
B_c^+ → J/ψ μ^+ ν_μ X,
J/ψ → μ^+ μ^-,
γ → e^+ e^-.

The final state therefore contains three muons and two low-pT oppositely charged tracks from a converted photon. The main observable is

Δm = m(J/ψ μ e^+e^-) − m(J/ψ μ),

where a narrow signal is expected near 50–70 MeV.

Follow the strategy of the ATLAS B_c^{*+} observation, but redesign the reconstruction, trigger, event selection, and background model for CMS. Use the following references:

* ATLAS Collaboration, “Observation of a B_c^{*+} meson with the ATLAS detector,” arXiv:2605.16228.
* Semen Turchikhin, “Heavy-flavour spectroscopy results from ATLAS,” LHCP 2026.
* Anna Sfyrla, “ATLAS Highlights,” LHCP 2026, especially slide 18 shown in the provided image.

Use CMS Run-3 data from 2024 where available. Find the official data samples with DAS and dasgoclient, focusing on suitable B-physics parking (ParkingDoubleMuonLowMass), J/ψ, low-mass dimuon, double-muon, or triple-muon datasets. Select the trigger paths yourself from the official CMS Run-3 HLT menus.

This analysis is being run on lxplus, and I have already run `voms-proxy-init -voms cms -valid 168:00`. Any agent that needs CMS data or MC must use DAS/`dasgoclient` for discovery and should choose an appropriate fast access path for the task: CRAB, HTCondor, direct XRootD/AAA reads, EOS access, or Rucio replication checks as appropriate. Avoid slow bulk copies unless there is a clear reason. Before using CRAB or HTCondor, first find and study the current relevant CMS/CERN tutorials and documentation, then follow those instructions instead of relying on memory.

For data and MC processing, CRAB or HTCondor are both acceptable. CRAB submissions must be prepared and submitted from a suitable CMSSW environment for the task. HTCondor submissions must be prepared and submitted from the AFS filesystem, for example under `/afs/cern.ch/user/y/yiyangz/condor`; output files may still be written to EOS when appropriate. First check whether a suitable NanoAOD exists, including BPH NanoAOD if available for the selected 2024 data and triggers. If a suitable NanoAOD contains the required objects and sufficiently low-pT conversion-track information, it may be used directly. If no suitable NanoAOD exists, or if NanoAOD lacks the needed particles, conversion information, or sufficiently low track-pT reach, write an ntuple maker and run it on the appropriate data tier with CRAB or HTCondor. For real data, always apply the certified luminosity mask; for 2024 data, consider `/eos/user/c/cmsdqm/www/CAF/certification/Collisions24/Cert_Collisions2024_378981_386951_Golden.json` or the correct updated certification JSON for the selected run range.

Use CMS Run-3 MC at √s = 13.6 TeV with detector conditions matched to the selected data periods. Search DAS for official signal and background samples. If no official B_c^{*+} signal MC exists, generate a private Run-3 CMSSW sample with an appropriate B_c production model, EvtGen decays, and full GEANT4 detector simulation, including photon conversion in the CMS tracker material.

Reconstruct J/ψ → μ^+μ^-, combine it with a third muon to form a semileptonic B_c^+ candidate, and reconstruct the soft photon from an e^+e^- conversion. Optimize the muon, vertex, displacement, conversion-radius, opening-angle, track-pT, and e^+e^- invariant-mass requirements.

Before the full analysis, verify whether the required very low-pT conversion tracks are available in CMS NanoAOD or MiniAOD.

Model the dominant combinatorial background using data-driven methods such as event mixing, same-sign track pairs, conversion sidebands, or wrong-charge three-muon candidates. Investigate possible peaking backgrounds, particularly B^{*+} → B^+γ with B^+ → J/ψ K^+ and hadron-to-muon misidentification.

Categorize events according to B_c^+ candidate quality, conversion quality, or another optimized discriminator, and fit all categories and Run-3 years simultaneously. Perform an extended likelihood fit to the Δm distribution and propagate the main uncertainties from trigger and muon efficiencies, low-pT tracking, photon conversion, tracker material, signal modelling, and background modelling.

Report the fitted signal yield, cross-section of B_c^{*+}, local significance, global significance, expected significance, Δm(B_c^{*+}), statistical and systematic uncertainties, goodness of fit, and category-by-category results.

In the final analysis note, compare the CMS Run-3 result with the ATLAS Run-2 observation and available theoretical predictions. If the available CMS data products do not support sufficiently low-pT conversion reconstruction, state this clearly and produce the strongest technically valid reduced analysis or sensitivity projection.
