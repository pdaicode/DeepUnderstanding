# Review of Image Captioning Algorithms

# 1. Benchmark Algorithms

Benchmark on COCO with Karpathy's split, as reported in original paper [[Source]](https://cs.stanford.edu/people/karpathy/deepimagesent/):

| Algorithm                         | Year | B4   |METEOR| ROUGE| CIDEr | SPICE| NW   |
| -------------                     |:----:|-----:| ----:|-----:|------:|-----:|-----:|
| Kaparthy                          | 2015 | 23.0 | 19.5 |      | 66.0  |      |      |
| Show attend and tell *            | 2015 | 25.0*| 23.04*|  |  |  |  |
| Semantic Attention [[Source]](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/You_Image_Captioning_With_CVPR_2016_paper.pdf)[[Github]](https://github.com/chapternewscu/image-captioning-with-semantic-attention)| 2016 | 30.4| 24.3|  |  |  |  |
| Knowing When to Look [[Source]](https://github.com/yufengm/Adaptive)| 2017 | 33.2| 26.6|  |108.5  |  |  |
| Self Critical [[Source]](http://openaccess.thecvf.com/content_cvpr_2017/papers/Rennie_Self-Critical_Sequence_Training_CVPR_2017_paper.pdf)| 2017 | 31.9 | 25.5 | 54.3 | 106.3 |  |      |
| Convolutional Image Captioning    | 2018 | 28.1 | 24.1 | 51.9 | 89.0  | 17.1 |      |
| Bottom-Up Top-Down                | 2018 | 36.2 | 27.0 | 56.4 | 113.5 | 20.3 |      |
| Bottom-Up Top-Down, CIDEr loss    | 2018 | **36.3** | **27.7** | **56.9** | **120.1** | **21.4** |      |
| NBT                               | 2018 | 34.9 | 27.4 |      | 108.9 | 20.4 |      |
| Name                              | 2019 |  |  |  |  |  |  |

Controllability [[Source]](https://arxiv.org/abs/1811.10652)

| Algorithm                         | Year | B4   |METEOR| ROUGE| CIDEr | SPICE| NW   |
| -------------                     |:----:|-----:| ----:|-----:|------:|-----:|-----:|
| Kaparthy                          | 2015 | 23.0 | 19.5 |      | 66.0  |      |      |
| NBT                               | 2018 | 34.9 | 27.4 |      | 108.9 | 20.4 |      |
| Show Control and Tell             | 2019 | 20.9 | 24.4 | 52.5 | 193.0 | 45.3 | 0.508|
| Show Control and Tell, CIDEr+NW   | 2019 | 22.3 | 25.6 | 55.3 | **209.7** | 48.5 | 0.649|
| Name                              | 2019 |  |  |  |  |  |  |


*: not sure if use the same split


## 2.1 Experiment Setup
- Metric

[[SPICE]](https://panderson.me/spice/): Semantic Propositional Image Caption Evaluation. Peter Anderson, Basura Fernando, Mark Johnson and Stephen Gould. the European Conference on Computer Vision (ECCV), Amsterdam, the Netherlands, October 2016.

[[CIDEr]](https://www.cv-foundation.org/openaccess/content_cvpr_2015/papers/Vedantam_CIDEr_Consensus-Based_Image_2015_CVPR_paper.pdf): Consensus-based Image Description Evaluation, CVPR 2015

[[ROUGE-L]](https://en.wikipedia.org/wiki/ROUGE_(metric)): Longest Common Subsequence (LCS) based statistics [[Source]](http://aclweb.org/anthology-new/P/P04/P04-1077.pdf). Longest common subsequence problem takes into account sentence level structure similarity naturally and identifies longest co-occurring in sequence n-grams automatically.

[[METEOR]](https://en.wikipedia.org/wiki/METEOR) (Metric for Evaluation of Translation with Explicit ORdering) is a metric for the evaluation of machine translation output. The metric is based on the harmonic mean of unigram precision and recall, with recall weighted higher than precision.

[[BLEU]](https://en.wikipedia.org/wiki/BLEU) (bilingual evaluation understudy) is an algorithm for evaluating the quality of text which has been machine-translated from one natural language to another. 

- COCO

Following Karpathy's split [[Source]](https://cs.stanford.edu/people/karpathy/deepimagesent/):

You can also download the JSON blobs for all three datasets (but without the VGG CNN features) [here](./data/caption_datasets.zip)(35MB). See our Github repo for more instructions. 


---
# 3. Algorithm Summary
## 3.1 General
- Bottom-Up and Top-Down Attention for Image Captioning and Visual Question Answering, 

Peter Anderson, Xiaodong He, Chris Buehler, Damien Teney, Mark Johnson, Stephen Gould, Lei Zhang; The IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2018, pp. 6077-6086

- Convolutional Image Captioning, 

Jyoti Aneja, Aditya Deshpande, Alexander G. Schwing; The IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2018, pp. 5561-5570


- SC: self critical

https://github.com/ruotianluo/self-critical.pytorch

- reconstruction-network

## 3.2 Detection based

- NBT: neural baby talk [[code]](https://github.com/jiasenlu/NeuralBabyTalk)

```
@inproceedings{Lu2018Neural,
author = {Lu, Jiasen and Yang, Jianwei and Batra, Dhruv and Parikh, Devi},
title = {Neural Baby Talk},
booktitle = {CVPR},
year = {2018}
}
```

- Show control and tel [[code]](https://github.com/aimagelab/show-control-and-tell)

```
@inproceedings{cornia2019show,
  title={{Show, Control and Tell: A Framework for Generating Controllable and Grounded Captions}},
  author={Cornia, Marcella and Baraldi, Lorenzo and Cucchiara, Rita},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  year={2019}
}
```

## 3.3 MILA Lab
- SAT: show attend and tell [[code]](https://github.com/karpathy/neuraltalk) [[code]](https://github.com/zsdonghao/Image-Captioning)

https://github.com/sgrvinod/a-PyTorch-Tutorial-to-Image-Captioning

https://github.com/yunjey/show-attend-and-tell

```
@article{Xu2015show,
    title={Show, Attend and Tell: Neural Image Caption Generation with Visual Attention},
    author={Xu, Kelvin and Ba, Jimmy and Kiros, Ryan and Cho, Kyunghyun and Courville, Aaron and Salakhutdinov, Ruslan and Zemel, Richard and Bengio, Yoshua},
    journal={arXiv preprint arXiv:1502.03044},
    year={2015}
} 
```

## 3.4 Feifei Li
- Andrej Karpathy, Li Fei-Fei, Deep Visual-Semantic Alignments for Generating Image Descriptions, CVPR 2015 Paper

https://cs.stanford.edu/people/karpathy/deepimagesent/


# Reference
- Knowing When to Look: Adaptive Attention via A Visual Sentinel for Image Captioning, 2017
- Grounding of textual phrases in images by reconstruction, ECCV, 2016
