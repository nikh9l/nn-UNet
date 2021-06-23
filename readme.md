# nnU-Net

This code is a forked repository from the [nn-UNet] (https://github.com/MIC-DKFZ/nnUNet) original repository, 
where a detailed overview of nnn-UNet is explained and maintained by the authors.

In this repo, we added a novel loss function named Log-Cosh Tversky loss by wrapping the existing Tversky loss inside a 
log-cosh funtion and comapred the preformance with other existing loss functions. We have added the trainer class for each 
loss function that has been used for comparison with the proposed loss function. The experiments conducted revelaed that 
the medical image segmentation results were improved for this loss function in terms of Specificity and accuracy metrics, along with faster convergence.

The datasets used for the experiment are MRI images of Hippocampus, Heart, Prostate from [Medical Segmentation Decathlon Challenge] (http://medicaldecathlon.com/). 
A Python Notebook explaining the steps of the experiments is added in the Notebooks folder.

A paper has been published covering the entire work in the PAKDD-2021 conference under the title 
"Addressing the class imbalance problem in Medical Image Segmentation via Accelerated Tversky Loss function". 
For more details, refer the paper <https://link.springer.com/chapter/10.1007/978-3-030-75768-7_31>.