# Data Dictionary: `prometheus-quantum-chemistry`

## 1. Pre-Registration & Checksum Manifests (`manifests/`)
- `manifests/phase4_chemistry_pre_registration_v2.json`: Pre-registered `32`-configuration molecular chemistry benchmark (`8` in `Cohort Chem-Dev-8`: `M_Dev_01..M_Dev_08`; `24` in `Cohort Chem-Holdout-24`: `M_Hold_01..M_Hold_24`) specifying molecular geometries, active spaces, exact full-CAS `JW` FCI and paired-electron `DOCI` reference energies, Restricted Hartree-Fock (`RHF`) energies, and noiseless ansatz verification (`< 25.0 mHa` on `32/32` configurations). Byte-exact `SHA-256 = 34fe8b70274c3d5569c331302eaecde2c095fbcd31d965fb6708c79150f64ffa`.
- `manifests/phase4_submission_manifest_v2.json`: Pre-registered execution schedule, standalone `512`-shot confirmation rules, provider account budgets, and hard spending ceilings (`749.0 s` IBM Quantum, `779.25 cr` IQM Resonance). Byte-exact `SHA-256 = ea393602b2b123a64f96027a31cb32f1e3cb65728d5270af82078ae615744134`.
- `manifests/PHASE4_SHA256SUMS.json`: File-level SHA-256 digest table covering the portable Phase 4 release contents.

## 2. Sanitized Hardware Execution Ledgers & Pre-Execution Locks (`ledgers/` - `13` Files)
- `ledgers/phase4_master_172_job_ledger.csv`: Chronological `172`-row master QPU job ledger (`job_seq 1..172`) across `Stage 4.0` (`20` jobs), `Phase 4A` (`60` jobs), and `Phase 4B` (`92` jobs), recording stage, cohort, window/wave, policy ID, provider (`IBM_Quantum` / `IQM_Resonance`), QPU (`ibm_fez` / `emerald`), anonymized account alias, verifiable hardware Job ID / UUID, PUB counts (`pubs_total = pubs_qwc + pubs_witness`), `shots_per_pub`, `physical_shots`, `settled_cost`, `billing_unit`, and UTC submission timestamp.
- `ledgers/phase4_allowance_reservation_ledger.json`: Cumulative reservation-guard and provider settlement ledger (`86` IBM jobs = `675.0 s`; `86` IQM jobs = `735.75 cr`; `0` unrecovered reservations).
- `ledgers/phase4_stage4_0_preexecution_frozen_plan.json`: Frozen `Stage 4.0` pilot compilation and scheduled physical duration (`tau_sched_ns`) spread plan (`0` holdout configurations touched).
- `ledgers/phase4_stage4_0_deep_audit.json`: `Stage 4.0` (`Cohort Chem-Dev-8`, `20` jobs, `353` PUBs, `238,080` shots) empirical billing, duration-mismatch correlation, and `Raw v2.0` per-molecule breakdown.
- `ledgers/phase4_stage4_0_sym_rem_audit.json`: `Stage 4.0` `0`-parameter `Sym-REM` calibration and Rung-1 uncertainty stopping sweep on `Cohort Chem-Dev-8`.
- `ledgers/phase4_holdout24_frozen_lock_v1.json`: Pre-holdout cryptographic specification locked prior to `Phase 4A` execution (`Canonical Payload SHA-256 = aa8f3a62fddcdb79f7f946100c1d678ce90ee11040ca82b6c32c362d18733a65`).
- `ledgers/phase4a_holdout24_campaign_results.json`: Complete `Phase 4A` (`Cohort Chem-Holdout-24`, `60` jobs, `2,585` PUBs, `1,802,752` shots across `Windows 1..3`) per-window job and per-molecule dual-estimator (`Sym-REM` & `Raw v2.0`) Primary + Confirmation results.
- `ledgers/phase4a_holdout24_statistical_analysis.json`: Pre-committed `N = 24` molecule-clustered paired Wilcoxon signed-rank tests, `B = 10,000` bootstrap `95%` CIs, `20,000`-draw sign-flip permutation p-values, Holm-Bonferroni adjustments, and width/species stratifications.
- `ledgers/phase4b_spsa_frozen_lock_v1.json`: Pre-execution cryptographic lock for `Phase 4B` live closed-loop `8`-step `SPSA` starting cold at Restricted Hartree-Fock (`phi_0 = 0`) across `Cohort Chem-4B-6` (`Canonical Payload SHA-256 = f770c6a7f7b28d933d23bd4e9adf230c93439a341a17e9c24a1a725192b5f0a0`).
- `ledgers/phase4b_spsa_campaign_results.json`: Sanitized `Phase 4B` (`92` jobs, `1,874` PUBs, `1,715,200` shots) closed-loop trajectory and final dual-estimator ledger across all `42` (`6` molecular configurations x `7` policies) hardware-in-the-loop runs (`original_private_ledger_sha256 = d2fd3925149f741217a5ed846e234f697b9e83e699e5d77c3825ff0ec8fb9b99`).
- `ledgers/phase4b_spsa_checkpoint.json`: Wave-by-wave (`Waves 0..11`) `Phase 4B` hardware job settlement checkpoint (`46` IBM + `46` IQM jobs).
- `ledgers/phase4b_spsa_job_ledger.csv`: Flat `92`-row CSV ledger of all `Phase 4B` QPU jobs.
- `ledgers/phase4b_spsa_molecule_policy_matrix.csv`: Flat `42`-row (`6` molecular configurations x `7` policies) CSV matrix of cold `RHF` errors, learned parameters `phi_final`, exact noiseless variational errors, Primary/Confirm `Sym-REM` and `Raw v2.0` errors, early freezes, Rung-1 stops, HW-Only confirmation flags, and Strict Joint confirmation flags.

## 3. Empirical Reports (`reports/` - `4` Files) & Publication Figures (`figures/` - `12` PNGs at `300 DPI`)
- `reports/prometheus_phase4_capstone_evidence_release.md`: Consolidated Phase 4 Capstone Evidence Release report (`Stage 4.0 + Phase 4A + Phase 4B`).
- `reports/phase4_stage4_0_dev_pilot_report.md`: Detailed `Stage 4.0` Development & Cost Calibration Pilot report (`20` jobs).
- `reports/phase4a_holdout24_campaign_report.md`: Detailed `Phase 4A` Prospective Out-of-Sample Holdout-24 report (`60` jobs).
- `reports/phase4b_iterative_spsa_campaign_report.md`: Detailed `Phase 4B` Live Closed-Loop Iterative `SPSA` report (`92` jobs).
- `figures/fig1_phase4_capstone_cost_to_accuracy_across_stages.png`, `figures/fig2_phase4_capstone_estimator_and_stopping_validation.png`, `figures/fig3_phase4_capstone_campaign_accounting_172_jobs.png`: Capstone `300 DPI` synthesis figures, accompanied by the `9` stage-level `300 DPI` figures (`fig1..3_stage4_0_*.png`, `fig1..3_phase4a_*.png`, `fig1..3_phase4b_*.png`).

## 4. Standalone Zero-Credential Verifier (`scripts/`) & Top-Level Checksum Ledger
- `scripts/verify_phase4_public_release.py`: Deterministic `6`-stage verification script (Python 3 standard library + `numpy` + `scipy` only).
- `REPO_SHA256_MANIFEST.json`: LF-normalized byte-exact SHA-256 manifest of all tracked repository files.
