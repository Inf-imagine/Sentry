![Sentry-Image](assets/Sentry-Image-logo.png)

# Sentry-Image: Detect Any AI-generated Images
<p align="center">
🤗 <a href="http://sentry.infimagine.com/" target="_blank">Sentry-Image Demo & Leaderboard</a> • 🐦 <a href="" target="_blank">Twitter</a> • 📃 <a href="https://arxiv.org/abs/2304.13023" target="_blank">Sentry-Image Paper</a> <br>
</p>



Sentry-Image is an open-source project for detecting AI-generated contents. The core features will include:
* The weights, training code and evaluation code for state-of-the-art AI-generated contents detection models.
* The training, validation and test datasets for [Sentry-Image Leaderboard](http://sentry.infimagine.com/).

Why we need Sentry-Image?
* 🧐 Recent [study](https://arxiv.org/abs/2304.13023) have shown that humans struggle significantly to distinguish real photos from AI-generated ones, with a misclassification rate of **38.7%**.

* 🤗 To help people confirm whether the images they see are real images or AI-generated images, we launched the Sentry-Image project.

* 💻 Sentry-Image is an open source project which provides the SOTA fake image detection models in [Sentry-Image Leaderboard](http://sentry.infimagine.com/) to detect whether the image provided is an AI-generated or real image.

Stay tuned for this project! Feel free to contact [contact@infimagine.com](contact@infimagine.com)! 😆 

## News
* [2023/07] We open source the [Sentry-Image repository](https://github.com/Inf-imagine/Sentry) and [Sentry-Image Demo & Leaderboard](http://sentry.infimagine.com/). 

## Install

## Model Weights

## Dataset



## TODO
- [ ] Release the training, validation and test datasets from MPBench.
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