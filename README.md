# 🧠 Extend-STRAINER-to-Inverse-Imaging-Tasks

## 📘 Overview

This project explores the application of **STRAINER** (Spatially Transferable Implicit Neural Representations) to inverse problems in computational imaging, with a focus on medical imaging tasks such as CT scan reconstruction, denoising, and super-resolution. While traditional methods like CNNs, GANs, and ViTs have made significant progress, they often require large datasets and expensive training. STRAINER offers a more sample-efficient alternative through transfer learning of INRs.

Our work investigates the effectiveness of STRAINER on various inverse problems and proposes an extension using learnable activation functions via **Kolmogorov–Arnold Networks (KAN)** to improve performance in complex scenarios.

---

## 🧪 Methods and Tasks

### ✅ Task 1: Testing STRAINER on Inverse Problems

* **Problems tested**:

  * Denoising (4 Gaussian noise levels)
  * Super-resolution (2× and 4×)
  * CT reconstruction (2 datasets, multiple projection angles)
* **Findings**: STRAINER improves convergence speed but not final image quality. CT reconstruction remains a challenge.

### ✅ Task 2: Encoder Size vs Reconstruction Quality

* Evaluated STRAINER with encoder depths from 1 to 4 layers.
* Applied to both natural and CT image reconstruction tasks.
* **Conclusion**: No clear correlation between encoder size and quality; deeper is not always better.

### ✅ Task 3: Evaluating STRAINER at Scale

* Ran over 100+ experiments on different datasets with:

  * SIREN (random init)
  * STRAINER with 1 training image
  * STRAINER with 10 training images
* **Result**: STRAINER (10-shot) converges fastest, but final reconstruction quality is similar across variants.

### ✅ Task 4: Visualizing STRAINER’s Learning Process

* Added PyTorch hooks to extract and visualize MLP layer activations across training steps.
* Compared feature learning in SIREN vs STRAINER.
* **Insight**: Despite architectural similarities, STRAINER and SIREN learn different features, pointing to architectural limitations in STRAINER.

---

## 🚧 Extension: KAN Integration

STRAINER relies heavily on the choice of activation function. Motivated by its limitations in CT reconstruction, we propose replacing the fixed sine activation with a **learnable function via KAN (Kolmogorov–Arnold Network)**. Preliminary results suggest KAN may provide more flexible representations for complex inverse tasks.


---

## 📁 Project Structure

```
.
├── CT_aligment.ipynb/        # CT image alignment
├── CT_image_STRAINER.ipynb/  # STRAINER on CT reconstruction
├── Dataloader.ipynb/         # Plot  STRAINER at Scale
├── Denoise_STRAINER.ipynb/   # STRAINER on denoising tasks
├── SR_STRAINER.ipynb/        # STRAINER on super-resolution
├── KAN_STRAINER.ipynb/       # STRAINER with learnable KAN activation
└── README.md                 # Project overview (this file)
```

---

## 🚀 What's Next?

* Complete testing of STRAINER+KAN on CT and denoising tasks.
* Investigate other learnable activation strategies.


---

## 📚 Citation

Got it! Here's how you can include the citations for **STRAINER**, **SIREN**, and **KAN** directly in your `README.md` in a clean and professional way:

---

## 📚 References

* Vyas, K., Humayun, A. I., Dashpute, A., Baraniuk, R. G., Veeraraghavan, A., & Balakrishnan, G. (2023).
  **Learning Transferable Features for Implicit Neural Representations**.
  *arXiv preprint arXiv:2311.17124*. [https://arxiv.org/abs/2311.17124](https://arxiv.org/abs/2311.17124)

* Sitzmann, V., Martel, J. N. P., Bergman, A. W., Lindell, D. B., & Wetzstein, G. (2020).
  **Implicit Neural Representations with Periodic Activation Functions**.
  *Advances in Neural Information Processing Systems (NeurIPS)*, 33, 7462–7473.
  [https://proceedings.neurips.cc/paper\_files/paper/2020/file/53c04118f1176ca5dd3e764e3f8d408b-Paper.pdf](https://proceedings.neurips.cc/paper_files/paper/2020/file/53c04118f1176ca5dd3e764e3f8d408b-Paper.pdf)

* Zhang, Q., Liu, Z., Huang, Z., Chen, Y., Darrell, T., Mahadevan, V., & Zhang, X. (2024).
  **Kolmogorov-Arnold Networks**.
  *arXiv preprint arXiv:2401.04077*. [https://arxiv.org/abs/2401.04077](https://arxiv.org/abs/2401.04077)

---

## 🙋 Authors

This project was conducted as part of the Rice University Capstone Program under the guidance of Prof. Guha Balakrishnan. Special thanks to Kushal Vyas for research mentorship and technical insight.

---
