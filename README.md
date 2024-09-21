##  Advertising Banner Generation
A model capable of generating product advertising poster automatically, based on provided product descriptions.The goal is to produce creative poster that closely resemble human-created templates.
## Quick Start
Clone this project and run inference:
```
git clone https://github.com/QuagHien/text2poster.git
```

Run code: text2poster/src/inference/gen_poster.ipynb

## Data preparation
Organize data folder as follows:
  ```
  |- data/
      |- train/
          |- images/
          |- info.csv
      |- test/
          |- info.csv

#example data:
#gdown 1mFhnTOCFiMwsVGXOxwpQP3m5pWYHSn9P
#unzip data.zip
  ```
## Data preprocessing
Translation data to English:
```
bash text2poster/run/translation.sh
```
## Method: Stable Diffusion && Laying Out Stylized Texts
*   Step 1: Fine-tune UNet in Stable Diffusion

  In the first step I fine-tune UNet in the stabilityai/stable-diffusion-2-1 model with our self-collected poster background image dataset.

  Code : text2poster/src/fine-tune/fine-tune_Unet-stable-diffusion.ipynb
*   Step 2: Laying Out Stylized Texts

## Architecture

## Results
