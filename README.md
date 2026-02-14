# Byte Pair Encoding (BPE) Tokenizer – Assignment Part A

## Overview
This project implements a **Byte Pair Encoding (BPE)** tokenizer from scratch using Python.  
The goal of the assignment is to understand how BPE works by manually implementing each step, rather than using existing tokenizer libraries.

The tokenizer is trained on a fixed corpus derived from *Alice’s Adventures in Wonderland* and is then used to tokenize new text.

---

## Dataset
- **Source:** Alice’s Adventures in Wonderland (public domain)
- **Corpus size:** 500 words
- **Preprocessing steps:**
  - Converted to lowercase
  - Punctuation removed
  - Split on whitespace
- Each word is treated as an independent unit

---

## Implementation Details
The following components were implemented from scratch:

1. **Initial Vocabulary Construction**
   - Words are split into characters
   - End-of-word marker `</w>` is appended

2. **Pair Frequency Computation**
   - Counts frequencies of adjacent symbol pairs
   - Frequencies are weighted by word counts

3. **Merging Symbol Pairs**
   - The most frequent adjacent pair is merged globally
   - Word frequencies remain unchanged

4. **BPE Training Loop**
   - Repeats pair counting and merging for a fixed number of merges
   - Stores merge operations in order

5. **Tokenization**
   - Tokenization of individual words using learned merges
   - Tokenization of full text by tokenizing each word and concatenating results

---

## Key Observations
- Frequent words (e.g., *alice*) are often merged into single tokens
- Common substrings (e.g., `in`, `ing</w>`) are learned as subword units
- Unseen words are handled gracefully using known subwords and characters
- Some merges are frequent but linguistically unintuitive (e.g., `('e','</w>') → e</w>`), highlighting limitations of BPE

---

## Limitations
- BPE is purely frequency-based and does not consider linguistic meaning
- Some words are split into many small tokens if they are not frequent
- End-of-word based merges can create unintuitive tokens

---

## Tools and Libraries Used
- Python standard libraries only:
  - `collections`
  - `re`
- No external tokenizer libraries were used, in accordance with assignment rules

---

## Generative AI Usage
This assignment was completed with assistance from **ChatGPT 5.2 – Thinking (OpenAI)** as a learning aid.  
AI was used to:
- Understand BPE concepts
- Clarify implementation logic
- Improve explanation clarity

All AI usage is documented in the **AI Usage Report** included with the submission.

---

## Author
Student ID: **[Your Student ID Here]**

Course: **[Course Name / Code]**
