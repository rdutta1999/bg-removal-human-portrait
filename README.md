# bg-removal-human-portrait
**Removing Background from Portrait Images using U2-Net trained with Cyclical Learning​**

This project presents a novel approach to remove the background from portrait images using the U<sup>2</sup>-Net model. It is trained using cyclical learning and generates the alpha channel transparency mask of the image. We use a custom root mean squared error-based loss function that allows the model to focus primarily on the edges of the human portrait, which is critical since those are the areas where the foreground (in our case, the human) slowly changes into the background. Since we treat this task as image Matting and predict continuous pixel values instead of discrete labels, our approach remains agnostic to the user input image resolution. The proposed method is trained and evaluated in the EasyPortrait dataset. The generated results show that our approach does indeed work and can extract the human from an image, with fine boundaries and proper transparency mask, especially near the hair and clothing.

## Dataset

**EasyPortrait** 

* Links:
[Github](https://github.com/hukenovs/easyportrait) and [Arxiv](https://arxiv.org/abs/2304.13509)

* Details:
    - Number of Images: 40,000​
    - ~38.3K FullHD+ images​
    - Size of dataset: 91.78GB​
    - Number of Unique Persons: 13,705​

![Pic1](./imgs/dataset.jpg?raw=true)


## Training Environment

* Packages / Frameworks / Compilers:​
    - Python: 3.6.13​
    - PyTorch: 1.14.x​
    - CUDA Toolkit:  10.0.130​
    - CUDNN: 7.6.5​
    - NVCC: 11.7​
    - Visual Studio Community 2019​

* Hardware:​
    - GPU: RTX 2060 Super (8GB VRAM)​
    - CPU: Ryzen 3600​
    - RAM: 16GB 3200MHz​

* Operating System: Windows 10 Pro 64bit (v22H2)​

## Pre-trained Models

The original [U<sup>2</sup>-Net](https://github.com/xuebinqin/U-2-Net) pre-trained weight file (*u2net.pth*) and our final trained model checkpoint (*final_model_ckpt.pth*) can be found [here on Google Drive](https://drive.google.com/drive/folders/1IVqR4LGcJV9aEzxEKuZ66hy0IXNV1tlq?usp=sharing).

Place the two folders - **saved_models** and **model_checkpoints** - in the root directory of the downloaded repository.

## Source Code and Packages

To train the model and do inference runs, simply run all the cells in the *Data_Mining_project.ipynb* notebook in sequential order.

To see a list of the required packages and dependencies, refer to the miniconda environment file *environment.yml*.

## Model Output

![Pic1](./imgs/model_output.png?raw=true)

## Related Report and Presentation

A report and presentation on this work can be found here (in PDF format):-

* [Report](./extras/P09_ProjectReport.pdf)
* [Presentation](./extras/P09_Presentation.pdf)