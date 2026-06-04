#  Food vs Not Food Text Classification using DistilBERT

A complete Natural Language Processing (NLP) project that demonstrates the end-to-end workflow of:

* Synthetic dataset generation using LLMs
* Dataset hosting on Hugging Face Datasets
* Fine-tuning DistilBERT for text classification
* Model deployment on Hugging Face Hub
* Interactive Gradio demo deployment on Hugging Face Spaces

---

## Project Overview

This project trains a Transformer-based model to classify text into one of two categories:

| Label    | Description                                                         |
| -------- | ------------------------------------------------------------------- |
| food     | Text refers to food, beverages, ingredients, meals, or edible items |
| not_food | Text refers to non-edible objects, places, activities, or concepts  |

### Example Predictions

| Input Text                           | Prediction |
| ------------------------------------ | ---------- |
| "A bowl of hot tomato soup."         | Food       |
| "The laptop battery needs charging." | Not Food   |
| "Fresh mango juice was served."      | Food       |
| "The bicycle is parked outside."     | Not Food   |

---

##  Project Pipeline

```text
LLM Generated Synthetic Data
            │
            ▼
Hugging Face Dataset
            │
            ▼
Tokenization with DistilBERT
            │
            ▼
Fine-Tuning using Transformers
            │
            ▼
Model Evaluation
            │
            ▼
Hugging Face Model Hub
            │
            ▼
Gradio Demo Deployment
```

---

## Repository Structure

```text
food_not_food_distil_bert_uncase_fine_tuned/

├── Creating_Hugging_Face_Synthetic_Dataset.ipynb
├── Finetuned_DistilBert_Food_Not_Food_Classification_Model_Training.ipynb
├── README.md
```

---

## Dataset

The training dataset was synthetically generated using Large Language Models to create diverse examples of food-related and non-food-related text.

### Hugging Face Dataset

https://huggingface.co/datasets/ashutosh-kedar/food_not_food_synthetic_dataset

### Dataset Generation Notebook

https://github.com/ashutosh-kedar/food_not_food_distil_bert_uncase_fine_tuned/blob/main/Creating_Hugging_Face_Synthetic_Dataset.ipynb

---

## Model

The model is based on:

* DistilBERT Base Uncased
* Hugging Face Transformers
* PyTorch

### Hugging Face Model

https://huggingface.co/ashutosh-kedar/finetuned_distil_bert_food_not_food_classification_model

---

## Interactive Demo

Try the model directly in your browser:

### Hugging Face Space

https://huggingface.co/spaces/ashutosh-kedar/HF_Food_Not_Food_Classifier_Demo

The Gradio application allows users to enter any sentence and instantly receive a prediction along with the model confidence score.

---

##  Technologies Used

* Python
* PyTorch
* Hugging Face Transformers
* Hugging Face Datasets
* Hugging Face Hub
* Gradio
* Pandas
* NumPy
* Scikit-Learn

---

##  Usage

### Install Dependencies

```bash
pip install transformers torch
```

### Load Model

```python
from transformers import pipeline

classifier = pipeline(
    "text-classification",
    model="ashutosh-kedar/finetuned_distil_bert_food_not_food_classification_model"
)

result = classifier("A delicious slice of pizza")
print(result)
```

### Example Output

```python
[
  {
    "label": "food",
    "score": 0.998
  }
]
```

---

## Learning Objectives

This project demonstrates:

* Synthetic dataset creation using LLMs
* Dataset publishing on Hugging Face Hub
* Transformer fine-tuning workflows
* Text classification with DistilBERT
* Model deployment and sharing
* Building interactive NLP applications using Gradio

---

## Future Improvements

* Expand dataset size
* Add more food categories
* Collect real-world data for evaluation
* Compare DistilBERT with larger Transformer models
* Deploy using FastAPI and Docker
* Add batch inference support

---

## Author

### Ashutosh Kedar

Passionate about Machine Learning, Deep Learning, Computer Vision, and Natural Language Processing.

### Connect with Me

* GitHub: https://github.com/ashutosh-kedar
* Hugging Face: https://huggingface.co/ashutosh-kedar
* Linkedin : https://www.linkedin.com/in/ashutosh-kedar/

---

##  If You Found This Project Useful

Please consider giving the repository a star and trying out the Hugging Face demo.

Feedback, suggestions, and contributions are always welcome.
