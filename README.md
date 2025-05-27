# Deep Deblur

## Overview

**Deep Deblur** is an advanced deep learning project for removing motion blur from images.  
The model uses frequency mining, adaptive feature fusion, and BitNet Transformers to restore sharp, clear images from blurry inputs.  
This project is inspired by the AdaIR and DeblurDiNAT repositories.

---

## Key Features

- **Frequency-aware processing:** Enhances only the most affected frequency bands, not the whole image.
- **Lightweight Gated Feature Fusion:** Combines details and overall context, preserving edge sharpness and global clarity.
- **BitNet Transformers:** Super-efficient Transformer backbone using 1-bit quantization for fast, large-image processing.
- **Custom Loss Functions:** Uses a combo of Charbonnier, edge, and contrastive losses for real, artifact-free restoration.
- **Strong Data Augmentation:** Handles a wide variety of blurring, rotation, and distortion scenarios.

---

## Dataset

- Uses the **GoPro dataset**: High-quality, paired blurry/sharp images with realistic motion blur.
- For research only. Download instructions are in the repo.

---

## Results

| Method      | PSNR  | SSIM   |
|-------------|-------|--------|
| NAFNet      | 26.53 | 0.808  |
| HINet       | 26.12 | 0.788  |
| MPRNet      | 26.87 | 0.823  |
| DGUNet      | 27.25 | 0.837  |
| MIRNetV2    | 26.30 | 0.799  |
| SwinIR      | 24.52 | 0.773  |
| Restormer   | 27.22 | 0.829  |
| **Ours**    | **28.38** | **0.9175** |

---

## Quick Start

1. **Clone the repo**
    ```bash
    git clone https://github.com/yourusername/deep-deblur.git
    cd deep-deblur
    ```

2. **Install requirements**
    ```bash
    pip install -r requirements.txt
    ```

3. **Download GoPro dataset** (link in README or ask for instructions).

4. **Training**
    ```bash
    python train.py
    ```

5. **Testing**
    ```bash
    python test.py --ckpt_name best_model.pth
    ```

---

## Files

- `options.py`: Configuration, hyperparameters, and paths.
- `train.py`: Training loop with PyTorch Lightning.
- `test.py`: Testing and evaluation.
- `models.py`, `losses.py`, `utils.py`: Core model and utility functions.
- `assets/`: (Optional) Example images.

---

## References & Credits

- [AdaIR](https://github.com/c-yn/AdaIR)
- [DeblurDiNAT](https://github.com/HanzhouLiu/DeblurDiNAT)
- GoPro Dataset: [Download](https://seungjunnah.github.io/Datasets/gopro)


