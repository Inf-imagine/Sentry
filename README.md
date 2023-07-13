![Sentry-Image](assets/Sentry-Image-logo.png)

# Sentry-Image: Detect Any AI-generated Images
<p align="center">
🤗 <a href="http://sentry.infimagine.com/" target="_blank">Demo & Leaderboard</a> • 🐦 <a href="" target="_blank">Twitter</a> • 📃 <a href="https://arxiv.org/abs/2304.13023" target="_blank">Paper</a>
• 📦 <a href="https://huggingface.co/datasets/InfImagine/FakeImageDataset" target="_blank">Dataset</a> <br>
</p>



Sentry-Image is an open-source project for detecting AI-generated contents. The core features will include:
* The weights, training code and evaluation code for state-of-the-art AI-generated contents detection models.
* The training, validation and test [datasets](https://huggingface.co/datasets/InfImagine/FakeImageDataset) for [Sentry-Image Leaderboard](http://sentry.infimagine.com/).

Why we need Sentry-Image?
* 🧐 Recent [study](https://arxiv.org/abs/2304.13023) have shown that humans struggle significantly to distinguish real photos from AI-generated ones, with a misclassification rate of **38.7%**.

* 🤗 To help people confirm whether the images they see are real images or AI-generated images, we launched the Sentry-Image project.

* 💻 Sentry-Image is an open source project which provides the SOTA fake image detection models in [Sentry-Image Leaderboard](http://sentry.infimagine.com/) to detect whether the image provided is an AI-generated or real image.

Stay tuned for this project! Feel free to contact [contact@infimagine.com](contact@infimagine.com)! 😆 

## News
* [2023/07] We open source the [Sentry-Image repository](https://github.com/Inf-imagine/Sentry) and [Sentry-Image Demo & Leaderboard](http://sentry.infimagine.com/). 
* [2023/07] We open source the [Sentry-Image dataset](https://huggingface.co/datasets/InfImagine/FakeImageDataset). 

## Install

## Model Weights

## Fake Image Dataset
Fake Image Dataset is now open-sourced at [huggingface (InfImagine Organization)](https://huggingface.co/datasets/InfImagine/FakeImageDataset/tree/main/ImageData/train). ↗ It consists of two folders, *ImageData* and *MetaData*. *ImageData* contains the compressed packages of the Fake Image Dataset, while *MetaData* contains the labeling information of the corresponding data indicating whether they are real or fake.
### How to Download
```shell
git lfs install
git clone https://huggingface.co/datasets/InfImagine/FakeImageDataset
```

### Fake2M Dataset

| Dataset     | SD-V1.5Real-dpms-25 | IF-V1.0-dpms++-25 | StyleGAN3     |
| ----------- | :-----------:       | :-----------:     | :-----------: |
| Generator   | Diffusion           | Diffusion         | GAN           |
| Numbers     | 1M                  | 1M                | 87K           |
| Resolution  | 512                 | 256               | (>=512)       |
| Caption     | CC3M-Train          | CC3M-Train        | -             |
| ImageData Path     | ImageData/train/SDv15R-CC1M          | ImageData/train/IF-CC1M        | ImageData/train/stylegan3-80K             |
| MetaData Path     | MetaData/train/SDv15R-CC1M.csv          | MetaData/train/IF-CC1M.csv        | MetaData/train/stylegan3-80K.csv             |


## TODO
- [x] Release the training, validation datasets from MPBench.
- [ ] Release the test datasets from Sentry-Image Leaderboard.
- [ ] Release the training and evaluation code of Sentry-Image.


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
@misc{lu2023seeing,
      title = {Seeing is not always believing: Benchmarking Human and Model Perception of AI-Generated Images}, 
      author = {Zeyu Lu, Di Huang, Lei Bai, Jingjing Qu, Chengyue Wu, Xihui Liu, Wanli Ouyang},
      year = {2023},
      eprint = {2304.13023},
      archivePrefix = {arXiv},
      primaryClass = {cs.AI}
}
```