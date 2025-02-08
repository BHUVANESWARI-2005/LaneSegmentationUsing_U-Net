# Lane Segmentation using U-Net

## About the Project
This project implements **lane segmentation** using a **U-Net** model. The model takes road images as input and generates segmentation masks to identify lane markings. The dataset consists of road images and corresponding color-coded lane masks. The primary goal is to assist autonomous driving systems by detecting lane boundaries accurately.

## Project Implementation
The implementation follows these key steps:

1. **Data Preprocessing**  
   - Load road images and their corresponding segmentation masks.
   - Resize images and masks to a fixed size (256x256).
   - Normalize image pixel values.
   - Convert masks into binary labels (lane vs. background).

2. **Data Augmentation**  
   - Random Horizontal Flip
   - Random Rotation
   - Brightness Adjustment
   - Contrast Enhancement

3. **Model Architecture (U-Net)**  
   - Encoder: Convolutional layers with ReLU activation and max-pooling.
   - Bottleneck: Deeper convolutional layers to learn high-level features.
   - Decoder: Up-sampling layers followed by convolutional layers for precise segmentation.
   - Output Layer: A convolutional layer with softmax activation for pixel-wise classification.

4. **Training the Model**  
   - Loss function: `sparse_categorical_crossentropy`
   - Optimizer: `Adam`
   - Batch Size: `16`
   - Epochs: `20`

## Required Libraries
Ensure the following libraries are installed before running the project:

```bash
pip install numpy opencv-python tensorflow matplotlib tqdm scikit-learn
```

## Results
- The model successfully segments lanes with high accuracy.
- Data augmentation improves model robustness.
- The trained model can be further optimized using hyperparameter tuning.

