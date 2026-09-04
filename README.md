# TinyGPT — Transformer Language Model From Scratch

A minimal GPT-style Transformer language model implemented from scratch using PyTorch.

This project was created to understand the internal working of modern Transformer-based language models by implementing the major components manually instead of relying on high-level Transformer APIs.

The model is trained on a character-level text dataset and learns to generate new text autoregressively, one character at a time.



## Overview

TinyGPT is a small decoder-only Transformer inspired by the architecture behind GPT-style language models.

The primary purpose of this project is educational. Rather than treating Transformers as a black box, the project breaks the architecture down into its fundamental components and implements them directly in PyTorch.

The model includes:

- Character-level tokenization
- Token embeddings
- Positional embeddings
- Causal self-attention
- Query, Key, and Value projections
- Scaled dot-product attention
- Causal masking
- Multi-head attention
- Feed-forward neural networks
- GELU activation
- Residual connections
- Layer normalization
- Dropout
- Cross-entropy loss
- AdamW optimization
- Autoregressive text generation



## Project Objective

The main objective of this project is to understand how a GPT-style Transformer processes a sequence and predicts the next token.

The project focuses on answering questions such as:

- How are tokens represented numerically?
- Why do we need embeddings?
- How does a Transformer understand token positions?
- What are Query, Key, and Value?
- How is attention calculated?
- Why is attention divided by the square root of the head dimension?
- Why does GPT require causal masking?
- Why are multiple attention heads used?
- Why are residual connections necessary?
- What does LayerNorm actually do?
- How does the Transformer produce the probability of the next token?
- How does autoregressive text generation work?



## Architecture

The overall architecture of TinyGPT is:

```text
Input Text
    |
    v
Character Tokenization
    |
    v
Token IDs
    |
    +--------------------------+
    |                          |
    v                          v
Token Embedding        Positional Embedding
    |                          |
    +------------+-------------+
                 |
                 v
        Combined Representation
                 |
                 v
        Transformer Block 1
                 |
                 v
        Transformer Block 2
                 |
                 v
        Transformer Block 3
                 |
                 v
        Transformer Block 4
                 |
                 v
        Transformer Block 5
                 |
                 v
        Transformer Block 6
                 |
                 v
           Final LayerNorm
                 |
                 v
          Language Model Head
                 |
                 v
              Logits
                 |
                 v
              Softmax
                 |
                 v
        Next Token Prediction
                 |
                 v
          Generated Text
