# Diffusion Generative Model

A Jupyter Notebook implementation of a diffusion generative model.

## Installation

To run this notebook, you'll need to install the following dependencies:

* `torch`
* `torchvision`
* `matplotlib`
* `diffusers`
* `datasets`

You can install them using pip. Note that `diffusers` must be upgraded to the latest version:
```bash
pip install torch torchvision matplotlib datasets transformers
pip install --upgrade diffusers
```

## GPU Acceleration

### NVIDIA GPU
For NVIDIA GPU acceleration, you'll need to install the torch package with CUDA support:
```bash
pip install torch torchvision --extra-index-url https://download.pytorch.org/whl/cu116
```
Then, you can run the notebook using the `cuda` device.

### Apple Silicon
For Apple Silicon (M1/M2/M3) acceleration, you'll need to install the `accelerate` package:
```bash
pip install accelerate
```
Then, you can run the notebook using the `mps` device.

## Running the Notebook

To run the notebook, simply execute the cells in the notebook. Make sure to select the correct device (either `cuda` or `mps`) depending on your hardware.
Note that you'll need to modify the device selection code in the notebook to use the correct device. For example:

```python
device = torch.device('cuda' if torch.cuda.is_available() else 
                      'mps' if torch.backends.mps.is_available() else 'cpu')
```

This will select the `cuda` device if available, otherwise it will select the `mps` device if available, and finally it will fall back to the `cpu` device if neither `cuda` nor `mps` is available.