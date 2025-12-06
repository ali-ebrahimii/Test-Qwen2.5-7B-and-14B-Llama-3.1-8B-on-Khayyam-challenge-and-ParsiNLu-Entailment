# Benchmarking Qwen2.5-7B, Qwen2.5-14B, and Llama-3.1-8B on Khayyam Challenge & ParsiNLU Entailment

This repository contains experiments for evaluating modern multilingual LLMs — **Qwen2.5 (7B & 14B)** and **Llama-3.1-8B** — on two major Persian NLP benchmarks:

* **Khayyam Challenge (Persian reasoning & exam-style MCQA)**
* **ParsiNLU Entailment Task**

The goal is to measure model performance on Persian logical reasoning, entailment understanding, and general NLU capabilities.

---

## 📂 Repository Structure

```
Test-Qwen2.5-7B-and-14B-Llama-3.1-8B-on-Khayyam...
│
├── load_models_and_test.ipynb     # Main notebook to load models and run evaluations
└── README.md                      # Documentation
```

---

## 🚀 What This Project Does

* Loads **Qwen2.5-7B**, **Qwen2.5-14B**, and **Llama-3.1-8B** using HuggingFace Transformers.
* Runs them on:

  * **Khayyam Challenge** (Persian reasoning & exam questions)
  * **ParsiNLU Entailment** (textual entailment classification)
* Computes:

  * Accuracy
  * Model predictions
  * Error cases (optional)
* Enables reproducible comparison across models and datasets.

---

## ▶️ How to Use

1. Open the notebook:

   ```
   load_models_and_test.ipynb
   ```

2. Install required libraries:

   ```bash
   pip install transformers accelerate datasets
   ```

3. Make sure you have access to the required models on HuggingFace.

4. Run cells to:

   * Load each model
   * Load datasets
   * Evaluate and compare accuracy

---

## 📊 Benchmarks

### **1. Khayyam Challenge**

* Multiple-choice QA for Persian logic & reasoning
* Inspired by MMLU-style evaluations

### **2. ParsiNLU Entailment**

* Classifies: **entailment**, **contradiction**, **neutral**
* Standard Persian NLI evaluation

---

## 🎯 Purpose

This repository is useful for:

* Persian NLP research
* Evaluating foundation LLMs on Farsi datasets
* Model selection for fine-tuning
* Academic experiments and benchmarking
