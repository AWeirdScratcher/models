# 0. Tensors

🍔 [Learn Pytorch](https://www.learnpytorch.io/00_pytorch_fundamentals/)

Tensors are one of the core building blocks of Pytorch, and here are a few types of them:

**Scalar**: Basically a single number, and in "tensor-speak," it's a *zero dimension* tensor.

```python
import torch

scalar = torch.tensor(69)
scalar, scalar.ndim
```

```python
tensor(69), 0
```

**Vector**: 
