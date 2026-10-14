# NLP_TrigramVsTransformer
Author: Calvin Harmsen  
Date: 10/14/2026

## Overview
This project compares a simple trigram next‑word prediction model with a simulated transformer-style attention approach. The goal is to understand how early statistical language models work, why they fail with limited context, and how attention mechanisms allow modern models to make better predictions.

The trigram model predicts the next word using only the previous two words. The transformer simulation assigns importance weights to multiple words across the entire sentence, showing how broader context improves predictions.

## Files
- `trigram_vs_transformer.py` — main project file  
- `README.md` — project description and learning summary  
- Screenshots folder — trigram outputs and attention tables  

## Trigram Model Summary
The trigram model:
1. Preprocesses text (lowercase, remove punctuation, tokenize)
2. Builds trigram counts from a small training corpus
3. Converts counts into probabilities
4. Predicts the next word using the last two words of a prompt

### Example Trigram Outputs
**Prompt:** The cat sat on the ___  
Context used: (on, the)  
Prediction: mat  
Probability: 1.0

**Prompt:** I want to eat ___  
Context used: (eat, _)  
Prediction: pizza, pasta, dinner  
Probability: varies based on corpus

**Prompt:** She picked up the phone because ___  
Context used: (because, _)  
Prediction: it, she  
Probability: depends on corpus

## Transformer Simulation Summary
The transformer-style simulation assigns weights to important words in each sentence. Instead of only using the last two words, it considers the entire sentence.

Example (The cat sat on the ___):
- cat: 0.40  
- sat: 0.20  
- on: 0.10  
- the: 0.10  
Prediction: mat  
Reason: “cat,” “sat,” and “on” strongly relate to the object being sat on.

## What I Learned
- Trigram models are simple and predictable but fail when context is missing.
- They only use two words, which causes incorrect predictions when meaning depends on earlier parts of the sentence.
- Transformers use attention to weigh multiple words, allowing them to understand relationships across the entire sentence.
- More context leads to more accurate predictions, especially in sentences involving cause/effect or long-range dependencies.
