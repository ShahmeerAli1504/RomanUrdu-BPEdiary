# RomanUrdu-BPEdiary

Byte Pair Encoding (BPE) Tokenizer & Sentence Segmentation for Roman Urdu Diaries

## Overview

This project implements **Sentence Segmentation** and **Byte Pair Encoding (BPE) subword tokenization** for Roman Urdu diary data.  
Roman Urdu is notoriously tricky to process due to its lack of standardized spelling, heavy use of phonetic variations, and informal style.  
The goal is to **train a tokenizer** from scratch on a dataset of 100 Roman Urdu diaries, then evaluate it on a separate 14-day diary set, focusing on:

- Vocabulary size reduction
- Out-of-Vocabulary (OOV) handling
- `<UNK>` token analysis

---

## Features

- **Custom Roman Urdu preprocessing**
  - Lowercasing
  - Punctuation removal
  - Optional spelling normalization (e.g., `"mujhe"` → `"mujhay"`)
- **BPE Implementation from Scratch**
  - Starts with character-level vocabulary
  - Iteratively merges frequent subword pairs
  - Vocabulary size limit (`vocab_size = 1000` by default)
- **`<UNK>` Handling**
  - ID `0` reserved for `<UNK>`
  - Unseen tokens replaced at inference
- **Evaluation Metrics**
  - `<UNK>` occurrences per file & overall
  - Vocabulary coverage percentage
  - Unique OOV types count
- **Encoding/Decoding**
  - `encode(text)` → list of subword IDs
  - `decode(ids)` → reconstructed text

---
