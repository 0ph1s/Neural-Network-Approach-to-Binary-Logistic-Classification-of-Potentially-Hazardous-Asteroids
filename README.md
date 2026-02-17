# 🌌 Asteroid Classification with Neural Networks

This project uses **Artificial Neural Networks** to classify asteroids as **hazardous** or **non-hazardous** based on astronomical data. The network is trained using **binary logistic regression**, **gradient descent**, and automatic hyperparameter tuning via **KerasTuner**.

## 📊 Dataset

The data comes from Kaggle:  
🔗 [NASA Nearest Earth Objects](https://www.kaggle.com/datasets/sameepvani/nasa-nearest-earth-objects?resource=download)

The target variable is `hazardous`, indicating whether the asteroid poses a threat to Earth (`1` for hazardous, `0` for non-hazardous).

### 📥 Features used:
- `est_diameter_min` and `est_diameter_max`: Estimated diameters
- `relative_velocity`: Relative velocity
- `miss_distance`: Closest approach distance
- `absolute_magnitude`: Absolute brightness

## 🧠 Neural Network Architecture

- Densely connected hidden layers with **ReLU**
- Output layer with **sigmoid** activation (probability between 0 and 1)
- Optimizer: **Adam**
- Loss function: **Binary Crossentropy**

The number of layers, neurons per layer, and learning rate are automatically tuned using random search (`KerasTuner`).

## ⚙️ Hyperparameter Tuning

With `KerasTuner`, the following were explored:
- Number of hidden layers: 1 to 3
- Neurons per layer: 8 to 64
- Learning rate (η): between 0.0001 and 0.01 (log scale)

## 🧪 Results

- **Final Accuracy**: 91%
- **AUC (Area Under the ROC Curve)**: 0.91

### 🎯 Classification Report:
| Class         | Precision | Recall |
|---------------|-----------|--------|
| Non-Hazardous | 0.92      | 0.99   |
| Hazardous     | 0.73      | 0.14   |

### 🔢 Confusion Matrix
```
[[16346    93]
 [ 1480   249]]
```

## 📈 Visualizations

- **ROC Curve**  
- **Accuracy per Epoch (training and validation)**  
- **Loss per Epoch (training and validation)**  

## 📚 Mathematical Foundations

This project is backed by a full mathematical analysis:

See the full PDF analysis: [`Neural_Network-3.pdf`](Neural_Network-3.pdf)

## 📁 Project Structure

```
📦 asteroid-classification
├── 📄 neo.csv               # Original dataset
├── 📄 modelo_neural.py      # Project code
├── 📄 Neural_Network-3.pdf  # Mathematical analysis
├── 📄 README.md             # This file
```

## 🚀 How to Run

1. Install dependencies:
```bash
pip install pandas numpy matplotlib scikit-learn tensorflow keras-tuner
```

2. Run the code:
```bash
python modelo_neural.py
```

---

## ✍️ Author

Peterson Carara Junior  
📅 June, 2025

---
