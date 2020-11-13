# Colorizer
Black and white image colorization with OpenCV.
## Table of Content
  * [Demo](#demo)
  * [Overview](#overview)
  * [Motivation](#motivation)
  * [Technical Aspect](#technical-aspect)
  * [Installation And Run](#installation and run)
  * [Directory Tree](#directory-tree)
  * [To Do](#to-do)
  * [Bug / Feature Request](#bug---feature-request)
  * [Technologies Used](#technologies-used)
  * [Team](#team)
  * [License](#license)
  * [Credits](#credits)
## Demo
![Alt Text](https://j.gifs.com/2xVL2P.gif)

## Overview
Image colorization is the process of taking an input grayscale (black and white) image and then producing an output colorized image that represents the semantic colors and tones of the input (for example, an ocean on a clear sunny day must be plausibly “blue” — it can’t be colored “hot pink” by the model).

## Motivation

When I learned linear algebra and came to know about how the machine inteprets pictures as tensors and concept of image segmentation. I remember there were some movies which was restored and picutured in theatre. I just came across Research papers of University of california in image colorization. And most iimportantly when I colorized photos of my Grandmother with gorgeous saree, that smile in my mother's face worth it.

## Technical Aspect
- The technique we’ll be covering here today is from Zhang et al.’s 2016 ECCV paper, [Colorful Image Colorization](http://richzhang.github.io/colorization/). Developed at the University of California, Berkeley by Richard Zhang, Phillip Isola, and Alexei A. Efros.

- Previous approaches to black and white image colorization relied on manual human annotation and often produced    desaturated results that were not “believable” as true colorizations.

- Zhang et al. decided to attack the problem of image colorization by using Convolutional Neural Networks to  “hallucinate” what an input grayscale image would look like when colorized.

- To train the network Zhang et al. started with the [ImageNet dataset](http://image-net.org/) and converted all images from the RGB color space to the Lab color space.

- Similar to the RGB color space, the Lab color space has three channels. But unlike the RGB color space, Lab encodes color information differently:
  - The **L channel** encodes lightness intensity only
  - The **a channel** encodes green-red.
  - And the **b channel** encodes blue-yellow.

- As explained in the original paper, the authors, embraced the underlying uncertainty of the problem by posing it as a classification task using class-rebalancing at training time to increase the diversity of colors in the result. The Artificial Intelligent (AI) approach is implemented as a feed-forward pass in a CNN (“Convolutional Neural Network”) at test time and is trained on over a million color images.

- The color photos were decomposed using Lab model and “L channel” is used as an input feature and “a and b channels” as classification labels as shown in below diagram.



## Installation And Run 
1.The Code is written in Python 3.7. If you don't have Python installed you can find it [here](https://www.python.org/downloads/). If you are using a lower version of Python you can upgrade using the pip package, ensuring you have the latest version of pip. To install the required packages and libraries, run this command in the project directory after [cloning](https://www.howtogeek.com/451360/how-to-clone-a-github-repository/) the repository:
```bash
pip install -r requirements.txt
```
2. [Run the file with](https://docs.streamlit.io/en/stable/):
 ```bash
 $ streamlit run app.py
 ```
