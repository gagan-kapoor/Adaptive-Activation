# Novel Activation Function in ResNet18 (CIFAR-10 & Fashion-MNIST)

This project implements a **custom ResNet-18 architecture** using TensorFlow/Keras and introduces a **novel activation function** that combines the strengths of ReLU and Tanh. The goal is to **compare its performance** with standard activations like **ReLU, ELU, and Swish** across two benchmark datasets: **CIFAR-10** and **Fashion-MNIST**.

---

## Project Highlights

- ✅ Novel custom activation function (`TanhReLU`) that smoothly replaces ReLU’s zero-negative gradient issue
- ✅ Modular ResNet-18 architected from scratch using the Functional API
- ✅ Drop-in replacement support for `ReLU`, `ELU`, `Swish`, and **custom activations**
- ✅ Side-by-side benchmarking on **CIFAR-10** and **Fashion MNIST**
- ✅ Auto-logging of **loss**, **accuracy**, and **precision/recall/F1** to `.json` for reproducibility
- ✅ Smoothed training/validation plots and final performance comparison

---

## Custom Activation Function Details

The custom activation function is defined as:
f(x) = x if x ≥ 0
= tanh(x) if x < 0


- This provides smoother gradients in the negative space
- Avoids the “dying ReLU” problem
- More computationally efficient than Swish or Mish

---

## Datasets

- **CIFAR-10**  
  - 60,000 32x32 RGB images  
  - 10 classes

- **Fashion-MNIST**  
  - 70,000 28x28 grayscale images  
  - 10 apparel classes

Both datasets are normalized to `[0, 1]` and loaded via `tensorflow.keras.datasets`.

---
✅ Custom function consistently outperforms or closely matches the best performing standard activation functions with lower variance in validation accuracy.

---

## 📊 Tracked Metrics

- Training/Validation Loss
- Training/Validation Accuracy
- Precision
- Recall
- F1-Score
- JSON logs per run (`relu_cifar10.json`, `swish_fashion.json`, etc.)

---
Why This Matters
Tiny changes like replacing ReLU with better activations can improve real-world model performance.
This project can be adapted for:
Retail image pipelines (like Walmart or Amazon)
Mobile networks (small but fast)
Feature extraction tasks in vision-based AI

Author

Gagan Kapoor

⭐ Like this?
Give a ⭐️ to support this work and help others discover better activations!
