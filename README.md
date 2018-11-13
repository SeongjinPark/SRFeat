# SRFeat: Single Image Super-Resolution with Feature Discrimination
This is the implementation of the models and source code for the "SRFeat: Single Image Super-Resolution with Feature Discrimination", ECCV2018.

# File description
- config.py: inlucde configuration for file paths and hyper parameters for networks
- main_gan_init.py: code to pretrain our generator with MSE loss
- main_gan_train.py: code to train our generator with VGG loss, image GAN loss, feature GAN loss
- main_gan_eval.py: code to infernce our generator with a trained model.
- models/SRFeat_init.npz: weight model trained by main_gan_init.py 
- models/SRFeat_full.npz: weight model trained by main_gan_train.py

# Usage for testing
- Set valid paths for testset and trained models in config.py
- Run main_gan_eval.py

# Usage for training
Because directly training a network with GAN loss is difficult, we first pretrain our network with MSE loss and after train our network with GAN loss. We recommend to precompute LR images by MATLAB imresize function ('bicubic' option) for getting the same results of our paper.
- Set valid paths for dataset and validation set in config.py 
- Download vgg 19 model in [here](https://drive.google.com/open?id=1c_HRDUmbSORB51VMhR1tdPEKPdjwaDp6)
- Run main_gan_init.py (takes a few days)
- Run main_gan_train.py

# Citation
[1] @InProceedings{Park_2018_ECCV,
author = {Park, Seong-Jin and Son, Hyeongseok and Cho, Sunghyun and Hong, Ki-Sang and Lee, Seungyong},
title = {SRFeat: Single Image Super-Resolution with Feature Discrimination},
booktitle = {European Conference on Computer Vision (ECCV)},
year = {2018}
}

# Acknowledgement
- Code architecture is based on [tensorlayer-srgan](https://github.com/tensorlayer/srgan)
