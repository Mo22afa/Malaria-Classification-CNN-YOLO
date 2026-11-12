# Malaria Cell Classification Using CNN and YOLO

A deep learning project that classifies microscopic malaria cell images into two categories:

- **Parasitized**
- **Uninfected**

The project implements and compares a custom Convolutional Neural Network (CNN) built from scratch with a pretrained YOLO11n classification model fine-tuned on the malaria dataset.

## Project Overview

The project explores two image-classification approaches:

1. **Custom CNN:** built with TensorFlow and Keras.
2. **YOLO11n Classification:** initialized from pretrained weights and trained on the malaria dataset using Ultralytics.

The comparison focuses on validation accuracy and the models' classification behavior.

## Dataset

- **Source:** Malaria dataset provided by TensorFlow Datasets (TFDS).
- **Total images:** 27,558.
- **Classes:** Parasitized and Uninfected.
- **Image size used by the models:** 128 × 128 pixels.
- **Split in the latest run:** 80% training (22,046 images), 10% validation (2,756 images), and 10% held-out testing (2,756 images).

The same 80/10/10 split is used for both models.

> **Evaluation note:** The latest Colab run (November 12, 2026) uses a separate test split. The GitHub notebook and historical figures may still show earlier experiment outputs until the new Colab notebook is uploaded. The held-out test results below come from that new run.

## Model 1: Custom CNN

The CNN was designed and trained from scratch using TensorFlow/Keras.

### Architecture

```text
Input (128 × 128 × 3)
        ↓
Data Augmentation
        ↓
Conv2D (32) → MaxPooling
        ↓
Conv2D (64) → MaxPooling
        ↓
Conv2D (128) → MaxPooling
        ↓
Flatten
        ↓
Dense (128) → Dropout (0.5)
        ↓
Softmax (2 classes)
```

### Training configuration

- Optimizer: Adam
- Loss: Sparse Categorical Crossentropy
- Batch size: 32
- Epochs: 10
- Data augmentation: random horizontal flip, rotation, and zoom

## Model 2: YOLO Classification

The project uses the pretrained `yolo11n-cls.pt` classification model from Ultralytics.

The TFDS images are exported into the directory structure required by Ultralytics, with separate training and validation folders for each class.

### Training configuration

- Model: YOLO11n-cls
- Image size: 128 × 128
- Batch size: 32
- Epochs: 10
- Dataset split in latest run: 22,046 training, 2,756 validation, and 2,756 test images

## Results

### Latest run — held-out test set (November 12, 2026)

The following values were read from the saved Google Colab notebook output after the dataset was split 80/10/10. They are **test-set** accuracy values, not validation accuracy.

| Model | Test Accuracy |
|---|---:|
| Custom CNN | **95.57%** |
| YOLO11n Classification | **96.88%** |

YOLO11n scored **1.31 percentage points higher** in this run. These measurements are based on the 2,756-image test split. Further evaluation is needed before any real-world or clinical use.

### Historical run — validation set (80/20)

These are the earlier validation measurements and must **not** be presented as the new test results:

| Model | Earlier Validation Accuracy |
|---|---:|
| Custom CNN | 95.86% |
| YOLO11n Classification | 96.68% |

### Visual Results

The figures below were generated from the **earlier 80/20 run**. The latest 80/10/10 run has new plots in the user's saved Colab notebook; these historical images remain for reference until the notebook and updated visuals are published.

#### Historical CNN training curves

![Previous CNN training accuracy](results/cnn_training_accuracy.png)

![Previous CNN training loss](results/cnn_training_loss.png)

#### Historical confusion matrices

![Previous CNN confusion matrix](results/cnn_confusion_matrix.png)

![Previous YOLO confusion matrix](results/yolo_confusion_matrix.png)

#### Historical sample predictions

![Previous CNN sample predictions](results/cnn_sample_predictions.png)

![Previous YOLO sample predictions](results/yolo_sample_predictions.png)

#### Historical comparison chart

![Previous CNN vs YOLO validation accuracy](results/cnn_vs_yolo_accuracy.svg)

## Features

- Custom CNN architecture built from scratch
- Pretrained YOLO11n classification model
- TFDS dataset loading and preprocessing
- Image resizing and normalization
- Data augmentation for CNN training
- Training and validation accuracy/loss curves
- Confusion matrices
- Sample predictions with confidence scores
- CNN and YOLO validation-accuracy comparison

## Technologies Used

- Python
- TensorFlow
- Keras
- TensorFlow Datasets
- Ultralytics YOLO
- OpenCV
- NumPy
- Matplotlib
- Scikit-learn

## How to Run

The project is provided as a Jupyter Notebook.

1. Open **[CNN and YOLO.ipynb](./CNN%20and%20YOLO.ipynb)** in Google Colab or a Jupyter environment.
2. Install the required packages if they are not already available:

   ```bash
   pip install -r requirements.txt
   ```

3. Run the notebook cells in order. The notebook downloads the malaria dataset through TensorFlow Datasets and prepares the directory structure needed for YOLO training.

YOLO training can require a GPU and sufficient storage because the dataset images are exported to disk.

## Conclusion

In the latest held-out test run (80/10/10), the custom CNN achieved **95.57% test accuracy**, while YOLO11n Classification achieved **96.88% test accuracy**, a difference of **1.31 percentage points**. These results were recorded in the user's Colab notebook and have not been independently reproduced.

## Author

**Mostafa Abdelwahab**

- GitHub: [Mo22afa](https://github.com/Mo22afa)
- Repository: [Malaria Classification Using CNN and YOLO](https://github.com/Mo22afa/Malaria-Classification-CNN-YOLO)

---

*This project is for educational and research purposes. It is not a medical diagnostic tool.*
