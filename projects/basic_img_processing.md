# Image Mosaicking and Sketching Project

This project consists of two scripts: an image **mosaicking** script and an image **sketching** script. The mosaicking script creates a mosaic image from a target image by matching blocks in the target with patches from a folder. The sketching script generates a pencil sketch effect from a given image by inverting the grayscale image and applying a Gaussian blur.
Original repository : [https://github.com/simonriou/basic_img_processing](https://github.com/simonriou/basic_img_processing)

## Project Structure

- Mosaicking Script: Generates a mosaic representation of an image.
- Sketching Script: Converts an image into a pencil sketch using Gaussian blur.
- Steganography Script: Hides an image within another one using bits manipulation.
- Content-based Image Retrieval System (CBIR): Finds related images inside a dataset using log-Gabor and luminance computations.

## Requirements

Install the required Python libraries using:
```bash
pip install numpy matplotlib scikit-image scipy
```

# Mosaicking
## Usage
- Place your target image in the `Target_images/` directory and adjust the name of the target file on line 21
- Place your patches in the `patches` directory
- Run the script in your Python environment

# Sketching
## Usage
- Upload to your directory a `input.jpg` file that will be used for sketching
- Run the script in your Python environment

# Steganography
## Usage
- Upload your images to the `/imgs/` directory (check the images' names inside the script to match them), or use the provided ones.
- The script is progressively hiding the image into the other one, then decoding it.

# CBIR
## Usage
- The .zip file containing the patch images used as a dataset can be found in the root of the repository.
- Everything is pretty much explained in the script. You will be asked to enter the mode in which you want the script to run (only using Luminances and Chrominances, or only the log-Gabor filter results), then the number of the image that will be used as an input.
- Your input image is the last of the 6 displayed ones.

# License
All these projects are licensed under the MIT License.
