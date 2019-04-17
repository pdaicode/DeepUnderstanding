# Summary
# Table of contents <a name="top"></a>
1. [Image Captioning](#imagecaption)
2. [Scene Graph](#scenegraph)


# 1. Image Captioning <a name="imagecaption"></a> [[Top]](#top)

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

More details please refer to https://github.com/pdaicode/ImageVideoUnderstanding/blob/master/ImageCaptioning

# 2. Scene Graph <a name="scenegraph"></a> [[Top]](#top)
