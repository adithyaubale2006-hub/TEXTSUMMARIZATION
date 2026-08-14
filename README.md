# Text Summarization using PEGASUS

##  Overview

This project implements an **abstractive text summarization system** using the **PEGASUS Transformer model** from Hugging Face.

The model is fine-tuned on the **SAMSum dialogue summarization dataset** to generate concise summaries from conversations.

##  Technologies Used

* Python
* PyTorch
* Hugging Face Transformers
* Hugging Face Datasets
* PEGASUS
* SAMSum Dataset
* NLTK
* Evaluate
* ROUGE
* Google Colab / GPU

##  Model

**Model:** PEGASUS

PEGASUS is a Transformer-based sequence-to-sequence model designed specifically for abstractive summarization.

The project uses:

```text
google/pegasus-cnn_dailymail
```

and fine-tunes it for the SAMSum dialogue summarization task.

##  Dataset

**SAMSum Dataset**

The dataset contains conversations along with human-written summaries.

Example:

```text
Dialogue
Person A: Are you coming to the meeting?
Person B: Yes, I'll be there at 10.

Summary
Person B will attend the meeting at 10.
```

##  Project Workflow

```text
SAMSum Dataset
      ↓
Data Preprocessing
      ↓
Tokenization
      ↓
PEGASUS Model
      ↓
Fine-Tuning
      ↓
Text Generation
      ↓
ROUGE Evaluation
      ↓
Generated Summary
```

##  Key Steps

### 1. Load Libraries

The project uses Hugging Face Transformers and Datasets along with PyTorch, NLTK and Evaluate.

### 2. Load Dataset

The SAMSum dataset is loaded using:

```python
load_dataset("knkarthick/samsum")
```

### 3. Tokenization

Dialogue and summary text are converted into token IDs.

* Input dialogue → input IDs
* Summary → labels
* Maximum input length → 1024
* Maximum summary length → 128

### 4. Fine-Tuning

PEGASUS is fine-tuned using Hugging Face's `Trainer` and `TrainingArguments`.

### 5. Evaluation

The generated summaries are evaluated using the **ROUGE metric**.

### 6. Prediction

The trained model is loaded and used to generate summaries for unseen dialogues.

##  Example

### Input

```text
A: Did you finish the project?
B: Almost. I just need to complete the final section.
A: Okay, let me know when it's ready.
```

### Generated Summary

```text
B is almost finished with the project and will complete the final section.
```

##  Evaluation

The project uses **ROUGE** to compare generated summaries against reference summaries.

ROUGE evaluates the similarity between the generated summary and the human-written reference summary.

##  Project Structure

```text
Text-Summarization/
│
├── TEXTSUMMARIZATION.ipynb
└── README.md
```

##  Requirements

Install the required libraries:

```bash
pip install transformers datasets evaluate nltk torch
```

##  How to Run

1. Open `TEXTSUMMARIZATION.ipynb`
2. Run the notebook in Google Colab or another GPU-enabled environment.
3. Install the required dependencies.
4. Load the SAMSum dataset.
5. Load the PEGASUS model.
6. Run preprocessing and tokenization.
7. Fine-tune the model.
8. Evaluate using ROUGE.
9. Generate summaries using the trained model.

##  Note

This project uses a Transformer model and GPU acceleration is recommended. Model loading and fine-tuning can take significant time and memory.

The notebook is primarily intended as a **learning and demonstration project for Transformer-based text summarization**.

##  Learning Outcomes

Through this project, I learned:

* How sequence-to-sequence Transformer models work in practice
* How to use Hugging Face Transformers
* How to load and preprocess NLP datasets
* How to tokenize text for Transformer models
* How to fine-tune a pretrained model
* How to use `Trainer` and `DataCollatorForSeq2Seq`
* How to evaluate summarization using ROUGE
* How to generate summaries using a fine-tuned model

##  Author

**Adithya Ubale**

B.Tech | CSE
