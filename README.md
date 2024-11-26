# LAB-Deep-Learning-Transfer-Learning

![Reboot image](https://user-images.githubusercontent.com/970858/63474771-d6734700-c469-11e9-83bb-9429da563909.png)

## Introduction

In this lab, we will perform image classification using the MobileNetV2 model, a pre-trained neural network from TensorFlow optimized for lightweight and efficient transfer learning. We will use the Flowers Dataset, which contains images of five flower categories: daisies, dandelions, roses, sunflowers, and tulips. By following a structured machine learning pipeline, we will preprocess the dataset, fine-tune the model, and evaluate its performance to classify images into these categories.

---

## Setup Instructions

1. **Clone the repository**:
    ```bash
    git clone https://github.com/your-username/LAB-Deep-Learning-Transfer-Learning.git
    cd LAB-Deep-Learning-Transfer-Learning
    ```

2. **Create a virtual environment and install the required packages**:
    ```bash
    pip install -r requirements.txt
    ```

3. **Start Jupyter Notebook**:
    ```bash
    jupyter notebook
    ```

---

# LAB-Deep-Learning-Transfer-Learning: Flower Classification

---

## Iteration 1: Dataset Loading

### Objective
In this step, we will load the **Flowers Dataset**, a collection of flower images provided by TensorFlow. The dataset contains five categories: daisies, dandelions, roses, sunflowers, and tulips. The goal is to extract the dataset, load it into TensorFlow, and split it into training and validation subsets.

### Tasks
1. Download the dataset from TensorFlow’s public URL.
2. Extract the dataset into a structured folder format.
3. Use `image_dataset_from_directory` to load the data, split it into training and validation subsets, and resize the images to a uniform size.
4. Verify the loaded dataset by displaying the total number of images and some samples.

---

## Iteration 2: Data Preprocessing

### Objective
Preprocess the images to make them suitable for the MobileNetV2 model. This includes normalizing pixel values and applying data augmentation to enhance model generalization.

### Tasks
1. Normalize the pixel values of the images to a range of 0 to 1 using `Rescaling`.
2. Apply data augmentation techniques:
    - Random flips
    - Rotations
    - Zoom
3. Optimize the dataset pipeline with `tf.data`:
    - Shuffle the dataset.
    - Prefetch batches to improve training performance.
4. Confirm that the preprocessing steps are applied correctly by visualizing a batch of augmented images.

---

## Iteration 3: Load a Pre-trained Model

### Objective
Leverage the pre-trained **MobileNetV2** model for transfer learning. Configure the model to adapt it for the five flower categories.

### Tasks
1. Load the MobileNetV2 model with weights pre-trained on the ImageNet dataset.
2. Freeze the base model layers to retain the pre-trained features.
3. Add custom classification layers:
    - A global average pooling layer.
    - A dense layer with ReLU activation.
    - An output layer with softmax activation for five classes.
4. Compile the model with a categorical cross-entropy loss and an appropriate optimizer.

---

## Iteration 4: Fine-tune the Pre-trained Model

### Objective
Train and fine-tune the model to adapt the pre-trained features to the flower dataset.

### Tasks
1. Train the custom classification layers while keeping the base model frozen.
    - Use a moderate learning rate.
    - Monitor loss and accuracy on both training and validation datasets.
2. Unfreeze the base model layers for fine-tuning.
    - Use a smaller learning rate to prevent overfitting.
    - Fine-tune the entire model for a few additional epochs.
3. Visualize the training process:
    - Plot the training and validation accuracy.
    - Plot the training and validation loss.

---

## Iteration 5: Model Evaluation

### Objective
Evaluate the model’s performance on the validation dataset using various metrics and visualizations.

### Tasks
1. Compute overall accuracy on the validation set.
2. Generate a confusion matrix to visualize class-wise performance.
3. Calculate precision, recall, and F1-score for each class.
4. Identify any misclassifications and analyze potential causes.

---

## Iteration 6: Save and Load the Model

### Objective
Save the fine-tuned model to ensure it can be reused without retraining. Demonstrate how to reload the model for predictions.

### Tasks
1. Save the model using TensorFlow’s `model.save` method.
2. Load the saved model to verify that it works correctly.
3. Make predictions on new data using the loaded model.

---

## Iteration 7: Custom Predictions

### Objective
Test the model on custom images to validate its generalization on unseen data.

### Tasks
1. Provide a set of custom flower images.
2. Preprocess the images to match the input size and format of the model.
3. Use the model to predict the class for each image.
4. Display the images with their predicted labels and confidence scores.

---

## Submission
Once you have completed your analysis and visualizations, push your Jupyter notebook to your forked GitHub repository. Ensure that your final submission includes narratives explaining your visualizations and insights.

```bash
$ git add .
$ git commit -m "done"
$ git push origin main
```

Then create a Pull Request!!

## Additional Resources

- [ ]()
- [ ]()
- [ ]()
- [ ]().
- [ ]().

![happy_coding](https://user-images.githubusercontent.com/970858/63899010-c23fc480-c9ea-11e9-84a2-542907e42362.png)
