![Sentry-Image](assets/Sentry-Image-logo.png)

# Sentry-Image: Detect Any AI-generated Images
<p align="center">
📃 <a href="https://arxiv.org/abs/2304.13023" target="_blank">NeurIPS'23 Paper</a> • 🤗 <a href="http://sentry.infimagine.com/" target="_blank">Demo & Leaderboard</a> • 📋 <a href="https://docs.google.com/forms/d/e/1FAIpQLSfhYMAEnqsaxQPNfLqFEpnFxEUqBhmUoRyfPBfYVfZOx4MtLA/viewform?usp=sharing" target="_blank">Sentry-Questionnaire</a>  • 🐦 <a href="https://twitter.com/infimagine/status/1680439942063992832" target="_blank">Twitter</a> • 📦 <a href="https://huggingface.co/datasets/InfImagine/FakeImageDataset" target="_blank">Dataset</a> <br>

</p>



Sentry-Image is an open-source project for detecting AI-generated contents. The core features will include:
* The weights, training code and evaluation code for state-of-the-art AI-generated contents detection models.
* The training, validation and test [datasets](https://huggingface.co/datasets/InfImagine/FakeImageDataset) for [Sentry-Image Leaderboard](http://sentry.infimagine.com/).
* An open [questionnaire(Sentry-Questionnaire)](https://docs.google.com/forms/d/e/1FAIpQLSfhYMAEnqsaxQPNfLqFEpnFxEUqBhmUoRyfPBfYVfZOx4MtLA/viewform?usp=sharing) from HPBench.

Why we need Sentry-Image?
* 🧐 Recent [study](https://arxiv.org/abs/2304.13023) have shown that humans struggle significantly to distinguish real photos from AI-generated ones, with a misclassification rate of **38.7%**.

* 🤗 To help people confirm whether the images they see are real images or AI-generated images, we launched the Sentry-Image project.

* 💻 Sentry-Image is an open source project which provides the SOTA fake image detection models in [Sentry-Image Leaderboard](http://sentry.infimagine.com/) to detect whether the image provided is an AI-generated or real image.

Stay tuned for this project! Feel free to contact [contact@infimagine.com](contact@infimagine.com)! 😆 

## News
* [2023/07] We open source the [Sentry-Image repository](https://github.com/Inf-imagine/Sentry) and [Sentry-Image Demo & Leaderboard](http://sentry.infimagine.com/). 
* [2023/07] We open source the [Sentry-Image dataset](https://huggingface.co/datasets/InfImagine/FakeImageDataset). 
* [2023/08] We provide an open [questionnaire(Sentry-Questionnaire)](https://docs.google.com/forms/d/e/1FAIpQLSfhYMAEnqsaxQPNfLqFEpnFxEUqBhmUoRyfPBfYVfZOx4MtLA/viewform?usp=sharing) from HPBench! Now everyone can test your discriminant score against AIGC!


## Fake Image Dataset
Fake Image Dataset is now open-sourced at [huggingface (InfImagine Organization)](https://huggingface.co/datasets/InfImagine/FakeImageDataset/tree/main/ImageData/train). It consists of two folders, *ImageData* and *MetaData*. *ImageData* contains the compressed packages of the Fake Image Dataset, while *MetaData* contains the labeling information of the corresponding data indicating whether they are real or fake.
### How to Download
You can use following codes to download the dataset：
```shell
git lfs install
git clone https://huggingface.co/datasets/InfImagine/FakeImageDataset
```
You can use following codes to extract the files in each subfolder (take the *IF-CC95K* subfolder in ImageData/val/IF-CC95K as an example)：
```shell
cat IF-CC95K.tar.gz.* > IF-CC95K.tar.gz
tar -xvf IF-CC95K.tar.gz
```

### Data Organization
We recommend that your data directory should be organized like this: 
```
FakeImageDataset/
├── ImageData/
│   ├── train/
|   |   ├── IFv1-CC1M/
|   |   |   └── IFv1-dpmsolver++-50-1M/
|   |   ├── SDv15R-CC1M/
|   |   |   └── SDv15R-dpmsolver-25-1M/
|   |   └── stylegan3-80K/
|   |       ├── stylegan3-r-afhqv2-512x512/
|   |       ├── stylegan3-r-ffhqu-1024x1024/
|   |       ├── stylegan3-r-metfaces-1024x1024/
|   |       ├── stylegan3-t-afhqv2-512x512/
|   |       ├── stylegan3-t-ffhqu-1024x1024/
|   |       └── stylegan3-t-metfaces-1024x1024/
│   └── val/
|       ├── IF-CC95K/
|       |   ├── IF-ddim-25-15K/
|       |   ├── IF-ddim-50-15K/
|       |   ├── IF-ddpm-50-15K/
|       |   ├── IF-dpmsolver++-10-15K/
|       |   ├── IF-dpmsolver++-25-15K/
|       |   └── IF-dpmsolver++-50-15K/
|       ├── Midjourneyv5-5K/
|       ├── SDv15-CC30K/
|       |   ├── SDv15-dpmsolver-25-15K/
|       |   └── SDv15R-dpmsolver-25-15K/
|       ├── SDv21-CC15K/
|       |   └── SDv2-dpmsolver-25-10K/
|       ├── cogview2-22K/
|       └── stylegan3-60K/
|           ├── stylegan3-r-afhqv2-512x512/
|           ├── stylegan3-r-ffhqu-1024x1024/
|           ├── stylegan3-r-metfaces-1024x1024/
|           ├── stylegan3-t-afhqv2-512x512/
|           ├── stylegan3-t-ffhqu-1024x1024/
|           └── stylegan3-t-metfaces-1024x1024/
└── MetaData/
    ├── train/
    |   ├── IF-CC1M.csv
    |   ├── SDv15R-CC1M.csv
    |   └── stylegan3-80K.csv
    └── val/
        ├── IF-CC95K.csv
        ├── Midjourneyv5-5K.csv
        ├── SDv15-CC30K.csv
        ├── SDv21-CC15K.csv
        ├── cogview2-22K.csv
        ├── stylegan3-60K.csv
        └── stylegan3-80K.csv
```

### Training Dataset (Fake2M)

| Dataset     | SD-V1.5Real-dpms-25 | IF-V1.0-dpms++-25 | StyleGAN3     |
| :----------- | :-----------:       | :-----------:     | :-----------: |
| Generator   | Diffusion           | Diffusion         | GAN           |
| Numbers     | 1M                  | 1M                | 87K           |
| Resolution  | 512                 | 256               | (>=512)       |
| Caption     | CC3M-Train          | CC3M-Train        | -             |
| ImageData Path     | ImageData/train/SDv15R-CC1M | ImageData/train/IFv1-CC1M | ImageData/train/stylegan3-80K |
| MetaData Path     | MetaData/train/SDv15R-CC1M.csv          | MetaData/train/IF-CC1M.csv        | MetaData/train/stylegan3-80K.csv             |

### Validation Dataset (MPBench)

| Dataset     | SDv15               | SDv21             | IF            | Cogview2      | StyleGAN3     | Midjourneyv5  |
| :---------- | :-----------:       | :-----------:     | :-----------: | :-----------: | :-----------: | :-----------: |
| Generator   | Diffusion           | Diffusion         | Diffusion     | AR            | GAN           | -             |
| Numbers     | 30K                 | 15K               | 95K           | 22K           | 60K           | 5K            |
| Resolution  | 512                 | 512               | 256           | 480           | (>=512)       | (>=512)       |
| Caption     | CC15K-val           | CC15K-val         | CC15K-val     | CC15K-val     | -             | -             |
| ImageData Path | ImageData/val/SDv15-CC30K | ImageData/val/SDv21-CC15K | ImageData/val/IF-CC95K | ImageData/val/cogview2-22K | ImageData/val/stylegan3-60K | ImageData/val/Midjourneyv5-5K|
| MetaData Path  | MetaData/val/SDv15-CC30K.csv| MetaData/val/SDv21-CC15K.csv | MetaData/val/IF-CC95K.csv | MetaData/val/cogview2-22K.csv | MetaData/val/stylegan3-60K.csv | MetaData/val/Midjourneyv5-5K.csv |

### Others
**Aesthetic Quality**: 
We provide corresponding aesthetic scores for our dataset, using [CLIP-IQA](https://github.com/IceClear/CLIP-IQA).
You can download the aesthetic scores from [here](https://huggingface.co/datasets/InfImagine/FakeImageDataset/blob/main/AestheticQuality.zip) in our [huggingface dataset page](https://huggingface.co/datasets/InfImagine/FakeImageDataset/tree/main).

**Visulization**: 
We provide visualizations for our dataset, which you can find [here](assets/visualization/README.md).


## Maintenance Plan
We are currently in the process of expanding our support to include two of the latest models for the fake image dataset: Stable Diffusion XL and Midjourney V5. We have devised a comprehensive maintenance plan, as follows:
- [x] (2023.7) Release the [training, validation datasets](https://huggingface.co/datasets/InfImagine/FakeImageDataset) from MPBench.
- [x] (2023.8) Release an open [questionnaire](https://docs.google.com/forms/d/e/1FAIpQLSfhYMAEnqsaxQPNfLqFEpnFxEUqBhmUoRyfPBfYVfZOx4MtLA/viewform?usp=sharing) from HPBench!
- [ ] (2023.9) Support Stable Diffusion XL fake image dataset
- [ ] (2023.9) Release the training and evaluation code of Sentry-Image.
- [ ] (2023.10) Support Midjourney V5 fake image datset
- [ ] (2023.10) Release a new test datasets for Sentry-Image-Leaderboard.


## License
This project is open-sourced under the [Apache-2.0](https://www.apache.org/licenses/LICENSE-2.0). These weights and datasets are fully open for academic research and can be used for commercial purposes with official written permission. If you find our open-source models and datasets useful for your business, we welcome your donation to support the development of the next-generation Sentry-Image model. Please contact [contact@infimagine.com](contact@infimagine.com) for commercial licensing and donation inquiries.

## Citation
The code and model in this repository is mostly developed for or derived from the paper below. Please cite it if you find the repository helpful.
```
@misc{sentry-image-leaderboard,
      title = {Sentry-Image Leaderboard},
      author = {Zeyu Lu, Di Huang, Chunli Zhang, Chengyue Wu, Xihui Liu, Lei Bai, Wanli Ouyang},
      year = {2023},
      publisher = {InfImagine, Shanghai AI Laboratory},
      howpublished = "\url{https://github.com/Inf-imagine/Sentry}"
},
@inproceedings{lu2023seeing,
 title = {Seeing is not always believing: Benchmarking Human and Model Perception of AI-Generated Images},
 author = {Zeyu Lu, Di Huang, Lei Bai, Jingjing Qu, Chengyue Wu, Xihui Liu, Wanli Ouyang},
 booktitle = {Advances in Neural Information Processing Systems},
 year = {2023},
}
```
