# Monte Carlo (MC) Methods
- Demo of various MC methods relevant for Deep Learning (DL) 
- Programmed for the seminar 'Concepts in Deep Learning' at the University of Osnabrück (2024/2025) 
- By the group "Latent Architects", Hyerim Hwang and Jakob Lederer.

### MC Simulation 
This notebook demonstrates the power of Monte Carlo simulations. It includes an examples of how to use MC to estimate combinatorian event probabilities. 

### MC Dropout (MCDP)

This notebook focuses on Monte Carlo Dropout, a technique used to estimate model uncertainty in deep learning. It demonstrates how to implement MC Dropout in a neural network and evaluate its performance. The notebook includes code for training the model, applying dropout during inference, and analyzing the results. Note: Make sure to set the batch_size and epochs parameters to match the saved models' name if you want to load a pretrained model.


### Setup 

1. **Clone the repository**:
   ```bash
   git clone https://github.com/jlederer1/MC_methods
   cd MC_methods´´´

1. Create a virtual environment and install the requirements:

    ```python3 -m venv MC-env
    source MC-env/bin/activate
    pip install -r requirements.txt´´´