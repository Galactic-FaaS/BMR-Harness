# BMR Evaluation Harness

## The BMR Evaluation Harness is a Python-based tool designed for evaluating the performance of text generation models, specifically focusing on translation tasks. It uses three widely recognized evaluation metrics: BLEU (Bilingual Evaluation Understudy), METEOR (Metric for Evaluation of Translation with Explicit Ordering), and ROUGE (Recall-Oriented Understudy for Gisting Evaluation).
Features

    Batch Processing: Supports evaluating multiple inputs at once for efficiency.
    Comprehensive Metrics: Evaluates text using BLEU, METEOR, and ROUGE metrics.
    Model Agnostic: Can be used with any model that generates text, provided it is compatible with the Hugging Face transformers library.
    GPU Support: Automatically utilizes GPU resources if available, ensuring faster processing times for large models.

Prerequisites

    Python 3.6+
    PyTorch
    Hugging Face transformers
    NLTK
    rouge-score
    NumPy

Installation

First, ensure you have Python installed on your system. Then, install the required libraries using pip:

```bash

pip install torch transformers nltk rouge-score numpy
```

Usage
Step 1: Load Your Model

Replace "GalacticAI/DecimaXL" with the model you intend to use:

```python

from BMRHarness import load_model_and_tokenizer

model_name = "GalacticAI/DecimaXL"
translation_pipeline = load_model_and_tokenizer(model_name)
```

Step 2: Generate Translations

Pass your input texts to the generate_translations function:

```python

from BMRHarness import generate_translations

input_texts = ["Your input text here."]
translations = generate_translations(translation_pipeline, input_texts)
```

Step 3: Evaluate Translations

Provide the generated translations and their corresponding reference texts to the evaluate_text function:

```python

from BMRHarness import evaluate_text, print_scores
```

reference_texts = [[["Your reference text here."]]]
evaluation_scores = evaluate_text(translations, reference_texts)
print_scores(evaluation_scores)


Contributing

We welcome contributions to improve the BMR Evaluation Harness. Please feel free to submit issues and pull requests.
