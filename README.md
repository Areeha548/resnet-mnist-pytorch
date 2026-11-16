# ResNet-18 Digit Classifier on MNIST (PyTorch)

A simple project where I train a ResNet-18 model in PyTorch to recognize handwritten digits (0 to 9) from the MNIST dataset.

## Results

The model reached **99.28% best test accuracy** (epoch 4) and **99.21% final test accuracy** (epoch 5).

| Epoch | Train Loss | Test Accuracy |
|-------|-----------|---------------|
| 1 | 0.0996 | 97.77% |
| 2 | 0.0383 | 98.70% |
| 3 | 0.0279 | 99.24% |
| 4 | 0.0226 | 99.28% |
| 5 | 0.0183 | 99.21% |

Training loss kept going down and test accuracy went up, then stayed steady around 99.2%.

## Dataset

- **MNIST**: 70,000 grayscale images of handwritten digits, each 28x28 pixels.
- 60,000 images for training and 10,000 for testing.
- Images are converted to tensors and normalized (mean 0.1307, std 0.3081).

## Model

I used the ResNet-18 architecture from `torchvision`, trained from scratch (no pretrained weights), and changed two things so it works with MNIST:

1. **First layer:** changed to accept 1 channel (grayscale) instead of 3 (color).
2. **Max-pooling:** removed, because 28x28 images are already small.

ResNet uses skip connections, which make deep networks easier to train.

## Training Setup

- Loss function: Cross Entropy Loss
- Optimizer: Adam (learning rate 0.001)
- Batch size: 128 (training), 256 (testing)
- Epochs: 5
- Platform: Google Colab (GPU)

At the end of training, the model weights are saved to `resnet_mnist.pth`.

## Tech Stack

Python, PyTorch, torchvision

## How to Run

1. Open `resnet_mnist.ipynb` in Google Colab.
2. Turn on a GPU: **Runtime, Change runtime type, GPU**.
3. Click **Runtime, Run all**.
4. The MNIST dataset downloads automatically. Training takes a few minutes.

## What I Learned

- How a training loop works in PyTorch (forward pass, loss, backward pass, optimizer step).
- How to change the input layer of a standard model to work with a different type of data.
- How to read loss and accuracy to check if a model is learning well.

## Author

**Areeha Shafique**
GitHub: [Areeha548](https://github.com/Areeha548)
