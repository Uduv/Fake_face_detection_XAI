# Fake Face Detection with XAI

This project focuses on detecting fake faces using pre-trained models such as DenseNet and Xception, and Explainable Artificial Intelligence (XAI) techniques to interpret the model's predictions. Specifically, we use **Integrated Gradients** to understand which parts of the input image contribute most to the model's decision.

## Project Overview

1. **Data**: The dataset used for training and validation is the [FaceForensics++](https://github.com/ondyari/FaceForensics) dataset, which contains both real and fake face images.
2. **Models**: Pre-trained DenseNet and Xception models are used for classification.
3. **XAI Technique**: Integrated Gradients is used to explain the model's predictions by attributing the prediction to the input features.

## Models Used

### DenseNet

DenseNet is a convolutional neural network architecture known for its dense connectivity pattern. Each layer is connected to every other layer in a feed-forward fashion, which allows for more efficient parameter usage and better feature reuse.

### Xception

Xception is a convolutional neural network architecture that extends the Inception architecture. It uses a depthwise separable convolution approach, which reduces the number of parameters and computational cost while maintaining high performance.

## Integrated Gradients

**Integrated Gradients** is a model-agnostic method for interpreting the predictions of any differentiable model. It provides a way to attribute the prediction of a model to its input features by approximating the integral of the gradients of the output with respect to the input along a straight path from a baseline instance to the input instance.

**Key Points:**
- **Model-Agnostic**: Can be applied to any differentiable model.
- **Interpretability**: Helps understand which parts of the input (e.g., pixels in an image) are most important for the model's prediction.
- **Baseline**: Uses a baseline input (e.g., a black image) and computes the integrated gradients along a path from the baseline to the input.
- **Accurate Attribution**: Provides a more accurate attribution of the model's prediction compared to other methods like LIME or SHAP.

**Usage in This Project:**
- **Integrated Gradients** is used to explain the predictions of the trained fake face detection models (DenseNet and Xception).
- The method computes the importance of each pixel in the input image for the model's prediction.
- The results are visualized by overlaying the Integrated Gradients heatmap on the original image to highlight the regions that contribute most to the prediction.

## Results

The models are trained using the FaceForensics++ dataset, and the Integrated Gradients visualization helps in understanding the decision-making process of the models. 
