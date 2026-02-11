# NLP-Hatchling

Comparative implementations of **BDH (Baby Dragon Hatchling)**, **Transformer**, and **LSTM (RNN)** models evaluated on small-scale NLP benchmarks.

This repository investigates whether BDH can achieve competitive performance with standard Transformer architectures under controlled experimental settings.

---

## Project Goal

To perform a **fair, controlled comparison** between:

- BDH (Baby Dragon Hatchling)
- Transformer Encoder
- LSTM (Recurrent Neural Network)

All models are:

- Matched for parameter count (~2.6M parameters)
- Trained under identical conditions
- Evaluated on the same dataset
- Compared on accuracy, memory usage, and training speed

---

## Benchmark

### Dataset: AG News

- 120,000 training samples
- 7,600 test samples
- 4 classification categories:
  - World
  - Sports
  - Business
  - Sci/Tech

Loaded via HuggingFace `datasets`.

---

## Model Configurations

All models configured to ~2.6M parameters for fairness.

| Model        | Parameters |
|-------------|-----------|
| BDH         | ~2.66M    |
| LSTM        | ~2.62M    |
| Transformer | ~2.71M    |

Embedding dimension: 112  
Training epochs: 5  
Optimizer: AdamW (lr = 3e-4)  
Batch size: 64  
Max sequence length: 128  

---

## Results (Single Seed)

| Model        | Validation Accuracy | Peak GPU Memory | Epoch Time |
|-------------|--------------------|----------------|------------|
| BDH         | 90.07%             | 536 MB         | ~43 sec    |
| LSTM        | 88.76%             | 314 MB         | ~49 sec    |
| Transformer | 90.59%             | 342 MB         | ~40 sec    |

### Observations

- BDH significantly outperforms LSTM.
- BDH achieves accuracy comparable to Transformer.
- Transformer remains slightly superior in final accuracy.
- BDH currently uses higher GPU memory due to custom architecture implementation.

---

## Research Focus

This repository aims to explore:

- Architectural competitiveness of BDH
- Low-resource NLP performance
- Parameter efficiency comparisons
- Controlled experimental methodology

Future experiments will include:

- Multi-seed evaluation
- Low-data regime experiments
- Scaling experiments
- Memory optimization studies

---

## Notes

- All experiments are run with fixed random seeds for reproducibility.

- GPU memory statistics collected using PyTorch CUDA profiling.

- Models are intentionally kept small to allow experimentation on consumer GPUs (e.g., RTX 3060, T4).
  
---

## License
- MIT License

---

## Author

- Tushar Jagannath Jagtap