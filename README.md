# Protein-toxicity-prediction

This project implements a machine learning pipeline for predicting protein toxicity using ProtT5 embeddings and LightGBM classifier. The model achieves high accuracy in distinguishing between toxic and non-toxic proteins.

## Overview

The project uses state-of-the-art protein language models (ProtT5) to generate embeddings from protein sequences, followed by a LightGBM classifier for toxicity prediction. The pipeline includes:

- Protein sequence embedding generation using ProtT5
- Feature selection using Fisher scores
- Hyperparameter optimization for LightGBM
- Comprehensive model evaluation using multiple metrics

## Repository Contents

`Protein_toxixcity_prediction.ipynb`:  
End-to-end pipeline including embedding extraction, model training (LightGBM as the final model), and evaluation.

## Model Architecture

1. **Embedding Generation**
   - Uses the pretrained ProtT5 to generate protein sequence embeddings, which captures rich sequence information learned from large-scale protein databases.

2. **Feature Selection**
   - Implements Fisher score-based feature selection
   - Selects the top 512 most informative features

3. **Classification**
   - LightGBM classifier with optimized hyperparameters:
     - num_leaves: 100
     - n_estimators: 200
     - min_data_in_leaf: 50
     - max_depth: 100
     - learning_rate: 0.1
     - bagging_fraction: 0.5
## Data

The model uses protein sequences in FASTA format, with binary labels indicating toxicity:
- Positive samples: Toxic proteins
- Negative samples: Non-toxic proteins

## Evaluation Metrics

Models are evaluated using the following metrics on the test set:  
- Sensitivity (Recall of the positive class)  
- Specificity (Recall of the negative class)  
- Accuracy  
- Area Under the ROC Curve (AUC) — overall model discrimination ability  
- Matthews Correlation Coefficient (MCC) — balanced measure accounting for all confusion matrix elements

## How to Proceed and Run the Notebook

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
