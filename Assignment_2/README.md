# CSCI611 Assignment 2: CNN on CIFAR-10

This project implements a convolutional neural network for image classification on the CIFAR-10 dataset.

## Files

- `build_cnn.ipynb` - Main notebook with complete implementation and results
- `Assignment2_Report.md` - Full report analyzing the model and results  
- `README.md` - This file
- `requirements.txt` - Required Python packages
- `model_trained.pt` - Trained model weights
- `data/` - CIFAR-10 dataset (downloaded automatically)

## Setup

Install required packages:
```bash
pip install -r requirements.txt
```

## Running the Code

Open and run the Jupyter notebook:
```bash
jupyter notebook build_cnn.ipynb
```

Click Cell > Run All to execute the entire notebook. Training takes about 25-30 minutes on CPU.

## Model Summary

- Architecture: 3 convolutional layers + 2 fully connected layers
- Optimizer: Adam (lr=0.001)
- Training: 25 epochs, batch size 20
- Regularization: Dropout (p=0.25)
- **Test Accuracy: 75%**

## Results

The model achieved 75% accuracy on CIFAR-10 test set:
- Best classes: Automobiles (89%), Frogs (84%), Airplanes (83%)
- Challenging classes: Cats (53%), Dogs (64%)

All visualizations and detailed analysis are in the notebook and report.

## Requirements

- Python 3.7+
- PyTorch
- torchvision
- numpy
- matplotlib
- jupyter

---

**Author:** Khushi Choudhary  
**Course:** CSCI 611 - Spring 2025
