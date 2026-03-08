# Learning Notes & Concepts 📝

This file contains detailed notes, explanations, and insights gathered during the learning journey. Organized by topics for easy reference.

---

## Table of Contents

1. [Mathematical Foundations](#mathematical-foundations)
2. [Classical Machine Learning](#classical-machine-learning)
3. [Deep Learning Fundamentals](#deep-learning-fundamentals)
4. [Computer Vision](#computer-vision)
5. [Natural Language Processing](#natural-language-processing)
6. [Advanced Topics](#advanced-topics)
7. [Production & Optimization](#production--optimization)
8. [Research Papers Summary](#research-papers-summary)
9. [Code Snippets](#code-snippets)
10. [Common Pitfalls & Solutions](#common-pitfalls--solutions)

---

## Mathematical Foundations

### Linear Algebra

#### Vectors
```
Date: 
Key Concepts:
- 
- 

Intuition:


Code Example:
```python
# Example code
```

Mathematical Notation:


---

#### Matrices
```
Date:
Key Concepts:
-

Examples:
```

---

### Calculus

#### Derivatives & Gradients
```
Date:
Key Concepts:
-

Chain Rule (Critical for Backprop):


Practice Problems Solved:
-
```

---

### Probability & Statistics

#### Probability Distributions
```
Date:
Key Concepts:
-

Common Distributions:
1. Normal/Gaussian
2. Bernoulli
3. Multinomial

When to use each:
-
```

---

## Classical Machine Learning

### Supervised Learning

#### Linear Regression
```
Date:
Mathematical Formulation:
- Hypothesis: h(x) = θ₀ + θ₁x₁ + ... + θₙxₙ
- Cost Function: J(θ) = 1/(2m) Σ(h(x⁽ⁱ⁾) - y⁽ⁱ⁾)²

Gradient Descent Update:
- θⱼ := θⱼ - α ∂J(θ)/∂θⱼ

Implementation Notes:
-

Common Issues:
- Overfitting → Use regularization
- Underfitting → Add features/polynomial terms

When to use:
-
```

---

#### Logistic Regression
```
Date:
Key Differences from Linear Regression:
-

Sigmoid Function:
- σ(z) = 1/(1 + e⁻ᶻ)

Log Loss:
- J(θ) = -1/m Σ[y log(h(x)) + (1-y) log(1-h(x))]

Implementation Tricks:
-
```

---

### Ensemble Methods

#### Random Forests
```
Date:
How it works:
1. Bootstrap samples
2. Random feature selection
3. Build decision trees
4. Aggregate predictions

Hyperparameters:
- n_estimators
- max_depth
- min_samples_split
- max_features

Advantages:
-

When to use:
-
```

---

## Deep Learning Fundamentals

### Neural Networks

#### Backpropagation
```
Date:
Mathematical Derivation:
1. Forward pass
2. Compute loss
3. Backward pass (chain rule)
4. Update weights

Step-by-step for 2-layer network:


Common Mistakes:
-

Debug Checklist:
□ Gradient checking
□ Weight initialization
□ Learning rate tuning
```

---

#### Activation Functions
```
Date:
Comparison:

| Function | Range | Pros | Cons | Use Case |
|----------|-------|------|------|----------|
| Sigmoid  | (0,1) | ... | Vanishing gradient | Output layer (binary) |
| Tanh     | (-1,1)| ... | Vanishing gradient | Hidden layers (RNN) |
| ReLU     | [0,∞) | Fast, no vanishing | Dying ReLU | Hidden layers (CNN) |
| Leaky ReLU| (-∞,∞)| Fixes dying ReLU | ... | Alternative to ReLU |
| GELU     | ... | ... | ... | Transformers |

When to use each:
-
```

---

#### Optimization Algorithms
```
Date:
Comparison of optimizers:

SGD:
- Pro: Simple, generalizes well
- Con: Slow convergence
- When: Small datasets, need generalization

Momentum:
- Update: v = βv + ∇θJ(θ), θ -= αv
- Pro: Accelerates convergence
- Con: Additional hyperparameter

Adam:
- Combines momentum + RMSprop
- Pro: Adaptive learning rate, works well
- Con: Can overfit
- When: Default choice, large datasets

Learning rate schedules:
-
```

---

## Computer Vision

### Convolutional Neural Networks

#### Convolution Operation
```
Date:
Mathematical Definition:
- (f * g)[m,n] = ΣΣ f[i,j] · g[m-i, n-j]

Parameters:
- Kernel size: 3x3, 5x5, 7x7
- Stride: how much to move
- Padding: SAME vs VALID

Output size calculation:
- Output = (Input - Kernel + 2*Padding) / Stride + 1

Receptive field:
-

Implementation notes:
-
```

---

#### CNN Architectures
```
Date:
Evolution of architectures:

1. LeNet-5 (1998)
   - First CNN
   - 5 layers
   - For digit recognition

2. AlexNet (2012)
   - 8 layers
   - ReLU activation
   - Dropout
   - Data augmentation

3. VGGNet (2014)
   - Deeper (16-19 layers)
   - Small 3x3 filters
   - Simple architecture

4. ResNet (2015)
   - Skip connections
   - 50-152 layers
   - Solves vanishing gradient

5. Inception
   - Multiple filter sizes
   - 1x1 convolutions

Design principles learned:
-
```

---

## Natural Language Processing

### Transformers

#### Self-Attention Mechanism
```
Date:
Mathematical Formulation:
- Q, K, V = XWq, XWk, XWv
- Attention(Q,K,V) = softmax(QKᵀ/√dk)V

Multi-Head Attention:
- Run attention h times in parallel
- Concatenate results

Why it works:
-

Implementation tips:
-

Computational complexity:
- O(n²d) where n=sequence length

Optimizations:
-
```

---

## Advanced Topics

### Generative Adversarial Networks

#### GAN Training
```
Date:
Game Theory Perspective:
- Generator: min_G V(D,G)
- Discriminator: max_D V(D,G)

Training procedure:
1. Train D on real + fake
2. Train G to fool D
3. Repeat

Common issues:
- Mode collapse → 
- Non-convergence →
- Vanishing gradients →

Training tricks:
- Use labels smoothing
- Feature matching
- Different learning rates

Evaluation metrics:
- Inception Score
- FID (Fréchet Inception Distance)
```

---

## Production & Optimization

### Model Optimization

#### Quantization
```
Date:
Types:
1. Dynamic quantization
2. Static quantization
3. Quantization-aware training

FP32 → INT8:
- Reduce size by 4x
- Speedup: 2-4x

Trade-offs:
- Accuracy vs Speed
- Model size vs Latency

When to use:
-

Tools:
- PyTorch quantization
- TensorRT
- ONNX Runtime
```

---

## Research Papers Summary

### Template
```
Paper: [Title]
Authors: 
Year:
Conference/Journal:

Problem:
-

Key Contributions:
1.
2.
3.

Methodology:
-

Results:
-

Why it matters:
-

Implementation notes:
-

Code reference:
-
```

---

## Code Snippets

### Useful Utilities

```python
# Template for training loop
def train_epoch(model, dataloader, optimizer, criterion, device):
    model.train()
    total_loss = 0
    
    for batch_idx, (data, target) in enumerate(dataloader):
        data, target = data.to(device), target.to(device)
        
        optimizer.zero_grad()
        output = model(data)
        loss = criterion(output, target)
        loss.backward()
        optimizer.step()
        
        total_loss += loss.item()
    
    return total_loss / len(dataloader)
```

```python
# Model checkpoint saving
def save_checkpoint(model, optimizer, epoch, loss, path):
    torch.save({
        'epoch': epoch,
        'model_state_dict': model.state_dict(),
        'optimizer_state_dict': optimizer.state_dict(),
        'loss': loss,
    }, path)
```

---

## Common Pitfalls & Solutions

### Training Issues

1. **Loss not decreasing**
   - Check learning rate (too high/low)
   - Verify gradient flow
   - Check data preprocessing
   - Ensure labels are correct

2. **Overfitting**
   - Add regularization (L1/L2, dropout)
   - Increase dataset size
   - Data augmentation
   - Reduce model complexity
   - Early stopping

3. **Vanishing/Exploding Gradients**
   - Use proper initialization (Xavier, He)
   - Batch normalization
   - Gradient clipping
   - Skip connections
   - Choose appropriate activation functions

4. **Slow Training**
   - Increase batch size
   - Use better optimizer
   - Mixed precision training
   - Data loading optimization
   - Multi-GPU training

---

## Questions to Explore

- [ ] Why does batch normalization work so well?
- [ ] What's the intuition behind skip connections?
- [ ] How does attention capture long-range dependencies?
- [ ] Why is transfer learning effective?

---

**Note:** This is a living document. Update regularly with new insights and discoveries!
