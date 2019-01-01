## [High Quality Monocular Depth Estimation via Transfer Learning (arXiv 2018)](https://arxiv.org/abs/1812.11941)
**Ibraheem Alhashim** and **Peter Wonka**

Offical Keras (TensorFlow) implementaiton. If you have any questions or need more help with the code, feel free to contact the first author.

## Results

* KITTI
<p align="center"><img style="max-width:500px" src="https://s3-eu-west-1.amazonaws.com/densedepth/densedepth_results_01.jpg" alt="monodepth"></p>

* NYU Depth V2
<p align="center"><img style="max-width:500px" src="https://s3-eu-west-1.amazonaws.com/densedepth/densedepth_results_02.jpg" alt="monodepth"></p>

## Requirements
* This code is tested with Keras 2.2.4, Tensorflow 1.13, CUDA 9.0, on a machine with an NVIDIA Titan V and 16GB+ RAM running on Windows 10.
* Training takes about 20 hours with 4 NVIDIA Titan Xp (or above).

## Pre-trained Models
* [NYU Depth V2](https://s3-eu-west-1.amazonaws.com/densedepth/nyu.h5) (165 MB)
* [KITTI](https://s3-eu-west-1.amazonaws.com/densedepth/kitti.h5) (165 MB)

## Data
* [NYU Depth V2 (50K)](https://s3-eu-west-1.amazonaws.com/densedepth/nyu_data.zip) (4.1 GB): You don't need to extract the dataset since the code loads the entire zip file into memory when training.
* [KITTI](http://www.cvlibs.net/datasets/kitti/): copy the raw data to a folder with the path '../kitti'. Our method expects dense input depth maps, therefore, you need to run a depth [inpainting method](https://cs.nyu.edu/~silberman/datasets/nyu_depth_v2.html) on the Lidar data. For our experiments, we used our [Python re-implmentaiton](https://gist.github.com/ialhashim/be6235489a9c43c6d240e8331836586a) of the Matlab code provided with NYU Depth V2 toolbox. The entire 80K images took 2 hours on an 80 nodes cluster for inpainting. For our training, we used the subset defined [here](https://s3-eu-west-1.amazonaws.com/densedepth/kitti_train.csv).
* [Unreal-1k](https://github.com/ialhashim/DenseDepth): coming soon.

## Training
* Run `python train.py --data nyu --gpus 4 --bs 8`.

## Demo
Coming soon.

## Reference
Corresponding paper to cite:
```
@article{Alhashim2018,
  author    = {Ibraheem Alhashim and Peter Wonka},
  title     = {High Quality Monocular Depth Estimation via Transfer Learning},
  journal   = {arXiv e-prints},
  volume    = {abs/1812.11941},
  year      = {2018},
  url       = {https://arxiv.org/abs/1812.11941},
  eid       = {arXiv:1812.11941},
  eprint    = {1812.11941}
}
```
