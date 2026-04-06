
 🧠 Named Entity Recognition using BERT

A complete end-to-end **Named Entity Recognition (NER)** project using **BERT (bert-base-cased)** fine-tuned on a CoNLL-style dataset with Hugging Face Transformers.

---

🚀 Overview

Named Entity Recognition (NER) is a Natural Language Processing (NLP) task that identifies and classifies entities in text into predefined categories such as:

* 👤 Person (PER)
* 🏢 Organization (ORG)
* 📍 Location (LOC)
* 🔤 Miscellaneous (MISC)

In this project, we fine-tune a pre-trained **BERT model** for token classification to perform NER efficiently.

---

🛠️ Tech Stack

* **Language:** Python
* **Frameworks:** PyTorch, Hugging Face Transformers
* **Libraries:** Datasets, SeqEval, NumPy
* **Model:** `bert-base-cased`

---

📂 Dataset

The dataset follows a CoNLL-style format:

```json
{
  "tokens": ["EU", "rejects", "German", "call"],
  "tags": [1, 0, 2, 0]
}
```

🏷️ Label Mapping

| ID | Label  |
| -- | ------ |
| 0  | O      |
| 1  | B-PER  |
| 2  | I-PER  |
| 3  | B-ORG  |
| 4  | I-ORG  |
| 5  | B-LOC  |
| 6  | I-LOC  |
| 7  | B-MISC |
| 8  | I-MISC |

---

⚙️ Project Pipeline

1. **Data Loading**

   * Load dataset from JSON format

2. **Preprocessing**

   * Tokenization using BERT tokenizer
   * Align labels with subword tokens

3. **Model Setup**

   * Load pre-trained BERT model for token classification

4. **Training**

   * Fine-tune using Trainer API

5. **Evaluation**

   * Metrics: Precision, Recall, F1-score using SeqEval

---

🧪 Training Configuration

```python
TrainingArguments(
    output_dir="./results",
    do_eval=True,
    logging_steps=100,
    learning_rate=2e-5,
    per_device_train_batch_size=2,
    per_device_eval_batch_size=2,
    num_train_epochs=2
)
```

---

📊 Results

* Achieved strong performance on entity recognition tasks
* Model successfully learns contextual representations
* Handles token-level classification effectively

---

⚠️ Challenges Faced

During development, several real-world issues were encountered:

* ❌ Dataset script deprecation in Hugging Face
* ❌ Dependency conflicts (transformers, datasets, pyarrow, numpy)
* ❌ Token-label alignment issues
* ❌ Memory limitations (MPS / local system)
* ❌ Evaluation errors due to label format

---

🧠 Key Learnings

* Importance of correct label alignment in NER
* Handling subword tokenization in transformers
* Managing ML environments and dependencies
* Debugging training and evaluation pipelines

---

📁 Project Structure

```
├── train.json
├── valid.json
├── test.json
├── ner_bert_notebook.ipynb
├── README.md
```

---

▶️ How to Run

1. Clone the Repository

```bash
git clone https://github.com/your-username/ner-bert-project.git
cd ner-bert-project
```
2. Install Dependencies

```bash
pip install transformers datasets seqeval accelerate torch
```
3. Run the Notebook

```bash
jupyter notebook
```

---

💡 Future Improvements

* Add inference pipeline (predict on custom text)
* Deploy model as API (FastAPI / Flask)
* Experiment with advanced models (RoBERTa, DeBERTa)
* Hyperparameter tuning for better performance

---

🤝 Contributing

Contributions are welcome! Feel free to fork the repo and submit a pull request.

---
⭐ Acknowledgements

* Hugging Face 🤗 for Transformers & Datasets
* CoNLL dataset for NER benchmarking

---

📬 Contact

If you have any questions or suggestions, feel free to connect!

---

⭐ If you found this project helpful, don’t forget to star the repository!**
