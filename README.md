# FD-ARL: Feature Disentanglement with Adversarial-Reconstruction Learning for Cross-Subject Auditory Attention Decoding

<p align="center">
  <img src="https://img.shields.io/badge/Conference-ICASSP%202026-blue" alt="Conference">
  </p>

**Authors:** Yuan Liao, Haoqi Hu, Haizhou Li, Siqi Cai

**Affiliations:** The Chinese University of Hong Kong, Shenzhen; Harbin Institute of Technology, Shenzhen

---

## Abstract

The generalization of EEG-based Auditory Attention Decoding (AAD) models across subjects remains a critical bottleneck for practical Brain-Computer Interfaces (BCIs) and next-generation hearing aids. This limitation arises from the high variability between individual subjects' brain signals and the inherent complexity of extracting robust, invariant EEG features. To address this, we propose a novel feature disentanglement framework guided by adversarial and reconstruction learning (FD-ARL). FD-ARL first employs parallel spatio-temporal Transformer encoders to capture contextualized features, which are then decomposed by a disentanglement module into separate task-relevant and subject-specific latent codes. To ensure subject-invariance, the task-relevant code is refined through adversarial training with a gradient reversal layer. Simultaneously, a reconstruction loss ensures the preservation of critical information during disentanglement. Through rigorous leave-one-subject-out cross-validation on the KUL and DTU datasets, FD-ARL achieves state-of-the-art performance, demonstrating a substantial improvement over existing approaches. Our code will be publicly accessible at: https://github.com/Yuan/DART-Net.

## Model Architecture

![The overall structure of our FD-ARL framework](db2.png)
*The overall structure of our cross-subject EEG analysis framework consists of three modules: (a) Feature Extractor module with T-Former and S-Former for temporal and spatial patch embedding, (b) Feature Disentanglement module for separating task-specific and subject-specific representations, and (c) Joint Regularization module.*

## Main Results

### Comparison with State-of-the-Art Methods

| Dataset | Model              | 1-second             | 2-second             |
| :------ | :----------------- | :------------------- | :------------------- |
| **KUL** | CNN                | 56.8 ± 5.58          | 59.5 ± 8.21          |
|         | SSF-CNN            | 59.3 ± 6.69          | 60.8 ± 8.40          |
|         | MBSSFCC            | 62.7 ± 8.08          | 64.7 ± 8.62          |
|         | DGSD               | 63.6 ± 8.00          | --                   |
|         | DBPNet             | 61.1 ± 8.26          | 62.3 ± 7.37          |
|         | DARNet             | 69.9 ± 11.82         | 71.9 ± 13.01         |
|         | **FD-ARL (ours)** | **74.5 ± 14.73** | **74.6 ± 14.04** |
| **DTU** | CNN                | 51.8 ± 3.03          | 52.9 ± 3.42          |
|         | SSF-CNN            | 52.3 ± 3.50          | 53.4 ± 4.16          |
|         | MBSSFCC            | 52.5 ± 4.35          | 53.9 ± 5.80          |
|         | DGSD               | 55.2 ± 4.07          | --                   |
|         | DBPNet             | 55.5 ± 6.33          | 55.8 ± 6.11          |
|         | DARNet             | 55.6 ± 4.13          | 55.6 ± 4.04          |
|         | **FD-ARL (ours)** | **57.7 ± 4.68** | **58.1 ± 4.42** |

### Ablation Study

| Method                 | Accuracy (%) | Change (Δ%) |
| :--------------------- | :----------: | :---------: |
| **FD-ARL** |   **58.1** |     --      |
| FD-ARL w/o Adv         |     56.1     |    -2.0     |
| FD-ARL w/o Recon       |     57.2     |    -0.9     |
| FD-ARL (Base)          |     55.8     |    -2.3     |
| FD-ARL (Temporal-Only) |     56.8     |    -1.3     |
| FD-ARL (Spatial-Only)  |     50.5     |    -7.6     |


## Code Availability

The source code for this paper is available from the corresponding author upon reasonable request.

## Citation

If you find our work useful in your research, please consider citing:
```bibtex
@inproceedings{liao2026fdarl,
  title={{FD-ARL: Feature Disentanglement with Adversarial-Reconstruction Learning for Cross-Subject Auditory Attention Decoding}},
  author={Liao, Yuan and Hu, Haoqi and Li, Haizhou and Cai, Siqi},
  booktitle={2026 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP)},
  year={2026},
  organization={IEEE}
}
```
