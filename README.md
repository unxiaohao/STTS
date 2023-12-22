# Single Tube Text Spotter Enhancing Spatial Relationship in Chinese Scene Text Images

# Usage

- ## Installation

Python 3.8 + PyTorch 1.9.0 + CUDA 11.1 + Detectron2 (v0.6)

```
git clone https://github.com/unxiaohao/STTS.git
cd STTS
conda create -n stts python=3.8 -y
conda activate stts
pip install torch==1.9.0+cu111 torchvision==0.10.0+cu111 -f https://download.pytorch.org/whl/torch_stable.html
pip install -r requirements.txt
python -m pip install detectron2 -f https://dl.fbaipublicfiles.com/detectron2/wheels/cu111/torch1.9/index.html
python setup.py build develop
```

- ## Preparation

### Datasets

- `[SynChinese130K]` [images](https://github.com/aim-uofa/AdelaiDet/tree/master/datasets) | [annotations](https://1drv.ms/u/s!AimBgYV7JjTlgch5W0n1Iv397i0csw?e=Gq8qww)
- `[ArT]` [images](https://github.com/aim-uofa/AdelaiDet/tree/master/datasets) | [annotations](https://1drv.ms/u/s!AimBgYV7JjTlgch45d0VHNCoPC1jfQ?e=likK00)
- `[LSVT]` [images](https://github.com/aim-uofa/AdelaiDet/tree/master/datasets) | [annotations](https://1drv.ms/u/s!AimBgYV7JjTlgch7yjmrCSN0TgoO4w?e=NKd5OG)
- `[ReCTS]` [images](https://github.com/aim-uofa/AdelaiDet/tree/master/datasets) | [annotations](https://1drv.ms/u/s!AimBgYV7JjTlgch_xZ8otxFWfNgZSg?e=pdq28B)
- `[Evaluation ground-truth]` [Link](https://1drv.ms/u/s!ApEsJ9RIZdBQem-MG1TjuRWApyA?e=fVPnmT)

- ## Training

### **1. Pre-train**

```
python tools/train_net.py --config-file configs/R_50/ReCTS/pretrain.yaml --num-gpus 8
```

### **2. Fine-tune**

```
python tools/train_net.py --config-file configs/R_50/ReCTS/finetune.yaml --num-gpus 8
```

- ## Evaluation

To evaluate ICDAR 2019 ReCTS, you can directly submit the saved file to the [official website](https://rrc.cvc.uab.es/?ch=12&com=mymethods&task=4) for evaluation.

# Acknowledgement

This project is based on [Adelaidet](https://github.com/aim-uofa/AdelaiDet). For academic use, this project is licensed under the 2-clause BSD License.
