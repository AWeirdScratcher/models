# 00. Tensors

🍔 [Learn Pytorch](https://www.learnpytorch.io/00_pytorch_fundamentals/)

## Basics

Tensors are one of the core building blocks of Pytorch, and here are a few types of them:

**Scalar**: A single number, and in "tensor-speak," it's a *zero dimension* tensor.
- Dimensions: `0`
- Example usage: `a`

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

<br /><br />

**Vector**: A single-dimensional tensor that can contain many numbers.
- Dimensions: `1`
- Example usage: `y`

`In [2]:`
```python
vector = torch.tensor([6, 9, 4, 2, 0])
vector, vector.ndim, vector.shape
```

`Out[2]:`
```python
(tensor([6, 9, 4, 2, 0]),
 1,
 torch.Size([5]))
```

> **Counting Dimensions**: Count the open square brackets at the beginning of a tensor.

<br /><br />

**Matrix**: Has two dimensions (can contain "sub-lists," in the concept of Python).
- Dimensions: 2
- Example: `Q`

`In [3]:`
```python
MATRIX = torch.tensor([
  [6, 9, 4],
  [2, 0, 6]
])
MATRIX.shape
```

`Out[3]:`
```python
torch.Size([2, 3])
```

> This implies that the first dimension has two items (sub-lists), and the second dimension has three elements (numbers).

<br /><br />

**Tensor**: An n-dimensional array of numbers.
- Dimensions: $`n`$
- Example usage: `X`

`In [4]:`
```python
TENSOR = torch.tensor([
  [
    [1, 9, 8, 9],
    [0, 6, 0, 4]
  ]
])
TENSOR.shape
```

`Out[4]:`
```python
torch.Size([1, 2, 4])
```

> This implies: that for the first dimension, there is only one item; for the second dimension, there are two items; for the third dimension, there are four numbers.

## Random Tensors

To create a random tensor, use the `torch.rand(size)` function:

`In [5]:`
```python
torch.rand(3, 4)
```

`Out[5]:`
```python
tensor([[0.6541, 0.4807, 0.2162, 0.6168],
        [0.4428, 0.6608, 0.6194, 0.8620],
        [0.2795, 0.6055, 0.4958, 0.5483]])
```

### Manual Seed

Make the result more reproducible with manual seeds:

```python
torch.manual_seed(69)
```

For CUDA (GPU) support:

```python
torch.cuda.manual_seed(69)
```

## Zeros & Ones

Create zeros and ones with a given `size`:

`In [6]:`
```python
zeros = torch.zeros(3, 4)
ones = torch.ones(3, 4)

print(zeros)
print(ones)
```

`Out[6]:`
```python
tensor([[0., 0., 0., 0.],
        [0., 0., 0., 0.],
        [0., 0., 0., 0.]])
tensor([[1., 1., 1., 1.],
        [1., 1., 1., 1.],
        [1., 1., 1., 1.]])
```

### Zeros-like & Ones-like

Sometimes you might want to create a tensor filled with zeros and ones based on the shape of another tensor.

You can achieve this by using `torch.zeros_like(input)` or `torch.ones_like(input)`:

`In [7]:`
```python
x = torch.rand(2, 2)
zeros = torch.zeros_like(x)
ones = torch.ones_like(x)

print("x:", x)
print("zeros:", zeros)
print("ones:", ones)
```

`Out[7]:`
```python
x: tensor([[0.8950, 0.3771],
           [0.4230, 0.2123]])
zeros: tensor([[0., 0.],
               [0., 0.]])
ones: tensor([[1., 1.],
              [1., 1.]])
```

## Range

Use `torch.arange` to create a tensor of a range of numbers like 0 to 100.

`In [8]:`
```python
range_ = torch.arange(start=0, end=10, step=1)
range_
```

`Out[8]:`
```python
tensor([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
```

## Tensor Datatypes

The most common datatype in Pytorch (which is the default) is `torch.float32` (also known as `torch.float`). This is also referred to as "32-bit floating point."

Additionally, there's also a 16-bit floating point (`torch.float16` aka. `torch.half`) and a 64-bit floating point (`torch.float64` aka. `torch.double`).

The reason for using those different datatypes is to do with **precision** in computing, and "precision" is the amount of detail used to describe a number. The higher the value is, the more detail (and hence data) is used to describe a number. However, a higher precision value might lead to a slower performance; a lower precision value is indeed fast but might sacrifice the model's accuracy.

Let's create a tensor with a specific datatype:

`In [9]:`
```python
x = torch.rand(3, 3, dtype=torch.float64)
x
```

`Out[9]:`
```python
tensor([[0.7755, 0.7278, 0.6414],
        [0.5252, 0.4137, 0.5907],
        [0.5338, 0.2536, 0.3880]], dtype=torch.float64)
```
