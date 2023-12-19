##  Advertising Banner Generation - Zalo AI Challenge 2023
The model achieved a score of **0.39565** from Zalo AI Benchmark, ranking **13th** among participating teams.  
A model capable of generating product advertising banners automatically, based on provided product descriptions.The goal is to produce creative and engaging banners that closely resemble human-created templates.
## Quick Start
Clone this project and install the required packages:
```
git clone https://github.com/QuagHien/advertisingbanner-generation.git
pip install -r advertisingbanner-generation/requirements.txt
```
## Data preparation
Organize data folder as follows:
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

#example data:
#gdown 1mFhnTOCFiMwsVGXOxwpQP3m5pWYHSn9P
#unzip data.zip
  ```
## Data preprocessing
Translation data to English:
```
bash advertisingbanner-generation/run/translation.sh
```
# Method: Inference from pretrained Stable Diffusion model
## Solution  
*   My team's solution is to use images in the training set as condition images to support image generation for the stable diffusion model. To retrieve images from the training set, we uses a pretrained model to extract embedding and then calculates cosine similarity to find the closest image to support image generation on the test set.
*   From our experiment, [Realistic Vision](https://civitai.com/models/4201/realistic-vision-v51) version of Stable Diffusion 5.1 can produce best realistic result.
## Step to reproduce result  
Perform generation to reproduce the result, the output image will be at "output/images" directory:
```
bash advertisingbanner-generation/run/inference.sh
```
## Limitation

*    For this solution, our team can not achieve higher score than 0.39565 from Zalo AI Benchmark.
*    With the duplication score, this method failed with dulplication score up to 0.89360.
