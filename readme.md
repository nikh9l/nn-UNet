# nnU-Net

This code is a forked repository from the [nn-UNet](https://github.com/MIC-DKFZ/nnUNet) original repository, 
where a detailed overview of nnn-UNet is explained and maintained by the authors.

In this repo, we added a novel loss function named Log-Cosh Tversky loss by wrapping the existing Tversky loss inside a 
log-cosh funtion and comapred the preformance with other existing loss functions. We have added the trainer class for each 
loss function that has been used for comparison with the proposed loss function. The experiments conducted revelaed that 
the medical image segmentation results were improved for this loss function in terms of Specificity and accuracy metrics, along with faster convergence.

The datasets used for the experiment are MRI images of Hippocampus, Heart, Prostate from [Medical Segmentation Decathlon Challenge](http://medicaldecathlon.com/) and 
the execution is done on Google Colab environment.

Instructions - 
* Download the datasets from Medical Segmentation Decathlon (MSD) challenge. for datasets other than MSD, convert them into structured format that resembles the MSD directory structure.
* Mount the drive onto Colab to store the code repo
* Set a base directory to install the libraries and nn-UNet framework
* Upload the datasets into the base directory as mentioned [here](https://github.com/MIC-DKFZ/nnUNet/blob/master/documentation/setting_up_paths.md)
* Clone the repository and install dependencies and libraries
* Set the environment variables mentioning the location of input dataset folders and output folders to store the result
* Mention the Task name i.e., the dataset name to be used. Follow the naming convention as mentioned [here](https://github.com/MIC-DKFZ/nnUNet/blob/master/documentation/dataset_conversion.md)
* Run plan and preprocess script to configure the dataset and pipeline fingerprints
* Choose the U-Net variant and appropriate trainer class corresponding to the loss function and start the training
* Run the inference script to predict the results
* The results are generated in JSON file and are stored in the above mentioned results folder.


A Python Notebook explaining the steps of the experiments is added in the [Notebook](https://github.com/nikh9l/nn-UNet/tree/main/Notebook) folder.

A paper has been published covering the entire work in the PAKDD-2021 conference under the title 
"Addressing the class imbalance problem in Medical Image Segmentation via Accelerated Tversky Loss function". 
For more details, refer the [paper](https://link.springer.com/chapter/10.1007/978-3-030-75768-7_31).

@InProceedings{10.1007/978-3-030-75768-7_31,
author="Nasalwai, Nikhil
and Punn, Narinder Singh
and Sonbhadra, Sanjay Kumar
and Agarwal, Sonali",
editor="Karlapalem, Kamal
and Cheng, Hong
and Ramakrishnan, Naren
and Agrawal, R. K.
and Reddy, P. Krishna
and Srivastava, Jaideep
and Chakraborty, Tanmoy",
title="Addressing the Class Imbalance Problem in Medical Image Segmentation via Accelerated Tversky Loss Function",
booktitle="Advances in Knowledge Discovery and Data Mining",
year="2021",
publisher="Springer International Publishing",
address="Cham",
pages="390--402",
abstract="Image segmentation in the medical domain has gained a lot of research interest in recent years with the advancements in deep learning algorithms and related technologies. Medical image datasets are often imbalanced and to handle the imbalance problem, deep learning models are equipped with modified loss functions to effectively penalize the training weights for false predictions and conduct unbiased learning. Recent works have introduced various loss functions suitable for certain scenarios of segmentation. In this paper, we have explored the existing loss functions that are widely used for medical image segmentation, following which an accelerated Tversky loss (ATL) function is proposed that uses log cosh function to better optimize the gradients. The no-new U-Net (nn-Unet) model is adopted as the base model to validate the behaviour of the loss functions by using the standard benchmark segmentation performance metrics. To establish the robustness and effectiveness of the loss functions, multiple datasets are adopted, where ATL function illustrated better performance with faster convergence and better mask generation.",
isbn="978-3-030-75768-7"
}