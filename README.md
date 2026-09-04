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
Model Configuration

The model uses the following configuration:

Parameter	Value	Description



Batch Size      	    -64-	    Number of sequences processed simultaneously
Block Size              -128-    	Maximum context length
Embedding- Dimension-	192	        Dimension of token representations
Attention Heads-	    6-	        Number of attention heads
Transformer Layers-	    6-	        Number of Transformer blocks
Dropout-	            0.1-        Dropout probability
Learning Rate-	        3e-4-	    AdamW learning rate
Training Iterations-	3000-	    Number of training iterations
Evaluation Interval-	300-	    Frequency of evaluation


Main characteristics:

*Tokenization

This project uses character-level tokenization.

Instead of splitting text into words or subwords, every unique character appearing in the dataset becomes a token.

*Self-Attention

Self-attention allows every token to determine which previous tokens are important when producing its representation.

*Causal Masking

Because TinyGPT is an autoregressive language model, a token must not be allowed to see future tokens.
*Multi-Head Attention

Instead of using a single attention mechanism, TinyGPT uses multiple independent attention heads.
*Autoregressive Generation

After training, the model generates text one token at a time.

*Layer Normalization

TinyGPT uses Pre-LayerNorm.
*Feed-Forward Network

After self-attention, the representation passes through a position-wise feed-forward network.

Key Takeaways

This project demonstrates that a GPT-style language model can be constructed from relatively simple building blocks.

At a high level, the entire model can be understood as:
Tokens
   |
   v
Embeddings
   |
   v
Self-Attention
   |
   v
Contextual Representations
   |
   v
Feed-Forward Networks
   |
   v
Repeated Transformer Blocks
   |
   v
Logits
   |
   v
Next Token Prediction

Educational Philosophy

The central idea behind this project is:

Don't just use Transformers. Understand them.

Modern frameworks make it possible to load and use powerful Transformer models with only a few lines of code.

However, implementing a small Transformer from scratch provides a much deeper understanding of the architecture.

By building TinyGPT manually, the Transformer becomes less of a black box and more of a system that can be inspected, modified, debugged, and experimented with.

This project therefore focuses on understanding the fundamental ideas behind GPT rather than simply achieving the largest possible model or the best possible generated text.
Learning Roadmap:
Neural Networks
       |
       v
CNNs / RNNs / LSTMs / GRUs
       |
       v
Attention Mechanism
       |
       v
Transformers
       |
       v
Transformer From Scratch
       |
       v
TinyGPT
       |
       v
Subword Tokenization
       |
       v
Modern GPT Architecture
       |
       v
RoPE / RMSNorm / SwiGLU
       |
       v
Large-Scale Pretraining
       |
       v
Fine-Tuning
       |
       v
Instruction Tuning
       |
       v
Preference Optimization
       |
       v
Retrieval-Augmented Generation
       |
       v
LLM Applications
       |
       v
AI Agents
Inspiration

This project follows the educational philosophy of implementing a minimal GPT architecture from first principles.

It is particularly inspired by the work of Andrej Karpathy and the educational approach demonstrated through nanoGPT and related Transformer-from-scratch implementations.

Author

Milan Javoor

This project is part of a hands-on learning journey focused on Deep Learning, Transformers, Large Language Models, and AI Engineering.

License

This project is intended primarily for educational and research purposes.
