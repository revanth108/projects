**Plant Disease Prediction using CNN**
This project implements a Deep Learning model to identify and classify diseases in various plant species using Convolutional Neural Networks (CNN). The model is trained on the New Plant Diseases Dataset and can recognize 38 different classes of plant leaves, including both healthy and diseased states.
## Project Overview
The primary goal of this project is to provide an automated way to detect plant pathology from images, helping in early intervention for agricultural health.
    • Framework: TensorFlow / Keras
    • Model Architecture: Custom CNN with 10 Convolutional layers.
    • Input Image Size: 128x128 pixels (RGB).
    • Performance: Achieved ~98% training accuracy and ~95% validation accuracy.

## Dataset
The model uses the New Plant Diseases Dataset, which contains over 87,000 images of healthy and diseased crop leaves.
    • Classes: 38 (Apple, Blueberry, Cherry, Corn, Grape, Orange, Peach, Pepper, Potato, Raspberry, Soybean, Squash, Strawberry, and Tomato).
    • Dataset Source: Kaggle - New Plant Diseases Dataset

## Model Architecture
The model is built using a Sequential architecture with the following layers:
    1. Convolutional Layers: Five blocks of dual Conv2D layers with increasing filters (32, 64, 128, 256, 512).
    2. Pooling: MaxPool2D used after each block to reduce spatial dimensions.
    3. Regularization: Dropout layers (0.25 and 0.4) to prevent overfitting.
    4. Dense Layers: A fully connected layer with 1500 neurons followed by a Softmax output layer for the 38 classes.
### Compilation Settings
    • Optimizer: Adam (Learning Rate: 0.0001)
    • Loss Function: Categorical Crossentropy
    • Metrics: Accuracy

## Performance Evaluation
The model was trained for 10 epochs, showing strong convergence:
Metric	Training	Validation
Loss	0.0600	0.1969
Accuracy	98.10%	95.08%
### Key Results
    • High precision and recall across most classes (e.g., Corn and Grape reached nearly 100% accuracy).
    • Slight confusion noted in similar-looking diseases like Tomato Early Blight vs Tomato Late Blight.

## How to Use
    1. Clone the Repository:
       Bash
       git clone https://github.com/revanth108/projects.git
    2. Install Dependencies:
       Ensure you have tensorflow, numpy, pandas, and matplotlib installed.
    3. Run the Notebook:
       Open Train_plant_disease.ipynb to retrain the model or view the preprocessing steps.
    4. Inference:
       The trained model is saved as trained_model.keras. You can load this using tf.keras.models.load_model() to predict new leaf images.

Would you like me to create a requirements.txt file based on the libraries used in this notebook?
