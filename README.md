# Protein-toxicity-prediction
This repository implements a machine learning pipeline to predict protein toxicity from amino acid sequences using ProtT5 embedding vectors and a LightGBM classifier.

## 🔍 Project Overview
Predicting toxic proteins is crucial for ensuring drug safety and advancing biological research. This project transforms protein sequences into rich numerical representations using the ProtT5 protein language model, then trains classical machine learning classifiers to classify proteins into toxic and non-toxic classes.

## 📁 Repository Contents
``Protein_toxixcity_prediction.ipynb``:
End-to-end pipeline including embedding extraction, model training (LightGBM as the final model), and evaluation.

## 🧬 Feature Representation
ProtT5 Embeddings:
Protein sequences are encoded into dense vector embeddings using ProtT5, which captures rich sequence information learned from large-scale protein databases.

## Classifier Model
- LightGBM (final chosen model based on performance)

## 📏 Evaluation Metrics
Models are evaluated using the following metrics on the test set:
- Sensitivity (Recall of the positive class)
- Specificity (Recall of the negative class)
- Accuracy
- Area Under the ROC Curve (AUC) — overall model discrimination ability
- Matthews Correlation Coefficient (MCC) — balanced measure accounting for all confusion matrix elements

## 🚀 How to Proceed and Run the Notebook

1. **Clone the repository:**

```bash
git clone https://github.com/faezesarlifar/Protein-toxicity-prediction.git
cd Protein-toxicity-prediction
```

2. Launch Jupyter Notebook:

```bash
jupyter notebook Protein_toxixcity_prediction.ipynb
```

4. **Extract ProtT5 Embedding Vectors:**

- Run the cell(s) that extract ProtT5 embeddings from protein sequences using the provided command.  
- Embeddings will be saved as `.h5` files to disk.  
- GPU acceleration is recommended for faster extraction.

> **⚠️ Note:** You can also use the already extracted embedding vectors available in the `data` folder:  
> `negative_main_emb_ProtT5.h5` and `posititive_main_emb_ProtT5.h5`.

5. **Specify Embedding Location:**

- Update the notebook cell that loads embedding vectors to point to the `.h5` file(s) you generated or to the provided files in the `data` directory.

6. **Run Training and Evaluation Cells:**

- Train the LightGBM classifier using the loaded embeddings.  
- Evaluate performance with sensitivity, specificity, accuracy, AUC, and MCC. 




