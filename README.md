#Waste_ Management

Summative lab: an integrated assistant that identifies waste from images or text descriptions and
returns recycling instructions grounded in city policy documents.

## Components
1. **Image classifier (CNN):** MobileNetV2 transfer learning on the RealWaste dataset (9 classes), about 0.8 test accuracy.
2. **Text classifier:** TF-IDF (word and character n-grams) with logistic regression on waste descriptions, about 0.99 test accuracy.
3. **RAG instruction generator:** retrieval from policy documents with query expansion, a faithfulness check and an extractive fallback.
4. **Integrated assistant:** `waste_management_assistant(input, input_type)` routes the input, checks confidence and returns the category, instructions and sources.

## Files
- `waste_management_summative.ipynb`: the full notebook (Parts 1-5)
- `waste_descriptions.csv`, `waste_policy_documents.json`: supplementary data

## Data
RealWaste images (UCI): https://archive.ics.uci.edu/dataset/908/realwaste (not included because of size).

## Limitations
Synthetic, templated text data; the classifiers have no "not waste" class; the language model was not available offline, so instructions come from the policy text.
