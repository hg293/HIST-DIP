# Deep Image Prior for Image Restoration

**If you use this code, please cite our paper: [DOI: ...](https://doi.org/...)**

This repository contains code for image restoration using the Deep Image Prior framework. The code is provided in Google Colab notebook format for easy execution and experimentation.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Code Structure](#code-structure)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)

## Overview

The project implements an image restoration pipeline using a neural network without any prior training data. It leverages the concept of Deep Image Prior, where the structure of the network itself serves as an image prior. The code performs the following steps:

- Loads and preprocesses images.
- Applies histogram-based thresholding to create masks.
- Multiplies the original image with the mask to emphasize regions of interest.
- Initializes and trains a neural network to restore the image.
- Saves output images after each iteration.
- Calculates performance metrics like PSNR and CNR.

## Features

- **Deep Image Prior Framework**: Uses an untrained neural network for image restoration.
- **Histogram-Based Thresholding**: Enhances specific regions of the image based on histogram analysis.
- **Custom Neural Network Architectures**: Implements skip connection networks with custom layers.
- **Optimization and Loss Functions**: Includes MSE and Total Variation loss, optimized using Adam.
- **Performance Metrics**: Calculates PSNR and CNR to evaluate image quality.
- **Output Images**: Saves images after each iteration for visualization and analysis.
- **Colab Notebook**: The code is provided in a Google Colab notebook for ease of use.

## Requirements

- Google Colab account (optional but recommended)
- Python 3.6 or higher
- PyTorch
- NumPy
- OpenCV
- PIL (Python Imaging Library)
- Matplotlib
- torchvision

## Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/your_username/HIST-DIP.git
   cd HIST-DIP
   ```

2. **Open in Google Colab**

   - Upload the notebook to your Google Drive.
   - Open the notebook using Google Colab.

3. **Install Dependencies**

   In the first cell of the notebook, ensure you have the necessary installations:

   ```python
   !pip install torch torchvision opencv-python matplotlib
   ```

   **Note**: Some libraries like NumPy and PIL are pre-installed in Colab.

## Usage

1. **Prepare Your Images**

   - Place your input images in the Colab environment.
   - Example images used in the code are `shaky.tif` and `b.jpg`.

2. **Run the Notebook**

   - Execute the cells in order.
   - The notebook will guide you through the image restoration process.

3. **Monitor the Output**

   - Output images after each iteration will be saved in the `output images` folder in your Colab environment.
   - PSNR and CNR values will be displayed in the notebook.
   - A final restored image will be saved as `final_output_image.png`.

## Code Structure

- **Imports and Configurations**: Imports necessary libraries and sets up configurations like device settings.

- **Utility Functions**: Contains functions for image loading, processing, and visualization.

  - `get_image()`: Loads and resizes images.
  - `pil_to_np()`: Converts PIL images to NumPy arrays.
  - `np_to_pil()`: Converts NumPy arrays to PIL images.
  - `plot_image_grid()`: Plots images in a grid.
  - `calculate_cnr()`: Calculates the Contrast-to-Noise Ratio.
  - `psnr()`: Calculates the Peak Signal-to-Noise Ratio.

- **Neural Network Components**:

  - Custom layers like `Downsampler`, `Concat`, and activation functions.
  - `get_net()`: Builds the neural network architecture.

- **Histogram-Based Thresholding**:

  - Computes the histogram of the image.
  - Applies a manual threshold to create a binary mask.

- **Image Multiplication**:

  - Multiplies the original image with the mask to emphasize regions of interest.

- **Training Loop**:

  - Defines the `closure()` function, which includes the forward and backward passes.
  - Uses the `optimize()` function to perform optimization over a specified number of iterations.
  - Saves images after each iteration in the `output images` folder.

- **Performance Evaluation**:

  - Plots PSNR over iterations.
  - Calculates CNR for the original and improved images.

## Results

- **Restored Images**: The network outputs high-resolution restored images saved in the `output images` folder and as `final_output_image.png`.

- **PSNR Plot**: A plot showing PSNR over iterations to visualize the training progress.

- **CNR Improvement**: The calculated CNR values demonstrate the enhancement in contrast between regions of interest and the background.

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Commit your changes with clear messages.
4. Push your branch to your forked repository.
5. Create a Pull Request describing your changes.

## License

This project is licensed under the [MIT License](LICENSE).

---

**Disclaimer**: This code is provided as-is for educational purposes. Ensure you have the rights to use any images you process with this code. Use appropriate caution when working with large images or computationally intensive tasks.

---

If you have any questions or issues, please open an issue on GitHub.

---

[Back to top](#deep-image-prior-for-image-restoration)

---
