# SwinMR 

This is the official implementation of our proposed SwinMR:

Swin Transformer for Fast MRI

Please cite:

```
@article{huang2022swin,
      title={Swin Transformer for Fast MRI}, 
      author={Jiahao Huang and Yingying Fang and Yinzhe Wu and Huanjun Wu and Zhifan Gao and Yang Li and Javier Del Ser and Jun Xia and Guang Yang},
      year={2022},
      eprint={2201.03230},
      archivePrefix={arXiv},
      primaryClass={eess.IV}
}
```

![Overview_of_SwinMR](./tmp/FIG_Overview.png)


## Highlight

- A novel Swin transformer-based model for fast MRI reconstruction was proposed.
- A multi-channel loss with sensitivity maps was proposed for reserving more details.
- Comparison studies were performed to validate the robustness of our SwinMR.
- A pre-trained segmentation network was used to validate the reconstruction quality.


## Requirements

matplotlib==3.3.4

opencv-python==4.5.3.56

Pillow==8.3.2

pytorch-fid==0.2.0

scikit-image==0.17.2

scipy==1.5.4

tensorboardX==2.4

timm==0.4.12

torch==1.9.0

torchvision==0.10.0


## Training and Testing
Use different options (json files) to train different networks.

### Calgary Campinas multi-channel dataset (CC) 

To train SwinMR (PI) on CC:

`python main_train_swinmr.py --opt ./options/SwinMR/train_swinmr_CCpi_G1D30.json`

To train SwinMR (nPI) on CC:

`python main_train_swinmr.py --opt ./options/SwinMR/train_swinmr_CCnpi_G1D30.json`

To test SwinMR (PI) on CC:

`python main_test_swinmr.py --opt ./options/SwinMR/test/test_swinmr_CCpi_G1D30.json`

To test SwinMR (nPI) on CC:

`python main_test_swinmr.py --opt ./options/SwinMR/test/test_swinmr_CCnpi_G1D30.json`



This repository is based on:

SwinIR: Image Restoration Using Swin Transformer ([code](https://github.com/JingyunLiang/SwinIR) and 
[paper](https://arxiv.org/abs/2108.10257));

Swin Transformer: Hierarchical Vision Transformer using Shifted Windows
([code](https://github.com/microsoft/Swin-Transformer) and [paper](https://arxiv.org/abs/2103.14030)).