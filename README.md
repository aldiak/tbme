# IEEE TBME

![Method](./method.png)

## Installiation

- Create a new conda environment
```
conda create -n envname
conda activate envname
pip install -r requirements.txt
```

## Train

### Data Prepare
The datase structure is as follows:
```
dataset/  -- for training and prediction
├── train 2D/
│    ├── x_t1_data/
│    ├── x_fa_data/
│    └── y_data
└── test 2D/
│   ├── Subject ID/
│    	├── x_t1_data/
│    	├── x_fa_data/
│    	└── y_data
└── test 3D/  -- for quantitative evaluation
    ├── Subject ID/
	├── TestSet/
    		├── x_t1_data/
    		├── x_fa_data/
    		└── y_data
```
The implementation code of the dataset preprocessing steps can be found in `https://github.com/IPIS-XieLei/CNTSeg`

### Train model
Run `python train.py`

## Test
Set checkpoint path `model1_path` & prediction saving path `pred_file` in `python test.py`

Run `python test.py`

Set the above prediction saving path `pred_file` & test data path `input_label_base` & input label path `input1_label_nii` in `python get_metric.py`

you can also download our model checkpoints at [./checkpoints]

## HCP Dataset Collection
The HCP dataset can be downloaded from this address: https://db.humanconnectome.org/
NB: The ground truth is currently under restriction.

## Acknowledgements
Part of codes are reused from <a id="1">[1]</a> and <a id="2">[2]</a>

## References
<a id="1">[1]</a>
L. Xie, J. Huang, J. Yu, Q. Zeng, Q. Hu, Z. Chen, G. Xie, and Y. Feng, 
“Cntseg: A multimodal deep-learning-based network for cranial nerves tract segmentation,” 
Medical Image Analysis, vol. 86, p. 102766, 2023

<a id="2">[2]</a>
X. Deng, E. Liu, S. Li, Y. Duan, and M. Xu, 
“Interpretable multi-modal image registration network based on disentangled convolutional sparse coding,” 
IEEE Transactions on Image Processing, vol. 32, pp. 1078– 1091, 2023.


