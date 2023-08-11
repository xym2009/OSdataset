# OSdataset

A high-resolution dataset for optical and SAR image registraiton. Download link: https://pan.baidu.com/s/14bqaJhMSZEy7EXcXVAc77w with the code “vriw.”

The details of construction of this dataset are given as follows,
1) We first collect 20 pairs of optical and SAR remote sensing scenes. These scene pairs locate at several cities around the world, including Beijing, Shanghai, Suzhou, Wuhan, Sanhe, Yancheng, Dengfeng, Zhongshan, and Zhuhai in China, Renne in France, Tucson, Omaha, Guam, and Jacksonville in America, and Dwarka and Agra in India. The SAR images are collected from the Chinese GaoFen-3 (GF-3), a multipolarized C-band SAR satellite. Using the spotlight imaging mode, GF-3 can provide geocoding images with 1-m resolution and 10-km ground coverage. The optical images are collected from the Google Earth platform and resampled to 1-m resolution.
2) Each image scene is tailored to image patches of 1000×1000 pixels and 50% overlapping areas. We conduct the proposed registration method on each pair of optical and SAR patches parallelly and extract the center part (512×512) of the registered patches. All the image patches are converted to unsigned 8-b integers, and image enhancement is applied to visualize the data in grayscale for SAR patches. This procedure is implemented by first normalizing the range of image amplitude to the interval 0–255, then the grayscale adjustment function “imadjust” with default parameter settings in MATLAB is performed on SAR patches. The SAR amplitude is presented in linear scale.
3) In order to remove unsatisfactory patches that contain transformation distortions or visible land cover changes, we have checked all patches visually. We can obtain 2673 patch pairs of 512×512 pixels after this step. In order to build a high-resolution dataset of patch pairs for deep learning tasks, we finally generate 10692 patch pairs of 256×256 pixels. It should be noted that the patches have no overlapping areas, data augmentation can be conveniently implemented to further increase the number of final patches. We provide patch pairs of both 512×512 and 256×256 pixels. Our dataset is shared under the open-access license CC-BY-NC.

For more details, please refer to the corresponding paper: "Automatic Registration of Optical and SAR Images Via Improved Phase Congruency Model" (https://ieeexplore.ieee.org/abstract/document/9204802).

If you are using OSdataset in your project, we kindly ask you to cite:

@article{xiang2020automatic,
  title={Automatic registration of optical and SAR images via improved phase congruency model},
  author={Xiang, Yuming and Tao, Rongshu and Wang, Feng and You, Hongjian and Han, Bing},
  journal={IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing},
  volume={13},
  pages={5847--5861},
  year={2020},
  publisher={IEEE}
}
