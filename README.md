# Lyra_immo

## 🏡 Objectif
Modèle IA fine-tuné sur `gpt-3.5-turbo` pour l'estimation de biens immobiliers à partir de paramètres structurés.

## 📥 Données en entrée
- Surface (m²)
- Type de bien (appartement, maison, etc.)
- État général (neuf, bon, moyen, à rénover)
- Localisation (zone géographique, rural / urbain / périurbain)
- Coefficients multiplicateurs (implicites via barème)

## 🧾 Sortie
- Estimation de la valeur du bien exprimée en euros
- Réponse contextualisée (ton professionnel, fluide)

## 🔍 Détails d'entraînement
- 150 lignes d’entraînement, 30 de validation
- Entraînement sur prompts semi-naturels avec structure cohérente
- Hyperparamètres : `3 epochs`, `batch size = 1`, `learning rate multiplier = 2`

## 📊 Comportement observé
- Très bonne cohérence avec le barème implicite
- Réponses stables et polies
- Capacité de généralisation à des formulations utilisateur variées

## 🧪 Exemple de prompt
```
Surface : 82 m²
Type : maison
État : bon
Localisation : périphérie de ville moyenne (zone B1)
```

## 📁 Fichiers inclus
- `dataset_lyra_immo.jsonl` — 150 cas d'entraînement
- `validation_lyra_immo.jsonl` — 30 cas de validation
- `exemples_prompts.txt` — prompts tests variés
- `barème.xlsx` — table de coefficients utilisée

## 🛠️ Usage
Utilisable dans Make, n8n ou via API OpenAI (fine-tuned model ID requis)

## 📄 Licence
Modèle à usage pédagogique et démonstratif uniquement.
