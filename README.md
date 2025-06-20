# Generative-Deep-Learning-Model-for-MNIST-like-Digits
A deep learning project for generating handwritten digits using Variational Autoencoders (VAEs) and Generative Adversarial Networks (GANs). Trained on MNIST, this repository includes optimized architectures, KL annealing, mixed precision, and benchmarking insights. GAN achieves 88% image acceptability.

---

## 📌 Project Highlights

- 🔄 **VAE**: Stable, interpretable latent space, smoother digit generation.
- 🎨 **GAN**: Sharper and more varied digit samples, but requires more tuning.
- ⚙️ Includes **KL annealing**, **ReduceLROnPlateau**, **mixed precision training**, and **JIT compilation** for faster training.
- 🧪 Benchmarked on GPU with < 5 min training time per model.

---

## 🏗️ Models Overview

### Variational Autoencoder (VAE)

- **Architecture**:
  - Encoder: 3 Conv layers → Dense → Latent (z_mean, z_log_var)
  - Decoder: Dense → Reshape → 3 Transposed Conv layers
- **Loss**: Binary Cross-Entropy + KL Divergence
- **Optimizer**: AdamW (lr=0.0005)
- **Latent Dim**: 64
- **Training**: 50 epochs, batch size 128
- **Accuracy**: ~76% digit acceptability
- **Parameters**: ~2.3M
- **Training time**: ~5 mins

### Generative Adversarial Network (GAN)

- **Architecture**:
  - Generator: Dense → 4 Transposed Conv → Tanh
  - Discriminator: 2 Conv → Dense → Sigmoid
- **Loss**: Binary Cross-Entropy for both Generator & Discriminator
- **Optimizer**: Adam (lr=2e-4 / 1e-4)
- **Noise Dim**: 100
- **Training**: 100 epochs, batch size 512
- **Accuracy**: ~88% digit acceptability
- **Parameters**: ~6.6M
- **Training time**: ~5 mins

---

## ⚙️ Setup Instructions

### 1. Clone Repository

```bash
git clone https://github.com/abu3qel/Generative-Deep-Learning-Model-for-MNIST-like-Digits.git
cd your-repo
````

### 2. Install Dependencies

Ensure you have Python 3.12.7, then:

```bash
pip install -r requirements.txt
```

Or manually install:

```bash
pip install tensorflow keras matplotlib numpy
```
### Train GAN

---

## 🖼️ Sample Outputs

* Generated images from both models are saved in `generated_outputs/`
* Classifier outputs (ConvNet) provided for evaluation
* VAE produces smoother digits; GAN gives crisper but more volatile results

---

## 📊 Evaluation Summary

| Metric              | VAE     | GAN      |
| ------------------- | ------- | -------- |
| Training Time (GPU) | \~5 min | \~5 min  |
| Parameters          | 2.3M    | 6.6M     |
| Acceptable Digits   | 76%     | 88%      |
| Stability           | High    | Moderate |
| Code Length (lines) | 182     | 163      |

---

## ✍️ Author

Developed by Naif Alaqeili as part of the Generative Deep Learning coursework (March 2025).

---

## License

This project is licensed under the MIT License.

