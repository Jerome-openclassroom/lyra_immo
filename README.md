# Lyra_Immo

## 🏡 Objective
Fine-tuned GPT-3.5-turbo model for real estate valuation based on structured parameters.

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

## 📊 Observed Behavior
- Strong alignment with implicit valuation table
- Stable, well-phrased, professional answers
- Generalizes well to varied natural user inputs

## 🧪 Prompt Example
```
Surface: 82 m²  
Type: house  
Condition: good  
Location: outskirts of mid-sized city (zone B1)
```

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
