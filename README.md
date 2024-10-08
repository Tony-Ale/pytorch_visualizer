# Neural Network Visualization Tool
![](assets/demo_gif.gif)

This tool is designed to provide a dynamic visualization of neural network training. It integrates with a PyTorch model's forward pass as a decorator, allowing you to visualize how neural network training occurs.

### Features:
- **Supported Loss Functions:**
  1. `NLLLoss`
  2. `CrossEntropyLoss`

- **Layer Compatibility:**
  - Currently supports fully connected (dense) layers.

### Interactive Visualization:
- View the gradient, bias, and weight histories for both nodes and lines.
- Click on any node or line to inspect its parameters.


## Installation

```bash
pip install pytorch_visualizer
```

## How the API is used

Below is an example showing how the API can be used:

```python
from python_visualizer.nn_visualizer import visualize
class SimpleNN(nn.Module):
    def __init__(self):
        super(SimpleNN, self).__init__()
        self.fc1 = nn.Linear(2, 5) 
        self.fc2 = nn.Linear(5, 3)
        self.relu = nn.ReLU()
    
    @visualize(epochs=5, labels=None, loss_func=None, backward=False)
    def forward(self, x):
        x = self.fc1(x) 
        x = self.relu(x)
        x = self.fc2(x) 
        return x

```
check demo.ipynb for a full implementation with a training loop

## License
MIT

