# DynamicControl: Adaptive Condition Selection for Improved Text-to-Image Generation

<div style="display: flex; justify-content: center; align-items: center;">
  <a href="https://arxiv.org/abs/2412.03255" style="margin: 0 2px;">
    <img src='https://img.shields.io/badge/arXiv-2411.10499-red?style=flat&logo=arXiv&logoColor=red' alt='arxiv'>
  </a>
  <a href="https://github.com/hithqd/DynamicControl" style="margin: 0 2px;">
    <img src='https://img.shields.io/badge/GitHub-Repo-blue?style=flat&logo=GitHub' alt='GitHub'>
  </a>
  <a href='https://hithqd.github.io/projects/Dynamiccontrol/' style="margin: 0 2px;">
    <img src='https://img.shields.io/badge/Webpage-Project-silver?style=flat&logo=&logoColor=orange' alt='webpage'>
  </a>
</div>

## Abstract
To enhance the controllability of text-to-image diffusion models, current ControlNet-like models have explored various control signals to dictate image attributes. However, existing methods either handle conditions inefficiently or use a fixed number of conditions, which does not fully address the complexity of multiple conditions and their potential conflicts. This underscores the need for innovative approaches to manage multiple conditions effectively for more reliable and detailed image synthesis. To address this issue, we propose a novel framework, DynamicControl , which supports dynamic combinations of diverse control signals, allowing adaptive selection of different numbers and types of conditions. Our approach begins with a double-cycle controller that generates an initial real score sorting for all input conditions by leveraging pre-trained conditional generation models and discriminative models. This controller evaluates the similarity between extracted conditions and input conditions, as well as the pixel-level similarity with the source image. Then, we integrate a Multimodal Large Language Model (MLLM) to build an efficient condition evaluator. This evaluator optimizes the ordering of conditions based on the double-cycle controller’s score ranking. Our method jointly optimizes MLLMs and diffusion models, utilizing MLLMs’ reasoning capabilities to facilitate multi-condition text-to-image (T2I) tasks. The final sorted conditions are fed into a parallel multi-control adapter, which learns feature maps from dynamic visual conditions and integrates them to modulate ControlNet, thereby enhancing control over generated images. Through both quantitative and qualitative comparisons, DynamicControl demonstrates its superiority over existing methods in terms of controllability, generation quality and composability under various conditional controls.

## Method
![image](../main/assets/framework.png) 

## Updates
- **`2025/01/09`**: The model of our **DynamicControl** is available.
- **`2024/12/04`**: Our [**DynamicControl paper**](https://arxiv.org/abs/2412.03255) is available.


## :ballot_box_with_check: TODO List
- [ ] Release the training code
- [ ] Release the inference code
- [x] Release pre-trained models


## Model Zoo
| Model | Weights | 
| :---- | :---- | 
| Canny | [model](https://drive.google.com/file/d/15WjhB5tkNpeQ39eh95yEUY4p8Q0v9TpF/view?usp=sharing) | 
| Depth | [model](https://drive.google.com/file/d/1iZkwdanzapD1NKCcXty5XAi53cJluwhV/view?usp=sharing)|
| Hed | [model](https://drive.google.com/file/d/1zO_ml2-jyXSjsuoSp5WpjhPnACBuIJ3_/view?usp=sharing) |
| Segmentation | [model](https://drive.google.com/file/d/1uz0Er6ZVTuUp6Td1dUcZnUumvct6HoKt/view?usp=sharing) |
| Openpose | [model](https://drive.google.com/file/d/1NxglWpoTZQLp5LaXdF3tUdAc3rNvVV2n/view?usp=sharing) |

![image](../main/assets/compare.png)

## Citation

If you find this repository useful in your research, please consider giving a star ⭐ and a citation
```bibtex
@article{he2024dynamiccontrol,
      title={DynamicControl: Adaptive Condition Selection for Improved Text-to-Image Generation},
      author={He, Qingdong and Peng, Jinlong and Xu, Pengcheng and Jiang, Boyuan and Hu, Xiaobin and Luo, Donghao and Liu, Yong and Wang, Yabiao and Wang, Chengjie and Li, Xiangtai and Zhang, Jiangning},
      journal={arXiv preprint arXiv:2412.03255},
      year={2024}
      }
