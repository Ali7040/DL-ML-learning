# Phase 3: Deep Learning Fundamentals 🧠

**Duration:** Weeks 21-35 (3.5 months)  
**Goal:** Master neural networks from ground up, including PyTorch and TensorFlow

## Overview

This is where you transition from classical ML to deep learning. You'll build neural networks from absolute scratch (just NumPy), then master modern frameworks.

## Critical Philosophy

**IMPLEMENT FROM SCRATCH FIRST, THEN USE FRAMEWORKS**

Understanding backpropagation by implementing it is 100x better than just using PyTorch's autograd.

## Folders

### Neural-Networks-From-Scratch/
Pure NumPy implementations - no frameworks

### PyTorch-Basics/
PyTorch fundamentals and advanced features

### TensorFlow-Basics/
TensorFlow/Keras ecosystem

### Projects/
Neural network applications

## Weekly Breakdown

### Week 21-23: Neural Networks from Scratch

#### Week 21: Fundamentals
- [ ] Perceptron implementation
- [ ] Single layer network
- [ ] Activation functions (implement all)
- [ ] Forward propagation
- **Deliverable:** Working perceptron for XOR

#### Week 22: Backpropagation
- [ ] Derive backprop mathematically (2-layer network)
- [ ] Implement backprop from scratch
- [ ] Gradient checking
- [ ] Loss functions
- **Deliverable:** 2-layer network trained on MNIST

#### Week 23: Optimization & Regularization
- [ ] Implement SGD, Momentum, Adam
- [ ] Batch vs mini-batch vs stochastic
- [ ] Dropout implementation
- [ ] Batch normalization
- **Deliverable:** 3-layer network with all optimizers

### Week 24-26: Deep Learning Frameworks

#### Week 24-25: PyTorch
- [ ] Tensor operations and autograd
- [ ] Building custom layers
- [ ] Custom loss functions
- [ ] DataLoader and Dataset
- [ ] Model saving/loading
- [ ] Hooks and debugging
- **Deliverable:** Recreate all scratch implementations in PyTorch

#### Week 26: TensorFlow/Keras
- [ ] Keras Sequential API
- [ ] Functional API
- [ ] Model subclassing
- [ ] Custom layers and training loops
- [ ] TensorBoard integration
- **Deliverable:** Same models in TensorFlow

### Week 27-30: Convolutional Neural Networks

#### Week 27: CNN Fundamentals
- [ ] Implement 2D convolution in NumPy
- [ ] Understand padding, stride, dilation
- [ ] Pooling layers
- [ ] Receptive field calculation
- **Deliverable:** Simple CNN from scratch

#### Week 28-29: CNN Architectures
- [ ] LeNet-5 (implement and train)
- [ ] AlexNet
- [ ] VGGNet
- [ ] ResNet (understand skip connections)
- [ ] Inception modules
- **Deliverable:** Train each on CIFAR-10

#### Week 30: Advanced CNN
- [ ] Transfer learning
- [ ] Fine-tuning strategies
- [ ] Data augmentation
- [ ] Grad-CAM visualization
- **Deliverable:** Image classifier with transfer learning

### Week 31-35: Recurrent Neural Networks

#### Week 31-32: RNN Basics
- [ ] Vanilla RNN implementation
- [ ] Backpropagation through time (BPTT)
- [ ] Gradient problems (vanishing/exploding)
- [ ] Gradient clipping
- **Deliverable:** RNN for sequence prediction

#### Week 33-34: LSTM & GRU
- [ ] Understand LSTM gates
- [ ] Implement LSTM cell
- [ ] GRU architecture
- [ ] Bidirectional RNNs
- **Deliverable:** LSTM implementation from scratch

#### Week 35: Attention & Applications
- [ ] Attention mechanism
- [ ] Encoder-decoder
- [ ] Seq2seq models
- **Deliverable:** Text generation model

## Core Implementations (Must Do)

### From Scratch (NumPy Only)
1. **Multi-layer Perceptron**
   ```python
   class NeuralNetwork:
       def __init__(self, layers):
           # Initialize weights
       def forward(self, X):
           # Forward pass
       def backward(self, X, y):
           # Backpropagation
       def train(self, X, y, epochs):
           # Training loop
   ```

2. **Activation Functions**
   - Sigmoid, Tanh, ReLU, Leaky ReLU
   - Derivatives for each

3. **Optimizers**
   - SGD, Momentum, RMSprop, Adam
   
4. **Loss Functions**
   - MSE, Cross-Entropy, Hinge

5. **Regularization**
   - L1/L2 regularization
   - Dropout
   - Batch normalization

6. **2D Convolution**
   ```python
   def convolve2d(image, kernel, stride, padding):
       # Implement convolution
   ```

7. **RNN Cell**
   ```python
   class RNNCell:
       def forward(self, x, h_prev):
           # Compute hidden state
   ```

8. **LSTM Cell**
   ```python
   class LSTMCell:
       def forward(self, x, h_prev, c_prev):
           # Gates and cell state
   ```

## PyTorch Deep Dive Topics

