# IMDB Sentiment Analysis with QLoRA Fine-Tuning
## Overview
This project demonstrates sentiment analysis on the IMDB movie reviews dataset using a large language model fine-tuned with QLoRA (Quantized Low-Rank Adaptation). The goal is to compare a baseline pretrained model against a fine-tuned version and analyze the performance improvements achieved through parameter-efficient fine-tuning.

The work is structured as a complete, reproducible machine learning pipeline including data preparation, training, evaluation, visualization, and analysis.

## Dataset
- Name: IMDB Movie Reviews Dataset
- Source: Hugging Face datasets library
- Task: Binary sentiment classification (Positive / Negative)
- Size:
     - Training set: 25,000 reviews
     - Test set: 25,000 reviews

- Format: Plain text movie reviews with sentiment labels

## Model and Methodology
### Baseline Model

A pretrained language model is used in a zero-shot / prompt-based setting to establish a baseline accuracy on the IMDB test set.

### Fine-Tuned Model
Technique: QLoRA (4-bit quantization + LoRA adapters)
Advantages:
- Memory-efficient
- Faster training
- Suitable for limited GPU resources

Only a small subset of parameters is updated during training, while the base model remains frozen.

## Training Setup

Key training configurations:
- Batch size per device: 4
- Gradient accumulation steps: 4
- Learning rate: 2e-4
- Epochs: 1
- Precision: FP16
- Evaluation & checkpointing: Per epoch

The model was trained using the Hugging Face Trainer API. 

## Evaluation Strategy
Metric: Accuracy
Evaluation performed on a subset of the test data for efficiency
Comparison between:
- Baseline pretrained model
- QLoRA fine-tuned model

### Results
- Baseline Accuracy: 23.5%
- Fine-Tuned Accuracy: 49.5%

This represents an improvement of approximately +26 percentage points after fine-tuning.

## Visualizations
The notebook includes the following high-value visual analyses:
1. Training Loss Curve
Demonstrates stable convergence during fine-tuning
2. Baseline vs Fine-Tuned Accuracy Bar Chart
Clearly highlights performance improvement
3. Example Predictions
Qualitative comparison of model behavior on real reviews
4. Confusion Matrix (Optional Analysis)
Shows class-wise prediction behavior and error patterns


## Repository Structure
```
├── notebook.ipynb        # Complete runnable notebook
├── README.md             # Project documentation
```
## Conclusion
This project demonstrates that QLoRA is a practical and effective approach for adapting large language models to downstream NLP tasks such as sentiment analysis. The results validate the value of fine-tuning over baseline usage, both quantitatively and qualitatively.

## Author
Yeabsera Abebe
