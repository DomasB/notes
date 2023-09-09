---
tags:
  - "#quantization #deep-learning #neural-network #precision #ml #neural-network #weights"
---
### What is model quantization?

Model quantization can reduce the memory footprint and computation requirements of deep neural network models. Weight quantization is a common quantization technique that converts a model’s weights from the standard floating-point data type (e.g., 32-bit floats) to a lower precision data type (e.g., 8-bit integers), thus saving memory and resulting in faster inference (through reduced computational complexity). Model quantization can make large models, such as [[LLMs - Large Language Models|LLMs]], more practical for real-world applications at edge devices.

Model quantization can reduce the memory footprint and computation requirements of deep neural network models. Weight quantization is a common quantization technique that converts a model’s weights from the standard floating-point data type (e.g., 32-bit floats) to a lower precision data type (e.g., 8-bit integers), thus saving memory and resulting in faster inference (through reduced computational complexity). Model quantization can make large models, such as [[LLMs - Large Language Models|LLMs]], more practical for real-world applications at edge devices.

To save memory, quantization is used to store weights using lower-precision data types. There are two main quantization techniques:

1. **Post-Training Quantization (PTQ):** This technique converts already trained model weights to lower precision without retraining. While easy to implement, it can lead to performance degradation.
2. **Quantization-Aware Training (QAT):** In this approach, weight conversion is incorporated during pre-training or fine-tuning, enhancing model performance. However, QAT is computationally intensive and requires representative training data.

The focus of the article is on PTQ for reducing parameter precision. The article demonstrates PTQ using both simple and advanced methods on a toy example with a GPT-2 model. The code is available on Google Colab and GitHub.

The article then provides background on floating point number representation in deep learning:

- Floating point numbers use bits to represent values.
- The components include the sign bit (positive/negative), exponent (power of the base), and significand/mantissa (significant digits).
- Different data types are used, such as float32 (FP32), float16 (FP16), and bfloat16 (BF16), each with varying precision and memory usage.
- FP32 offers high precision but high computational and memory demands.
- FP16 is more memory-efficient but can introduce numerical instability and impact model accuracy.
- BF16 balan
- ces precision and range, making it a compromise for deep learning tasks.
