# LAB-Deep-Learning-Transfer-Learning

![Reboot image](https://user-images.githubusercontent.com/970858/63474771-d6734700-c469-11e9-83bb-9429da563909.png)

## Introduction

In this lab, we will perform sentiment analysis using the **DistilBERT** model, a distilled version of BERT from Hugging Face. We will utilize the provided dataset to fine-tune and evaluate the Transformer-based model to predict the sentiment expressed in the text as positive, neutral, or negative. The goal is to follow a machine learning pipeline that includes data loading, preprocessing, model fine-tuning, and evaluation of the model’s performance across all three sentiment categories. By the end of this lab, we will have a comprehensive understanding of how to train and optimize a multi-class sentiment analysis model using appropriate evaluation metrics.

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

## Iteration 1: Data Load

In the first step of this lab, you will load the dataset containing text samples labeled with three sentiment categories: positive, neutral, and negative. Using `pandas`, load the `Train.csv` and `Test.csv` datasets into DataFrames. Since this dataset has an extra class (neutral), it’s important to inspect the distribution of these three categories to understand how balanced the data is. Display a few rows of the dataset to confirm that the sentiment labels are clearly divided among these three categories.

---

## Iteration 2: Data Exploration

In this step, you will explore the dataset to understand the sentiment distribution and other key features. First, visualize the distribution of the three sentiment labels—positive, neutral, and negative—to check for any class imbalance. Additionally, examine the length of the text samples and generate word clouds for each class to get a sense of the common words. This exploration will help you determine whether any preprocessing or data balancing steps are needed before model training.

---

## Iteration 3: Feature Preprocessing

For the model to handle three-class classification, the text data needs to be preprocessed. You will use a pre-trained Hugging Face tokenizer (in this case, the `AutoTokenizer` for the **DistilBERT** model) to convert the raw text into tokenized sequences that the model can process. Ensure that the labels in the dataset are properly encoded as three distinct categories. After tokenization, pad and truncate the sequences to ensure a consistent input size for the model. Finally, split the data into training, validation, and test sets.

---

## Iteration 4: Load a Pre-trained Model

In this step, you will load a pre-trained **DistilBERT** model that can handle multi-class classification. Instead of binary classification, configure the model to output three classes (positive, neutral, and negative). Use the `TFDistilBertForSequenceClassification` model, which is designed for text classification tasks. Ensure the model is set up for three-class output by specifying `num_labels=3`. Also, load the corresponding tokenizer to ensure consistency in text processing.

---

## Iteration 5: Fine-tune the Pre-trained Model

Once the model is ready, fine-tune it on your dataset to adapt it for three-class sentiment classification. Use the TensorFlow/Keras training loop to fine-tune the model for a few epochs. During training, monitor key metrics such as loss and accuracy for all three classes. Fine-tuning allows the model to adapt its learned parameters to better suit the specific sentiment categories in your dataset.

---

## Iteration 6: Model Evaluation

After the fine-tuning process, evaluate the model’s performance on the test dataset. Generate predictions for positive, neutral, and negative sentiments, and compare these predictions against the actual labels. Evaluate the model using metrics such as accuracy, precision, recall, and F1-score for each of the three classes. Additionally, create a confusion matrix to visualize how well the model distinguishes between positive, neutral, and negative sentiments, highlighting any misclassifications between categories.

---

## Iteration 7: Save and Load the Model

After achieving satisfactory performance, save the fine-tuned model and tokenizer. Use Hugging Face’s `save_pretrained` method to store the model so it can be loaded and used later without the need for retraining. Demonstrate how to load the saved model and tokenizer to make predictions on new text data, which could fall into any of the three categories. This ensures that the model can be used for future sentiment analysis tasks.

---

## Iteration 8: Custom Predictions

In this section, you will test the model with your own comments, rather than the test set data. This gives us an opportunity to see how well the model generalizes to new, unseen data that you can create.

You can replace the default comments with your own text, and the model will predict whether each comment expresses a positive, neutral, or negative sentiment. 

This exercise helps us understand how the fine-tuned model behaves when faced with real-world input data and further validates its performance beyond the dataset we trained and tested on.

----

## Bonus: Handling Class Imbalance

In this bonus section, you will address the class imbalance in the dataset. The dataset contains significantly more positive examples than negative or neutral, which can result in the model being biased toward predicting the majority class.

### Option 1: Class Weights
You can assign different weights to each class during training to give more importance to the minority classes. TensorFlow’s `class_weight` parameter allows you to distribute weights for each class, similar to using a `Sampler` in PyTorch.

### Option 2: Data Augmentation
Alternatively, you can augment the minority class data by generating new text samples. One approach to this is by using synonym replacement, where certain words in the minority class text samples are replaced with their synonyms to create new variations of the data.

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
