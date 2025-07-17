# Lyra_Immo

## 🏡 Objective
Fine-tuned GPT-3.5-turbo model for real estate valuation based on structured parameters.

## 🧬 Model Reference

The current fine-tuned model (v2) is available under the following ID:

ft:gpt-3.5-turbo-0125:personal:lyra-immo:BuL5kHFV

This is the **second and corrected version** of the Lyra_Immo model.  
It replaces the previous version which was trained on a duplicated dataset and lacked true generalization.

This updated model integrates a reliable valuation logic based on structured parameters (surface, type, condit

## 📥 Input Data
- Surface area (m²)
- Property type (house, apartment, etc.)
- Overall condition (new, good, average, renovation needed)
- Location (region, rural / urban / suburban)
- Implicit coefficients (from scoring table)

## 🧾 Output
- Estimated property value (in euros)
- Contextualized response (professional tone, fluent)

## 🔍 Training Details
- 150 training examples (`datasets/dataset_lyra_immo.jsonl`)
- 30 validation examples (`datasets/validation_lyra_immo.jsonl`)
- Semi-natural prompts with structured logic
- Hyperparameters: `3 epochs`, `batch size = 1`, `learning rate multiplier = 2`

## 📊 Training Metrics Summary

The Lyra_Immo model was fine-tuned on 150 structured examples, with 30 validation cases, using OpenAI’s standard hyperparameters:

- Epochs: 3  
- Batch size: 1  
- Learning rate multiplier: 2  
- Shuffle: enabled

The model showed stable convergence throughout training.  
Key performance metric:

- **Full validation loss**: `0.867`  
- **Final validation loss (last step)**: `0.463`

These values indicate consistent generalization and alignment with the implicit valuation logic. No sign of overfitting or instability was observed.


## 📊 Observed Behavior
- Strong alignment with implicit valuation table
- Stable, well-phrased, professional answers
- Generalizes well to varied natural user inputs

## ✅ Model Behavior: Fine-tuned vs Base GPT-3.5

We tested the Lyra_Immo fine-tuned model against the base GPT-3.5-turbo using a set of 5 realistic prompts, each requesting a real estate valuation. The results are unambiguous:

**Prompt (multi-query):**

Can you give me an estimate for each of the following properties?

Apartment, 68 m², good condition, zone B2

House, 115 m², to renovate, zone C

Apartment, 52 m², new, downtown zone A

House, 140 m², average condition, outskirts zone B1

Studio, 41 m², good condition, zone B2


**Base model (GPT-3.5-turbo):**  
> *"As a language model, I am not qualified to provide real estate valuations..."*  
> (The model either refuses or produces vague, non-numeric responses.)

**Fine-tuned model (Lyra_Immo):**
Estimation : 178 060 €
Estimation : 141 750 €
Estimation : 248 400 €
Estimation : 319 000 €
Estimation : 123 620 €


**Conclusion:**  
The fine-tuned model generalizes the valuation logic learned from the training set and applies it confidently across all queries, even on edge cases (small surface, degraded condition). This behavior confirms the success of the fine-tuning and the model’s operational readiness for integration into automated workflows.


---

⚙️ Integration in Make (no-code automation)
The Lyra_Immo model has been successfully integrated into a Make scenario for real-time use.

The workflow performs the following steps:

Webhook trigger — receives an incoming message (manual or automated)

Client message — fetches content from a Google Doc

Lyra Immo (GPT) — sends the prompt to the fine-tuned model

Lyra Immo Response — creates a new document with the estimation


This simple and efficient scenario allows users to automate valuation requests with professional and contextualized responses.

---

## 📁 Included Files & Structure
```
Lyra_Immo/
├── costs_estate/
│   └── barème.xlsx
├── datasets/
│   ├── dataset_lyra_immo.jsonl
│   └── validation_lyra_immo.jsonl
├── French_description/
│   ├── Synthèse intégration dans Make.pdf
│   └── Synthèse pour GitHub.pdf
├── Make/
│   └── Workflow Make Lyra Immo.jpg
├── prompts/
│   └── exemples_prompts.txt
└── README.md
```

## 🛠️ Usage
Compatible with Make, n8n, or any GPT API using the fine-tuned model ID.

## 📄 License
For educational and demonstrative use only.
