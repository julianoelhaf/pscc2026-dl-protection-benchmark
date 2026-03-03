# Deep Learning Models for Fault Analysis in Power System Protection
This repository accompanies the article:

**Deep Learning Models for Fault Analysis in Power System Protection**  
Julian Oelhaf, Georg Kordowich, Christian Bergler, Andreas Maier, Johann Jäger, Siming Bayer  
*Electric Power Systems Research (2026)*

---

## Overview

This work presents a systematic evaluation of deep learning architectures for transmission-level fault analysis under varying operating conditions.

Four protection tasks are investigated:

- **Fault Detection (FD)**
- **Fault Classification (FC)**
- **Fault Line Identification (FLI)**
- **Fault Localization (FL)**

Nine neural network architectures are compared under identical preprocessing, windowing, and cross-validation conditions to enable controlled architectural assessment.

The study focuses on how model structure influences accuracy, robustness, and inference time when operating on electromagnetic transient (EMT) voltage and current waveforms.

---

## Dataset

Experiments are conducted using a publicly available EMT simulation dataset:

**Zenodo DOI:**  
<https://doi.org/10.5281/zenodo.18418330>

The dataset contains:

- 9,022 simulated fault scenarios  
- 90 kV double-line transmission topology  
- 6.4 kHz sampled voltage and current waveforms  
- Eight protection relay measurement locations  
- Domain-randomized operating conditions  

Please download the dataset from Zenodo and configure the local dataset path as described below.

---

## Reproducing the Experiments

The repository provides the training and evaluation scripts used in the paper.

After downloading the dataset, set the dataset directory in:

```text
config/dataset/hv_double_line_90kv.yaml
````

Example run:

```bash
python src/dl_fault_analysis/scripts/run_dl_experiment.py
````

Experiments are controlled via configuration files. All models and tasks evaluated in the paper can be reproduced using the provided configurations.

---

## Environment

- Python ≥ 3.10
- PyTorch-compatible environment (GPU optional)

Install via:

```bash
conda activate dl-fault-analysis && pip install -e .
```

---

## Scope and Limitations

The presented results are based on controlled EMT simulation of a fixed transmission topology with domain-randomized operating conditions.

The study provides a comparative architectural analysis under consistent conditions.
It does not claim universal generalization to unseen grid topologies or field-recorded data.

---

## Citation

If you use this work, please cite:

```bibtex
@article{oelhaf2026dl,
  title={Deep Learning Models for Fault Analysis in Power System Protection},
  author={Oelhaf, Julian and Kordowich, Georg and Bergler, Christian and Maier, Andreas and J\"{a}ger, Johann and Bayer, Siming},
  journal={Electric Power Systems Research},
  year={2026}
}
```

---

## License

MIT License
