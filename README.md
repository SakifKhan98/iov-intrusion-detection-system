# Intrusion Detection System Using Deep Learning and Transfer Learning for Internet of Vehicles

This repository extends the work presented in the original IEEE ICC 2022 paper:  
**"[A Transfer Learning and Optimized CNN Based Intrusion Detection System for Internet of Vehicles](https://arxiv.org/pdf/2201.11812.pdf)"** by Li Yang and Abdallah Shami.  
We have modernized the codebase, rewritten it in **PyTorch**, and **significantly expanded** the experiments to include:

- Image-based and raw-data-based intrusion detection models
- Vision Transformers (ViT), CNN1D, LSTM, and Transformer-based classifiers
- Model compression (quantization, pruning, knowledge distillation)
- Deployment preparation for edge devices like **Jetson Orin Nano**
- Benchmarking and full cross-model comparison with radar and bar charts

---

## 🚗 Overview

Modern vehicles and IoV systems face increasing threats from cyber-attacks due to limited encryption and authentication mechanisms. This project proposes and benchmarks a variety of deep learning models for both intra-vehicle (CAN bus) and inter-vehicle network intrusion detection, using both raw tabular time-series chunks and image-transformed network packets.

---

## 🧠 Key Features

### ✅ Image-Based Models (RGB-transformed data)

- **Vision Transformer (ViT)** (Newly Implemented)
- VGG16, VGG19
- InceptionV3, InceptionResNetV2
- Xception, ResNet50

### ✅ Raw Tabular Models (27×9 CAN chunks - Self Designed)

- CNN1D, CNN2D
- LSTM
- Transformer Encoder

### ✅ Additional Enhancements

- Model evaluation across accuracy, F1, inference latency, model size, and generalization
- Benchmarking charts (bar, radar/spider plots) using Seaborn
- Benchmarking and deployment pipeline for Jetson Orin Nano

---

## 🧪 Datasets Used

| Dataset               | Description                   | Link                                                                        |
| --------------------- | ----------------------------- | --------------------------------------------------------------------------- |
| **Car-Hacking (CAN)** | Raw CAN bus intrusion samples | [🔗 Download](https://ocslab.hksecurity.net/Datasets/CAN-intrusion-dataset) |

---

## 🛠 File Structure

```
.
├── artifacts/                    ← Trained model weights and artifacts
├── data/                         ← Preprocessed chunk files and sample CSVs
├── demo_models/                         ← Dummy models for demonstration purpose
├── experiments/
│   ├── 1-Data-Preprocessing.ipynb       # Tabular to image & raw CAN chunk conversion
│   ├── 2-CNN_Model_Development.ipynb    # Image-based CNN/ViT training and evaluation
│   ├── 2-Raw-Chunk-CNN-Training.ipynb   # Raw-based 1D/2D CNN, LSTM, Transformer training
│   ├── 3-Ensemble_Models-CAN.ipynb      # Ensemble model fusion (bagging, averaging, concat)
│   └── 3-Model_Comparison.ipynb         # Charts and radar plots for final benchmarking
├── requirements.txt
└── README.md
```

---

## 📊 Results & Visualization

| Model | Type  | Accuracy | F1 Score | Inference Time (ms) | Params | Size (MB) |
| ----- | ----- | -------- | -------- | ------------------- | ------ | --------- |
| ViT   | Image | 99.9%    | 0.998    | 15.2                | 86M    | 345       |
| CNN1D | Raw   | 99.6%    | 0.995    | 2.1                 | 1.2M   | 4.5       |
| LSTM  | Raw   | 99.2%    | 0.992    | 3.4                 | 2.8M   | 10.7      |
| VGG16 | Image | 99.7%    | 0.996    | 10.5                | 134M   | 510       |

📈 See `3-Model_Comparison.ipynb` for grouped bar plots and radar chart comparisons.

## 📦 Requirements

```bash
pip install -r requirements.txt
```

## ✉️ Contact

For questions or collaborations, reach out via:

- [Sakif Khan](mailto:sakifkhan98@gmail.com)
- [Original Authors: Li Yang](mailto:liyanghart@gmail.com) & [Abdallah Shami](mailto:Abdallah.Shami@uwo.ca)

---

## 📚 Citation

If you use this repo or build upon it, please cite the original work:

```
@INPROCEEDINGS{9838780,
  author={Yang, Li and Shami, Abdallah},
  booktitle={ICC 2022 - IEEE International Conference on Communications},
  title={A Transfer Learning and Optimized CNN Based Intrusion Detection System for Internet of Vehicles},
  year={2022},
  pages={2774-2779},
  doi={10.1109/ICC45855.2022.9838780}
}
```
