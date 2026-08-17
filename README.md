# PBMRNet

Official implementation of **PBMRNet: A Periodic Baseline-Guided Multi-Branch Residual Network for Smart Meter Data Imputation**.

PBMRNet is designed for missing-value reconstruction in smart-meter load data. The model combines a periodic baseline with local, periodic, and global temporal modeling, and uses gap-aware adaptive fusion to reconstruct missing load values under different missing conditions.

## Repository Structure

```text
PBMRNet/
├── datasets/
├── requirements.txt
└── train_pbmrnet.py
```

- `datasets/`: training, validation, and test data used in the experiments.
- `requirements.txt`: Python dependencies required to run the code.
- `train_pbmrnet.py`: main training and evaluation script for PBMRNet.

## Installation

Clone the repository and enter the project directory:

```bash
git clone <repository-url>
cd PBMRNet
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

It is recommended to use a Python virtual environment or Conda environment.

## Dataset

The processed datasets used for training, validation, and testing are provided in the `datasets/` directory.

Please keep the dataset directory structure unchanged so that the training script can load the data correctly.

## Training and Evaluation

Run the following command directly from the project root:

```bash
python train_pbmrnet.py
```

The script performs model training and evaluation using the provided dataset and the default experimental configuration.

## Reproducibility

To reproduce the reported experiments:

1. Install the dependencies in `requirements.txt`.
2. Keep the provided files in their original directory structure.
3. Run:

```bash
python train_pbmrnet.py
```

## Method Overview

PBMRNet contains the following main components:

- **Periodic Baseline:** constructs an initial reference from available same-slot observations across different days.
- **Local Branch:** captures short-range temporal continuity around missing positions.
- **Periodic Branch:** models same-slot cross-day dependencies.
- **Global Branch:** captures broader temporal context over the input window.
- **Gap-Aware Adaptive Fusion:** dynamically adjusts the contribution of different temporal branches according to the missing condition and observation availability.

The final missing-value reconstruction is obtained by adding the adaptively fused residual correction to the periodic baseline.

## Citation

If you find this code useful for your research, please cite our paper:

```bibtex
@article{PBMRNet,
  title   = {PBMRNet: A Periodic Baseline-Guided Multi-Branch Residual Network for Smart Meter Data Imputation},
  author  = {Liang He and Roman Belyaevsky},
  journal = {To be updated},
  year    = {2026}
}
```

The citation information can be updated after the paper is formally published.

## License

Please add the license information for this repository according to your intended open-source license.
