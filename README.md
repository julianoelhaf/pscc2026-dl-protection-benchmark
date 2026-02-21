# Deep Learning Architectures for Fault Analysis in Power System Protection Under Varying Operating Conditions

Official implementation accompanying the manuscript:

**Julian Oelhaf, Georg Kordowich, Christian Bergler, Andreas Maier, Johann Jäger, Siming Bayer**

*Deep Learning Architectures for Fault Analysis in Power System Protection Under Varying Operating Conditions*  
Submitted to *Electric Power Systems Research (EPSR)*.

---

## Overview

This repository provides the implementation used in the systematic evaluation of deep learning architectures for fault analysis in transmission power systems.

The study investigates four protection tasks:

- **FD** - Fault Detection  
- **FC** - Fault Classification  
- **FLI** - Fault Line Identification  
- **FL** - Fault Localization  

All models are trained and evaluated under identical preprocessing, cross-validation, and windowing conditions using EMT-simulated voltage and current waveforms.

The focus of this work is a controlled architectural comparison under varying operating conditions.

---

## Dataset

Experiments are conducted on a publicly available EMT simulation dataset:

- 9,022 simulated fault episodes  
- 90 kV double-line transmission topology  
- 6,400 Hz sampling frequency  
- Eight protection relay measurement locations  
- Domain-randomized operating conditions (line parameters, load levels, fault resistance, external grid strength)

Dataset DOI:

<https://doi.org/10.5281/zenodo.18418330>

Please download the dataset from Zenodo and place it in the `data/` directory as described in `data/README.md`.

---

## Evaluated Architectures

The following deep learning architectures are implemented:

- RNN  
- LSTM  
- GRU  
- CNN  
- Dilated CNN  
- Temporal Convolutional Network (TCN)  
- InceptionTime  
- CNN-LSTM hybrid  
- Temporal Fusion Transformer (TFT)

All models are evaluated under identical training settings to enable controlled comparison.

---

## Evaluation Protocol

- 5-fold cross-validation (episode-wise split)  
- Decision windows: 10-50 ms  
- Metrics:
  - Macro-F1 (FD, FC, FLI)
  - Mean Absolute Error (FL)
- Consistent preprocessing and normalization across tasks

Detailed protocol description is provided in the manuscript.

---

## Reproducing Experiments

Example (Fault Detection):

```bash
python experiments/run_fd.py --config configs/fd.yaml
````

Each protection task can be executed via the corresponding script in the `experiments/` directory.

---

## Hardware

Original experiments were conducted on NVIDIA GPUs (RTX 2080 Ti / RTX 3080).
Inference times may differ depending on hardware.

---

## Citation

If you use this repository, please cite:

```
@article{oelhaf2026dl,
  title={Deep Learning Architectures for Fault Analysis in Power System Protection Under Varying Operating Conditions},
  author={Oelhaf, Julian and Kordowich, Georg and Bergler, Christian and Maier, Andreas and Jäger, Johann and Bayer, Siming},
  journal={Electric Power Systems Research},
  year={2026}
}
```

---

## License

MIT License
