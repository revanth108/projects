
# Brain Tumor Detection using CNN & Transfer Learning

This project focuses on the automated detection of brain tumors from MRI scans using Deep Learning. It compares a custom-built **Convolutional Neural Network (CNN)** against a pre-trained **VGG16** model to identify the presence of malignancies.

## ## Project Overview
Early diagnosis of brain tumors is critical for patient outcomes. This notebook demonstrates a binary classification pipeline—distinguishing between "Tumor" and "No Tumor"—using medical imaging data.

* **Task:** Binary Classification (Tumor vs. No Tumor)
* **Models:** Custom CNN (Base Model) & VGG16 (Transfer Learning)
* **Input:** MRI Scans (Resized to 224x224 RGB)
* **Frameworks:** TensorFlow, Keras, OpenCV, Scikit-learn

---

## ## Dataset
The project utilizes the [Brain MRI Images for Brain Tumor Detection](https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection) dataset from Kaggle.
* **Content:** MRI scans labeled 'yes' (tumor) or 'no' (healthy).
* **Preprocessing:** * Image resizing to $224 \times 224$.
    * Color conversion from BGR to RGB.
    * Pixel normalization to the range $[0, 1]$.
    * Data split: 70% Training / 30% Testing.

---

## ## Model Architectures

### ### 1. Base CNN Model
A sequential architecture featuring:
* Four Convolutional layers with `ReLU` activation.
* `MaxPooling2D` for spatial dimension reduction.
* `Dropout` (0.25) to mitigate overfitting.
* A final `Dense` layer with `Sigmoid` activation for binary output.

### ### 2. Pre-trained VGG16 (Transfer Learning)
* **Base:** VGG16 trained on ImageNet (frozen layers).
* **Head:** Custom fully connected layers, including `Flatten`, `Dropout` (0.5), and `Dense` layers.
* **Advantage:** Leverages features learned from millions of images to improve accuracy on a small medical dataset.

---

## ## Performance Results
The models were evaluated on the test set with the following results:

| Model | Accuracy |
| :--- | :--- |
| **Base CNN Model** | ~81.58% |
| **Pre-Trained VGG16** | **~85.53%** |

### ### Key Observations
* **VGG16** outperformed the base model, demonstrating the effectiveness of transfer learning for medical imaging.
* **Early Stopping** was implemented to prevent overfitting by monitoring `val_loss`.

---

## ## Installation & Usage
1.  **Clone the repository:**
    ```bash
    git clone https://github.com/revanth108/projects.git
    ```
2.  **Install dependencies:**
    ```bash
    pip install tensorflow opencv-python numpy pandas matplotlib seaborn scikit-learn opendatasets prettytable
    ```
3.  **Run the notebook:**
    Open `Brain_tumor_Detection.ipynb` and provide your Kaggle credentials when prompted to download the dataset automatically.
