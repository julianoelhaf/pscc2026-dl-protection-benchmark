# Comparison of Deep Learning Methods for Power System Protection

> Repository accompanying our PSCC 2026 submission.  
> **Status:** Work in progress – code and pretrained models will be released after acceptance.

---

## Overview

This repository provides the framework, configuration templates, and documentation for a comprehensive benchmark of deep learning architectures applied to **power system protection** tasks.  
The study systematically compares recurrent, convolutional, hybrid, and transformer-based models under identical experimental conditions.

The benchmark covers four core protection tasks:

| Task | Abbreviation | Type | Metric |
|------|---------------|------|---------|
| Fault Detection | FD | Binary classification | F1-score |
| Fault Classification | FC | Multi-class classification | F1-score |
| Fault Line Identification | FLI | Multi-class classification | F1-score |
| Fault Localization | FL | Regression | Mean Absolute Error (MAE) |

All models are trained on high-frequency electromagnetic-transient (EMT) simulations of a **90 kV double-line system** with 48 measurement channels and sampling rate of 6.4 kHz.  
Input sequences are windowed to 10–50 ms segments with 5 ms stride, enabling consistent temporal coverage across tasks.

---

## Key Features

- **Unified training and evaluation pipeline** for FD, FC, FLI, FL  
- **Standardized data preparation** and windowing  
- **Cross-model comparability** through fixed seeds and shared hyperparameters  
- **Reproducibility focus**: all parameters, datasets, and metrics versioned  
- **PyTorch-based implementation** with MLflow tracking (to be published)

---

## Repository Layout

```text
pscc2026-protection-benchmark/
├─ README.md           ← you are here
├─ docs/               ← documentation and notes
├─ configs/            ← example YAML configs for training/evaluation
├─ data/               ← local data directory (not tracked)
└─ results/            ← result placeholders (not tracked)
```

---

## Usage

This repository currently contains only documentation and configuration templates.  
When the paper is accepted, the following will be added:

- Full training and evaluation code  
- Pretrained model checkpoints  
- Figure and table generation scripts  
- Dataset access or generation instructions  

Until then, you may explore:

```bash
configs/train_example.yaml
docs/README.md
```

These files describe expected configuration fields and experiment organization.

---

## Citation

If you reference this work, please cite the corresponding paper:

```bibtex
@inproceedings{oelhaf_pscc2026,
  title     = {Comparison of Deep Learning Methods for Power System Protection},
  author    = {Oelhaf, Julian and Ghosh, Tamoghna and Kordowich, Georg and Bergler, Christian and Maier, Andreas and Jäger, Johann and Bayer, Siming},
  booktitle = {24th Power Systems Computation Conference (PSCC)},
  year      = {2026},
  note      = {submitted}
}
```

A machine-readable citation is available in [`CITATION.cff`](./CITATION.cff).

---

## License

License information will be finalized prior to the public code release  
(anticipated: MIT or Apache-2.0).

---

## Acknowledgments

This work was conducted at the **Pattern Recognition Lab** (FAU Erlangen-Nürnberg) in collaboration with the **Institute of Electrical Energy Systems (IEES)**.  
Funded by the **German Research Foundation (DFG)** under project 535389056.  

---

**Maintainer:**  
Julian Oelhaf  •  Friedrich-Alexander-Universität Erlangen-Nürnberg  
📧 <julian.oelhaf@fau.de>  
🗓 Last updated: October 2025
