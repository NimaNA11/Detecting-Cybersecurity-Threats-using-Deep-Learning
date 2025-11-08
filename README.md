# Detecting Cybersecurity Threats using Deep Learning

A PyTorch-based feed-forward neural network for detecting cybersecurity threats. Features are scaled, the model is trained, and accuracy is evaluated on training, validation, and test datasets.

## Project Overview

This project demonstrates a complete pipeline for threat detection: loading and scaling data, defining a neural network, training, and evaluating performance on labeled datasets.

## Requirements

- Python 3.x  
- pandas  
- scikit-learn  
- torch  
- torchmetrics  

Install dependencies with:

bash
pip install pandas scikit-learn torch torchmetrics

## How to Run

1. **Load and scale data**  
   - Read CSV files (labelled_train.csv, labelled_test.csv, labelled_validation.csv).  
   - Separate features and labels (sus_label).  
   - Scale features using StandardScaler.  
   - Convert to PyTorch tensors.

2. **Define the neural network model**  
   - nn.Sequential with 3 fully connected layers (128 → 64 → 1).  
   - ReLU activations for hidden layers, Sigmoid for output.  
   - Loss: CrossEntropyLoss (BCELoss recommended for binary classification).  
   - Optimizer: SGD (Adam recommended for faster convergence).

3. **Train the model**  
   - Training loop over specified epochs.  
   - Forward pass, compute loss, backward pass, and update parameters.

4. **Evaluate the model**  
   - Predict on training, test, and validation sets.  
   - Compute accuracy using torchmetrics.Accuracy().

## Sample Output

Training accuracy: 0.95  
Validation accuracy: 0.92  
Testing accuracy: 0.91

## Notes

- Switching to BCELoss and Adam optimizer can improve performance.  
- Ensure sus_label column exists in all CSV files.
