
# Multi-model Text Summarizer

This project is a **multi-model text summarizer** built with Python using:
- [T5-small](https://huggingface.co/t5-small) (encoder-decoder transformer)
- [GPT-2 small](https://huggingface.co/gpt2) (decoder-only transformer)

It fine-tunes both models on a summarization dataset and provides:
✅ Training & validation loops  
✅ ROUGE score evaluation on test data  
✅ A Gradio-powered interactive web interface  

---

## 🚀 Features

- Fine-tune **T5-small** and **GPT-2 small** on custom datasets (`train.xlsx`, `validation.csv`, `test.csv`)
- Evaluate summaries using ROUGE-1, ROUGE-2, ROUGE-L
- Compare both models’ performance
- Generate summaries via a **Gradio web UI**

---

## 🛠️ Setup

1️⃣ **Install required libraries**

```bash
pip install transformers datasets rouge_score accelerate gradio pandas tqdm
```

2️⃣ **Prepare dataset**

Make sure you have:
- `train.xlsx` → will be converted to `train.csv`
- `validation.csv`
- `test.csv`

The expected columns are:
- `article`
- `highlights`

---

## 📂 Files

| File                    | Description                                      |
|-------------------------|--------------------------------------------------|
| `train.xlsx`            | Original Excel training data                     |
| `train.csv`             | Converted CSV training data                      |
| `validation.csv`        | Validation data                                  |
| `test.csv`             | Test data                                        |
| `summarizer.py` (or notebook) | Main training and evaluation script             |
| `README.md`             | This project overview file                       |

---

## 🏃‍♂️ How to Run

### Train models

```bash
# Inside notebook or script
python summarizer.py
```

### Launch Gradio app

After training, a Gradio web interface will launch at:
```
http://localhost:7860/
```

Use it to input custom text and choose between T5-small or GPT-2 summarization.

---

## 📊 Evaluation

We use ROUGE metrics to compare model performance:
- ROUGE-1 (unigram overlap)
- ROUGE-2 (bigram overlap)
- ROUGE-L (longest common subsequence)

Results are printed after testing on the test set.

---

## ⚙️ Models Used

| Model         | Type                  | Details                                 |
|---------------|-----------------------|----------------------------------------|
| T5-small      | Encoder-Decoder       | Pretrained for text-to-text tasks      |
| GPT-2 small   | Decoder-only (causal) | Pretrained for text generation         |

---

## ✨ Example

| Input Text                               | Model     | Summary Output                          |
|------------------------------------------|-----------|-----------------------------------------|
| Long article or document text...         | T5-small  | Shortened key points summary...         |
| Long article or document text...         | GPT-2     | Condensed generated summary...          |

---

## 🤖 Requirements

- Python 3.7+
- GPU (recommended) for faster training
- Libraries: `transformers`, `torch`, `gradio`, `rouge_score`, `pandas`

---

## 🏗 Future Improvements

- Add BART or Pegasus models
- Include multilingual summarization
- Integrate model checkpoints saving/loading
- Add custom hyperparameter configuration

---

## 💬 Contact

For questions or collaboration, feel free to reach out!
