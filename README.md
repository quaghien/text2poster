# Advertisement-Banner-Generation-ZaloAI23
Inference from pretrained Stable Diffusion model
## Quick Start
Clone this project and install the required packages:
```
    git clone https://github.com/QuagHien/BannerGeneration-ZaloAI23.git
    pip install -r requirements.txt
```
## Data preparation
Organize dataset folder as follows:
  ```
    |- data/
    |- train/
        |- images/
        |- info.csv
        |- info_trans.csv # Translated train data
        |- ...
    |- test/
        |- info.csv
        |- info_trans.csv # Translated test data
        |- ...
  ```
## Data preprocessing
Translation data to English:
```
    bash run/translation.sh
```
# Method: Inference from pretrained Stable Diffusion model
## Solution
Our team's solution is to use images in the training set as condition images to 

*   support image generation for the stable diffusion model. To retrieve images from the training set, we uses a pretrained model to extract embedding and then calculates cosine similarity to find the closest image to support image generation on the test set.
*   From our experiment, Realistic Vision version of Stable Diffusion 1.5 can produce best realistic result.
##Step to reproduce result
Perform generation to reproduce the result, the output image will be at "output/images" directory:
```
    bash run/inference.sh
```
## Limitation

*    For this solution, our team can not achieve higher score than 0.39565 from Zalo AI Benchmark.
*    With the duplication score, this method failed with dulplication score up to 0.89360.
