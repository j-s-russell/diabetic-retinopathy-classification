# Setup Instructions

```{tip}

The instruction below cover the specific libraries necessary for this project.
```

### Pre-requisities

#### Python Environment Setup

This project requires Python 3.8 or higher. We recommend using a virtual environment to manage dependencies.
Create and activate a virtual environment:

1. Create virtual environment
`python -m venv retinal_analysis_env`

2. Activate virtual environment

On Windows:
`retinal_analysis_env\Scripts\activate`

On macOS/Linux:
`source retinal_analysis_env/bin/activate`


#### Install Required Python Packages

Install the core dependencies:

`pip install torch torchvision` <-- Deep learning framework

`pip install pandas numpy matplotlib scikit-learn` <-- Data science and visualization

`pip install pillow opencv-python scikit-image` <-- Image processing

`pip install grad-cam` <-- Model interpretability

`pip install jupyterlab jupyter` <-- Jupyter environment

`pip install collections-extended` <-- Additional utilities

#### Verify Installation

Test your installation by running this in a Python environment:

```python
import pandas as pd
import numpy as np
import torch
import torchvision
import matplotlib.pyplot as plt
from sklearn.metrics import cohen_kappa_score
import cv2
from PIL import Image
from pytorch_grad_cam import GradCAM

print("All packages installed successfully!")
print(f"PyTorch version: {torch.__version__}")
print(f"CUDA available: {torch.cuda.is_available()}")
```

### Launch Jupyter Lab

Once everything is installed, start Jupyter Lab:

```python
jupyter lab
```

Your browser should open automatically with the Jupyter Lab interface. Navigate to the project notebooks to begin!
