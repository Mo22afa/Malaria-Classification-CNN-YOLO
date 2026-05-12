# 🦠 Malaria Classification Using CNN and YOLO

Deep Learning project for malaria cell image classification using:

- Custom CNN built from scratch
- Pretrained YOLO Classification model

---

# 📌 Project Overview

This project classifies malaria cell images into:

- Parasitized
- Uninfected

using two different Deep Learning approaches:

1. CNN built manually using TensorFlow/Keras
2. YOLO pretrained classification model using Ultralytics

The goal is to compare both models in terms of:
- Accuracy
- Performance
- Deep Learning architecture

---

# 📂 Dataset

Dataset used:
- Malaria Dataset from TensorFlow Datasets (TFDS)

Classes:
- Parasitized
- Uninfected

The dataset contains microscopic cell images for malaria detection.

---

# 🧠 CNN Architecture

The CNN model was built from scratch using:

- Conv2D
- MaxPooling2D
- Flatten
- Dense
- Dropout

Architecture:

```python
Conv2D → MaxPooling →
Conv2D → MaxPooling →
Conv2D → MaxPooling →
Flatten →
Dense →
Dropout →
Softmax
```

---

# 🚀 YOLO Classification

A pretrained YOLO Classification model was used:

```python
YOLO("yolo11n-cls.pt")
```

Transfer Learning was applied on the malaria dataset.

---

# 📊 Results

| Model | Accuracy |
|---|---|
| CNN From Scratch | 95.86% |
| YOLO Classification | 96.70% |

---

# 📈 Features

✅ CNN built from scratch  
✅ YOLO pretrained model  
✅ TensorFlow Dataset loading  
✅ Data preprocessing  
✅ Data augmentation  
✅ Accuracy & Loss graphs  
✅ Confusion Matrix  
✅ CNN vs YOLO comparison  
✅ Prediction visualization  

---

# 🛠️ Technologies Used

- Python
- TensorFlow
- Keras
- Ultralytics YOLO
- NumPy
- OpenCV
- Matplotlib
- Scikit-learn

---

# 📷 Sample Predictions

The project visualizes:
- Real labels
- Predicted labels
- Confidence scores

for both CNN and YOLO models.

---

# 📌 Conclusion

The CNN model achieved strong classification performance while being fully built from scratch.

The pretrained YOLO model achieved slightly higher accuracy due to transfer learning and pretrained weights.

YOLO provided:
- Faster convergence
- Better generalization
- Higher accuracy

while CNN helped understand Deep Learning fundamentals and CNN architecture design.

---

# 👨‍💻 Author

Mostafa Abdelwahab

GitHub:
https://github.com/Mo22afa