### Essential Concepts
- [ ] Tensor operations and broadcasting
- [ ] Autograd mechanics
- [ ] `torch.nn.Module` class
- [ ] `torch.utils.data.Dataset`
- [ ] Custom collate functions
- [ ] Learning rate schedulers
- [ ] Model checkpointing
- [ ] Gradient clipping
- [ ] Mixed precision training

### Advanced
- [ ] Custom backward functions
- [ ] Hooks (forward and backward)
- [ ] Custom layers with parameters
- [ ] Distributed training basics
- [ ] TorchScript
- [ ] Model quantization basics

## Projects

### Beginner
1. **MNIST Digit Recognition**
   - Implement from scratch
   - Then with PyTorch
   - Compare performance

2. **CIFAR-10 Classification**
   - Build custom CNN
   - Train from scratch
   - Apply data augmentation

3. **Sentiment Analysis**
   - LSTM for text
   - Word embeddings
   - Bidirectional LSTM

### Intermediate
4. **Image Classification with Transfer Learning**
   - Fine-tune ResNet/VGG
   - Custom dataset
   - Deploy with Flask

5. **Text Generation**
   - Character-level LSTM
   - Generate text
   - Temperature sampling

6. **Time Series Forecasting**
   - Stock price prediction
   - LSTM/GRU comparison
   - Feature engineering

### Advanced
7. **Custom Architecture from Paper**
   - Pick a paper
   - Implement architecture
   - Reproduce results

8. **Multi-task Learning**
   - Single model, multiple outputs
   - Shared representations

## Mathematical Understanding

### Must Derive by Hand
1. Gradient of loss w.r.t. weights (2-layer network)
2. Backpropagation equations
3. Chain rule for nested functions
4. Gradient of sigmoid, tanh, ReLU
5. Batch normalization gradients

### Must Calculate Manually
1. Forward pass for small network (2x2 example)
2. Backward pass with actual numbers
3. Convolution output size
4. Receptive field for CNN
5. LSTM gate computations

## Common Debugging Issues

### Training Problems
```python
# Checklist when model doesn't learn:
1. Check data preprocessing (normalization?)
2. Verify labels are correct
3. Initialize weights properly (Xavier/He)
4. Learning rate too high/low?
5. Gradient flow (use grad checking)
6. Loss function appropriate?
7. Batch size too small?
```

### Implementation Bugs
```python
# Common mistakes:
1. Shape mismatches
2. Wrong dimension for softmax
3. Not using torch.no_grad() for validation
4. Forgetting model.train()/model.eval()
5. Not zeroing gradients (optimizer.zero_grad())
6. Wrong loss reduction
```

## Resources

### Books
- "Deep Learning" by Goodfellow, Bengio, Courville (Bible)
- "Deep Learning with PyTorch" by Stevens
- "Dive into Deep Learning" (d2l.ai)

### Courses
- Stanford CS230 (Deep Learning)
- Stanford CS231n (CNNs)
- Fast.ai Practical Deep Learning

### Papers to Read
- "Batch Normalization" (Ioffe & Szegedy)
- "Dropout" (Srivastava et al.)
- "Adam optimizer" (Kingma & Ba)
- "Deep Residual Learning" (He et al.)

### Blogs
- Andrej Karpathy's blog
- Christopher Olah's blog (colah.github.io)
- Distill.pub

## Code Templates

### Training Loop Template
```python
def train_epoch(model, dataloader, optimizer, criterion, device):
    model.train()
    total_loss = 0
    
    for batch_idx, (data, target) in enumerate(dataloader):
        data, target = data.to(device), target.to(device)
        
        # Forward pass
        optimizer.zero_grad()
        output = model(data)
        loss = criterion(output, target)
        
        # Backward pass
        loss.backward()
        optimizer.step()
        
        total_loss += loss.item()
    
    return total_loss / len(dataloader)

def evaluate(model, dataloader, criterion, device):
    model.eval()
    total_loss = 0
    correct = 0
    
    with torch.no_grad():
        for data, target in dataloader:
            data, target = data.to(device), target.to(device)
            output = model(data)
            loss = criterion(output, target)
            total_loss += loss.item()
            
            pred = output.argmax(dim=1)
            correct += pred.eq(target).sum().item()
    
    accuracy = correct / len(dataloader.dataset)
    avg_loss = total_loss / len(dataloader)
    
    return avg_loss, accuracy
```

## Assessment Checklist

Before moving to next phase:
- [ ] Can derive backprop for 2-layer network on paper
- [ ] Implemented neural network from scratch (no frameworks)
- [ ] Understand gradient descent variants deeply
- [ ] Comfortable with PyTorch tensors and autograd
- [ ] Built and trained CNN from scratch
- [ ] Understand why CNNs work for images
- [ ] Implemented RNN and LSTM from scratch
- [ ] Trained models on real datasets
- [ ] Can debug training issues systematically
- [ ] Understand initialization strategies
- [ ] Know when to use which activation function
- [ ] Can implement any layer given its equations

## Next Steps

After completing this phase, specialize in:
- [04-Computer-Vision](../04-Computer-Vision/README.md)
- [05-NLP](../05-NLP/README.md)
- [06-Advanced-Topics](../06-Advanced-Topics/README.md)

---

**Master Tip:** If you can implement it from scratch, you truly understand it! 🚀
