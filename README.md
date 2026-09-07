# WP12 Public Reproducibility Release v1.0.0 — Corrected

Reproducibility artifact for:

**Asymmetric Cryptographic Interfaces for Noise-Degenerate SPDE Sensors: Leakage Bounds, Privacy Amplification, and an FPGA-Validated Digital Transceiver**

Authors: Adnan H. Abdulwahid, Faycal Znidi, Ram C. Neupane, and Elgaddafi Elamami.

## What this release contains
This release preserves the completed WP01–WP06 and WP09–WP12 digital/FPGA validation materials while making one documented correction to a derived precision-ablation summary. It includes reference/software material, RTL/FPGA packages, consolidated CSV/JSON data, publication-ready figures, LaTeX-ready outputs, Vivado/XSim evidence, correction provenance, and cryptographic/file manifests.

**Experimental scope:** the complete downstream digital transceiver is implemented and validated. WP07/WP08 physical sensor acquisition and physical source min-entropy characterization were not performed; physical entropy quality therefore remains outside the empirical claims of this artifact.

## Important correction
The immutable original WP12 archive transcribed the Q16.16 mean relative L2 error as approximately `9.50e-4` in several derived summaries. Re-running its own frozen WP10 script with 500 cases and seed `20260910` gives:

**Q16.16 mean relative L2 = 0.00905040766776842552 (approximately 9.05e-3).**

The original frozen packages remain untouched. Corrected public tables, figures, JSON/LaTeX summaries, and a corrected WP10 derivative are included. See [`docs/CORRECTION_NOTICE.md`](docs/CORRECTION_NOTICE.md).

## Quick start
```bash
python -m pip install -r requirements.txt
python scripts/reproduce_all.py
python scripts/verify_public_release.py
```

## Two distribution bundles
- **GitHub repository bundle:** browseable code/RTL/data/figures/key reports; omits the bulky raw `archival_evidence/` tree.
- **Full Zenodo bundle:** contains everything in the GitHub bundle **plus** the raw WP05/WP09 XSim archives and full WP06 archival evidence.

See [`docs/REPOSITORY_MAP.md`](docs/REPOSITORY_MAP.md) and [`docs/REPRODUCIBILITY_GUIDE.md`](docs/REPRODUCIBILITY_GUIDE.md).

## Headline archived evidence
The complete archive preserves the evidence supporting the principal N=64 internal routed-core benchmark at 130.005 MHz, including timing/utilization/power reports and build constraints. The power value is a Vivado post-implementation estimate, not measured board power. External board-I/O timing certification is not claimed.

## Provenance
- Original immutable WP12 SHA-256: `21cf97ae3ef8db104c9ab18ec37e0984fca506a72d75f241bcf5aff1fe66716b`
- Correction overlay SHA-256: `a657b1814752be37f8fa898667151ee56fdb498a4c46e549f00c7ed7fce373ca`
- Public release file hashes: `manifest/SHA256SUMS.txt`

## Citation
Machine-readable citation metadata are in `CITATION.cff`; Zenodo metadata are in `.zenodo.json`.

## Licensing
No license was present in the source archive, so this build intentionally does not assign rights on behalf of the authors. Before public release, resolve `LICENSE_SELECTION_REQUIRED.md`.

## Full raw-evidence archive
The complete Zenodo upload file is `WP12_ZENODO_FULL_v1.0_CORRECTED.zip` with SHA-256 `7c0f17076f19c67dca4407c82ac74665f16acd370388d7d9f7ed4e7b2aeb3aa6`. After Zenodo assigns a DOI, add the DOI/badge/link to this README and `CITATION.cff`.
