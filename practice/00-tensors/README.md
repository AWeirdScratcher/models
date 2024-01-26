# 0. Tensors

🍔 [Learn Pytorch](https://www.learnpytorch.io/00_pytorch_fundamentals/)

Tensors are one of the core building blocks of Pytorch, and here are a few types of them:

**Scalar**: Basically a single number, and in "tensor-speak," it's a *zero dimension* tensor.

`In [1]:`
```python
import torch

scalar = torch.tensor(69)
scalar, scalar.ndim
```

`Out[1]:`
```python
(tensor(69), 0)
```

<br />

**Vector**: A single-dimensional tensor that can contain many numbers.

`In [2]:`
```python
vector = torch.tensor([6, 9, 4, 2, 0])
vector, vector.ndim
```

`Out[2]:`
```python
(tensor([6, 9, 4, 2, 0]), 1)
```

> **Counting Dimensions**: Count the open square brackets at the beginning of a tensor.
