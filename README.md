# Benchmarking Qwen2.5-7B, Qwen2.5-14B, and Llama-3.1-8B on Khayyam Challenge & ParsiNLU Entailment

This repository evaluates three major multilingual LLMs—**Qwen2.5-7B**, **Qwen2.5-14B**, and **Llama-3.1-8B**—on two important Persian NLP benchmarks:

* **Khayyam Challenge** (Persian reasoning & multiple-choice logic)
* **ParsiNLU Entailment** (textual entailment)
* **ParsiNLU Sentiment** (aspect-based sentiment classification)

All evaluations are done in **zero-shot** mode using fully Persian prompts.

---

## 📂 Repository Structure

```
Test-Qwen2.5-7B-and-14B-Llama-3.1-8B-on-Khayyam...
│
├── load_models_and_test.ipynb   # Main evaluation notebook
└── README.md
```

---

## 🧠 Models Evaluated

* **meta-llama/Llama-3.1-8B-Instruct**
* **Qwen/Qwen2.5-7B-Instruct**
* **Qwen/Qwen2.5-14B-Instruct**

All models were loaded in **4-bit quantization** (BitsAndBytes nf4) for efficient GPU usage.

---

# 📊 FINAL RESULTS

## ⭐ 1. ParsiNLU – Entailment (Sent1, Sent2 → e / c / n)

| Model           | Accuracy   |
| --------------- | ---------- |
| **Qwen2.5-14B** | **62.69%** |
| Qwen2.5-7B      | 61.19%     |
| Llama-3.1-8B    | 53.76%     |

📌 **Winner: Qwen2.5-14B**
Qwen-14B gives the strongest semantic reasoning in Persian sentence-pair tasks.

---

## ⭐ 2. ParsiNLU – Sentiment (Aspect-Based, 7-level scale: −3…+3)

| Model        | Accuracy   |
| ------------ | ---------- |
| Llama-3.1-8B | **16.71%** |
| Qwen2.5-7B   | 12.32%     |
| Qwen2.5-14B  | 11.16%     |

📌 All models perform **near random baseline (~14%)**, meaning:

* Aspect-based sentiment is **very hard zero-shot**
* The task is not reliable for comparing model quality
* Better evaluated after fine-tuning

---

## ⭐ 3. Khayyam Challenge – Reasoning (Regex extraction)

| Model           | Accuracy   |
| --------------- | ---------- |
| **Qwen2.5-14B** | **43.00%** |
| Qwen2.5-7B      | 36.44%     |
| Llama-3.1-8B    | 28.50%     |

Comparison with the official Khayyam leaderboard (Regex method):

| Model                   | Accuracy |
| ----------------------- | -------- |
| Human                   | 77%      |
| GPT-4                   | 50%      |
| Claude 3 Haiku          | 42%      |
| **Qwen2.5-14B (yours)** | **43%**  |
| PersianMind             | 28%      |
| XVERSE-13B              | 30%      |
| mGPT                    | 26%      |
| Random                  | 25%      |

📌 ** Qwen2.5-14B result is competitive with Claude Haiku and far above other open models.**

---

# 🏆 Overall Conclusion

### ✔ **Best overall model: Qwen2.5-14B**

* Strongest Persian reasoning
* Strongest Persian entailment
* Competitive with closed-source mid-tier models (Claude Haiku) on Khayyam
* Clear winner for fine-tuning

### ✔ **Qwen2.5-7B is a good lightweight alternative**

* Decent reasoning
* Very close to 14B on entailment
* Good choice for low-resource deployment

### ✔ **Llama-3.1-8B underperforms in Persian**

* Lower reasoning ability
* Weaker entailment
* Slightly better on sentiment, but still poor overall

---

# 🔧 How to Use This Repository

1. Open the evaluation notebook:

```
load_models_and_test.ipynb
```

2. Install requirements:

```bash
pip install transformers accelerate datasets bitsandbytes
```

3. Run the cells to load each model and evaluate on the datasets.

---

# 🎯 Recommended Next Steps

* Fine-tune **Qwen2.5-14B** on Persian corpora for:

  * reasoning
  * summarization
  * paraphrase/NLI
  * medical QA (your specialty)

* Re-run evaluations using:

  * **FSDP / DeepSpeed** for large-batch inference
  * **Full Answer Probability** (Khayyam method #3) for higher accuracy
