# LAB-Deep-Learning-Transfer-Learning


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

In this step, we will load the **Flowers Dataset**, a collection of flower images provided by TensorFlow. The dataset contains five categories: daisies, dandelions, roses, sunflowers, and tulips. The goal is to extract the dataset, load it into TensorFlow, and split it into training and validation subsets.

### Tasks
1. Download the dataset from TensorFlow’s public URL.
2. Extract the dataset into a structured folder format.
3. Use `image_dataset_from_directory` to load the data, split it into training and validation subsets, and resize the images to a uniform size.
4. Verify the loaded dataset by displaying the total number of images and some samples.

---

## Iteration 2: Data Preprocessing

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

Leverage the pre-trained **MobileNetV2** model for transfer learning. Configure the model to adapt it for the five flower categories.

### Tasks
1. Load the MobileNetV2 model with weights pre-trained on the ImageNet dataset.
2. Freeze the base model layers to retain the pre-trained features.
3. Add custom classification layers:
    - A global average pooling layer.
    - A dense layer with ReLU activation and 1024 neurons.
    - An output layer with softmax activation for five classes.
4. Compile the model with a categorical cross-entropy loss and an appropriate optimizer, use a moderate learning rate.

---

## Iteration 4: Fine-tune the Pre-trained Model

Train and fine-tune the model to adapt the pre-trained features to the flower dataset.

### Tasks
1. Train the custom classification layers while keeping the base model frozen:
    - Set **`epochs`** to `5` for a short training duration.
    - Set **`steps_per_epoch`** to `50` to adjust for the dataset size.
    - Set **`validation_steps`** to `10` to evaluate on a subset of the validation data.
    - Monitor loss and accuracy on both training and validation datasets.
2. Visualize the training process:
    - Plot the training and validation accuracy.
    - Plot the training and validation loss.
---

## Iteration 5: Model Evaluation

Evaluate the model’s performance on the validation dataset using various metrics and visualizations.

### Tasks
1. Compute overall accuracy on the validation set.
2. Generate a confusion matrix to visualize class-wise performance.
3. Calculate precision, recall, and F1-score for each class.

---

## Iteration 6: Save and Load the Model

Save the fine-tuned model to ensure it can be reused without retraining. Demonstrate how to reload the model for predictions.

### Tasks
1. Save the model using TensorFlow’s `model.save` method.
2. Load the saved model to verify that it works correctly.
3. Make predictions on new data using the loaded model.

---

## Iteration 7: Custom Predictions

Once we have our model saved, we will proceed to make predictions with it. For this, in the test_images folder, we have a series of images that we will provide to the model to evaluate its performance with unseen images. 

### Tasks
1. Use the flower images provided in the test_images folder.
2. Preprocess the images to match the input size and format of the model.
3. Use the model to predict the class for each image.
4. Display the images with their predicted labels and confidence scores.

---

## Bonus Iteration: Sentiment Analysis with Transfer Learning

In this bonus task, students will explore how transfer learning can be applied to text data for sentiment analysis. Using a pre-trained text model, such as **DistilBERT** from Hugging Face, the goal is to fine-tune the model on a sentiment analysis dataset to classify text as positive, neutral, or negative.

#### Tasks:

1. **Dataset Preparation**:
   - Download a sentiment analysis dataset (e.g., IMDb, SST-2, or a custom dataset).
   - Preprocess the text data:
     - Tokenize the text using the tokenizer associated with the pre-trained model.
     - Convert the tokens into the format required by the model (e.g., attention masks, input IDs).

2. **Load Pre-trained Model**:
   - Load the pre-trained **DistilBERT** model with a classification head (e.g., `BertForSequenceClassification`).
   - Adapt the output layer to match the number of sentiment classes (e.g., 3 for positive, neutral, and negative).

3. **Fine-tuning**:
   - Freeze the base model initially and train only the classification head for a few epochs.
   - Unfreeze the base model and fine-tune all layers for better adaptation.
   - Use a categorical cross-entropy loss and an appropriate optimizer (e.g., AdamW).

4. **Evaluation**:
   - Evaluate the fine-tuned model on the validation/test dataset.
   - Compute metrics such as accuracy, precision, recall, and F1-score.
   - Generate a classification report and confusion matrix.

5. **Custom Predictions**:
   - Use the fine-tuned model to predict sentiments for custom text inputs.
   - Display the text along with its predicted sentiment and confidence score.

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

