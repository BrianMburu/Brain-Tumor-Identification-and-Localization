# Brain Tumor Detection and Localization

This notebook aims to improve the speed and accuracy of detecting and localizing brain tumors based on MRI scans. It uses a dataset of 110 patients with low-grade glioma (LGG) brain tumors1. The dataset contains MRI scans and corresponding segmentation masks that indicate the presence and location of tumors.

The notebook has the following content:

1. **Introduction**: A brief overview of the project and its objectives.
2. **Import libraries and datasets**: Load the necessary Python libraries and modules, as well as the dataset from Kaggle.
3. **Perform simple data visualization**: Explore the dataset by visualizing the value counts of the masks, and plotting 12 randomly selected MRI scan images from only sick patients followed by corresponding mask.
4. **Train a classifier model to detect if tumor exists or not**: Use a pre-trained ResNet50 model2 as a base model, and add a classification head to perform binary classification on whether an MRI scan has a tumor or not.
5. **Assess trained model performance**: Evaluate the classifier model on a test set, compute the confusion matrix, and print out the classification report with metrics such as accuracy, precision, recall, and F1-score.
6. **Build a segmentation model to localize tumor**: Use a ResUNet model architecture3, which combines ResNet blocks with U-Net structure, to perform semantic segmentation on MRI scans and generate pixel-wise masks that indicate tumor regions.
7. **Train a segmentation ResUNet model to localize tumor**: Train the segmentation model on a subset of MRI scans that have tumors, using dice loss as the loss function and dice coefficient as the evaluation metric.
8. **Assess trained segmentation ResUNet model performance**: Evaluate the segmentation model on a test set, plot some predicted masks along with ground truth masks, and compute the mean dice coefficient across all test samples.##

## instructions on how to set up and run the notebook:

1. Install the required libraries by running pip install tensorflow keras matplotlib kaggle on your terminal or command prompt.

2. Download the dataset from Kaggle (https://www.kaggle.com/mateuszbuda/lgg-mri-segmentation) and extract it to a folder in your local machine.

   - In the first cell, run the command `!kaggle datasets download -d mateuszbuda/lgg-mri-segmentation` to download the dataset using the Kaggle API or Download the dataset from url manually.
   - Copy the content of the content of the Brain MRI folder into the Data folder.
   - Run the remaining cells in order, making sure to update the file paths to match the location of the dataset on your local machine.
   - To modify the notebook or experiment with different parameters, you can edit the code in the relevant cells and re-run them.

   That's it! With these steps, you should be able to set up and run the notebook to train and evaluate the brain tumor detection and localization models.

## References

1. https://www.kaggle.com/mateuszbuda/lgg-mri-segmentation
2. https://keras.io/api/applications/resnet/#resnet50-function
3. https://arxiv.org/abs/1904.00592
4. https://arxiv.org/abs/1505.04597
5. https://towardsdatascience.com/introduction-to- u-net-and-res-net-for-image-segmentation-9afcb432ee2f
