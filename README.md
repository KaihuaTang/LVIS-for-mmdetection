# LVIS-for-mmdetection
support [Large Vocabulary Instance Segmentation (LVIS)](https://www.lvisdataset.org/) dataset for [mmdetection](https://github.com/open-mmlab/mmdetection)


## 1. Install mmdetection

Follow the instruction of [mmdetection](https://github.com/open-mmlab/mmdetection) to install

## 2. Install LVIS-API

To evaluate the LVIS, we also need its api. Follow the [LVIS-API](https://github.com/lvis-dataset/lvis-api) to install.

## 3. Prepare the LVIS Dataset

Download all the images and annotations from the [LVIS homepage](https://www.lvisdataset.org/dataset). Organize them in the data folder as:

```
mmdetection
├── mmdet
├── tools
├── configs
├── data
│   ├── coco
│   │   ├── lvis_v0.5_train.json
│   │   ├── lvis_v0.5_val.json
│   │   ├── images
│   │   │   ├── train2017
│   │   │   ├── val2017

```

## 4. Copy Code

* Copy ```LVIS.py``` and ```LVIS_utils.py``` into ```mmdet/datasets/``` folder.
* Add ```from .LVIS import LVISDataset``` to ```mmdet/datasets/__init__.py```, and ``` 'LVISDataset' ``` to ```__all__```

## 5. Change the Config File

* You can refer to our ```htc_x101_32x4d_fpn_20e_16gpu_example.py```.
* Change ```data```, ```dataset_type``` and ```data_root```.
* Set ```rcnn.score_thr=0.00001``` and ```rcnn.max_per_img=300``` in test_cfg.

## 6. A Weird logger. 