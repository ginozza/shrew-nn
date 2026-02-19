# Architecture: shrew-nn

`shrew-nn` is the high-level neural network library built on top of `shrew-core`. It provides stateful layers (Modules) that manage parameters and implement forward passes, similar to PyTorch's `torch.nn`.

## Core Concepts

- **Module Trait**: The foundational trait for all layers. Defines how parameters are registered and how data flows through the layer (`forward`).
- **Layers**: Implementations of common building blocks like `Linear`, `Conv2d`, `LSTM`, and `Transformer`.
- **Initialization**: Tools for initializing weights (Xavier, Kaiming, Orthogonal) to ensure stable training dynamics.
- **Functional API**: Stateless versions of layers (e.g., `functional::linear`) are also available but primarily used internally by Modules.

## File Structure

| File | Description | Lines of Code |
| :--- | :--- | :--- |
| `rnn.rs` | Implements Recurrent Neural Networks (RNN, LSTM, GRU) with support for bidirectional processing. | 595 |
| `metrics.rs` | implementation of evaluation metrics like Accuracy, Precision, Recall, F1-Score, and Confusion Matrix. | 511 |
| `conv.rs` | Convolutional layers (`Conv1d`, `Conv2d`, `Conv3d`) supporting custom strides, padding, and dilation. | 374 |
| `init.rs` | Parameter initialization strategies (Uniform, Normal, Xavier/Glorot, Kaiming/He). | 286 |
| `loss.rs` | Loss functions (`MSELoss`, `CrossEntropyLoss`, `NLLLoss`, etc.) for network training. | 278 |
| `attention.rs` | Multi-Head Attention mechanisms, crucial for Transformer architectures. | 249 |
| `batchnorm.rs` | Batch Normalization layers (`BatchNorm1d`, `BatchNorm2d`, `BatchNorm3d`). | 238 |
| `transformer.rs` | Transformer Encoder and Decoder blocks / layers. | 179 |
| `linear.rs` | Fully connected (dense) layers. | 159 |
| `activation.rs` | Activation modules (`ReLU`, `GELU`, `Sigmoid`, `Tanh`, `SiLU`, etc.). | 159 |
| `layernorm.rs` | Layer Normalization implementation. | 136 |
| `groupnorm.rs` | Group Normalization implementation. | 125 |
| `module.rs` | Defines the `Module` trait and parameter management logic. | 114 |
| `embedding.rs` | Lookup table for word embeddings. | 111 |
| `rmsnorm.rs` | Root Mean Square Layer Normalization (RMSNorm). | 84 |
| `dropout.rs` | Dropout layers for regularization. | 80 |
| `sequential.rs` | A container module that chains other modules together in sequence. | 77 |
| `flatten.rs` | Utility layer to flatten tensor dimensions. | 62 |
| `lib.rs` | Crate root. | 58 |
