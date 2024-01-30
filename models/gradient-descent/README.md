# Gradient Descent Model

This simple gradient descent model is trained on a linear equation ($y=0.7x+0.3$). The model guesses the weight $m$ and bias $b$ during the training process.

- [Safetensors](https://raw.githubusercontent.com/AWeirdScratcher/models/main/models/gradient-descent/gradient_descent_5k.safetensors) - 1KB
- [PyTorch PT File](https://raw.githubusercontent.com/AWeirdScratcher/models/main/models/gradient-descent/gradient_descent_5k.bin) - 3KB

## Safetensors

Load the model using 🤗 Safetensors:

```python
from safetensors.torch import load_file

load_file("./gradient_descent_5k.safetensors")
# => {'bias': ..., 'weights': ...}
```

## PyTorch

Load the model from the PyTorch PT file:

```python
import torch

model = torch.load("./gradient_descent_5k.bin")
model.state_dict()
# => OrderedDict([('weights', ...), ('bias', ...)])
```
