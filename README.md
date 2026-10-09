# Arabic-Calligraphy-Classification
Deep learning-based classification of five Arabic calligraphy styles using ResNet50, transfer learning, and the HICMA dataset, achieving 94.60% test accuracy. 


# Deep Learning for Arabic Calligraphy Classification

### Arabic Calligraphy Style Recognition Using ResNet50 and Transfer Learning

A deep learning project focused on automatically classifying five classical Arabic calligraphy styles using convolutional neural networks (CNNs) and transfer learning.

Developed as part of the Deep Learning course at Princess Nourah bint Abdulrahman University.

---

## Project Overview

Arabic calligraphy includes different artistic styles that share complex visual characteristics, making automated recognition challenging.

This project uses a ResNet50-based deep learning model to identify five Arabic calligraphy styles from handwritten images.

The model achieved **94.60% test accuracy** on the HICMA dataset.

## Classification Categories

The model classifies images into five styles:

1. Naskh
2. Thuluth
3. Kufic
4. Diwani
5. Muhaqqaq

---

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| TensorFlow / Keras | Model development and training |
| ResNet50 | Pre-trained CNN architecture |
| Transfer Learning | Feature extraction and fine-tuning |
| NumPy | Numerical operations |
| Matplotlib | Training and evaluation visualizations |
| Scikit-learn | Model evaluation |

---

## Dataset

The project uses the HICMA dataset, containing images of Arabic calligraphy.

Three original subsets were combined into a unified dataset containing **5,031 images**.

### Data Distribution

| Dataset | Images |
|---|---:|
| Training | 3,519 |
| Validation | 753 |
| Testing | 759 |
| Total | 5,031 |

### Preprocessing

- Resized images to 224 × 224 pixels.
- Applied ResNet50 preprocessing.
- Used data augmentation, including flipping, rotation, and zoom.
- Applied class weights to address dataset imbalance.

---

## Model Architecture

The classification system uses transfer learning with ResNet50, pre-trained on ImageNet.

### Architecture Components

1. ResNet50 backbone for feature extraction.
2. Global Average Pooling layer.
3. Dropout layer (0.3).
4. Dense output layer with five units and softmax activation.

### Model Configuration

| Parameter | Value |
|---|---|
| Backbone | ResNet50 |
| Input Shape | 224 × 224 × 3 |
| Output Classes | 5 |
| Loss Function | Sparse Categorical Crossentropy |
| Optimizer | Adam |
| Initial Learning Rate | 0.001 |

---

## Training Strategy

Training was conducted in two stages.

### Stage 1: Feature Extraction

- Froze the ResNet50 backbone.
- Trained the custom classification head.
- Used Early Stopping and Model Checkpoint.
- Best validation accuracy: approximately 96%.

### Stage 2: Fine-Tuning

- Unfroze the top layers of ResNet50.
- Reduced the learning rate to 0.00001.
- Applied Early Stopping to reduce overfitting.

---

## Model Performance

The final model was evaluated using 759 test images.

| Evaluation Metric | Result |
|---|---:|
| Test Accuracy | 94.60% |
| Macro F1-Score | 0.79 |
| Weighted F1-Score | 0.95 |

### Per-Class Performance

| Calligraphy Style | Precision | Recall | F1-Score |
|---|---:|---:|---:|
| Naskh | 0.998 | 0.954 | 0.975 |
| Thuluth | 0.835 | 0.967 | 0.896 |
| Diwani | 0.750 | 0.811 | 0.779 |
| Kufic | 0.833 | 1.000 | 0.909 |
| Muhaqqaq | 1.000 | 0.250 | 0.400 |

---

## Experimental Results

### Training and Validation Performance

![Training Results](results/training_curves.png)

### Confusion Matrix

![Confusion Matrix](results/confusion_matrix.png)

### Misclassified Samples

![Misclassified Samples](results/misclassified_samples.png)

---

## Limitations

- Significant class imbalance in the HICMA dataset.
- Limited training samples for Kufic and Muhaqqaq.
- Visual similarities between certain calligraphy styles.
- Limited test samples for minority classes.

Although overall test accuracy reached 94.60%, minority-class performance requires further improvement.

---

## Future Improvements

- Expand the dataset for underrepresented styles.
- Explore EfficientNet and Vision Transformer architectures.
- Apply advanced data augmentation techniques.
- Improve recognition of visually similar calligraphy styles.
- Investigate alternative feature extraction techniques.

---

## Project Information

**University:** Princess Nourah bint Abdulrahman University

**Course:** Deep Learning

**Dataset:** HICMA

**Model:** ResNet50 with Transfer Learning
