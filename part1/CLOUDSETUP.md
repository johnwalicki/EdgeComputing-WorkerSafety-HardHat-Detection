*Quick links :*
[Home](/README.md) - [Label Data](/part1/LABEL.md) - [**Cloud Setup**](/part1/CLOUDSETUP.md) - [Train Model](/part1/TRAIN.md) - [Setup Jetson](/part2/JETSON.md) - [Edge Inferencing](/part2/EDGEINFER.md) - [Horizon Hub](/part3/HZNHUB.md) - [Horizon Client](/part3/HZNCLIENT.md) - [Docker Model](/part4/DOCKERMODEL.md) - [Horizon Deploy](/part4/HZNDEPLOY.md)
***

# Edge Computing Worker Safety Hard Hat Detection - Section 2

## Create IBM Cloud resources

This section shows you how to use Cloud Annotations to label a dataset of hard hat images with White / Blue / Yellow / Person objects

### Lab Objectives

In this lab you will learn how to:

- Create an instance of Cloud Object Storage (COS) in IBM Cloud
- Upload the hard hat dataset to COS
- Create Watson Machine Learning instance

### Login to IBM Cloud

- Visit [IBM Cloud](http://cloud.ibm.com) and, if you don't yet have an account, register for a (free) IBM Cloud Lite account.
![IBM Cloud login](/images/IBM-Cloud-Login.png)

### Create a Cloud Object Storage instance

- IBM Cloud will provision 25GB for free.
- Visit the [IBM Cloud Catalog](https://cloud.ibm.com/catalog/services/cloud-object-storage) COS page.
- Click on the **Create** button
  ![COS Create](/images/COS-Create.png)

### Create a Cloud Object Storage bucket

- Click on the **Create bucket** button
  ![COS Create Bucket](/images/COS-CreateBucket.png)

- Select a **Standard** predefined bucket
- Name your bucket ```hardhat-detection-<your-initials>```
- The bucket name must be unique across the whole IBM Cloud Object Storage system
  ![COS Bucket name](/images/COS-BucketName.png)
- Press the **Next** button
- Unzip the hardhat-dataset.zip that was downloaded in the previous section.
  - Make certain you extract / unzip the .zip file.
- Navigate to the files on your computer
- Drag the ```_annotations.json``` and the ```images``` directory




You are now ready to train your Tensorflow hard hat model, so proceed to the next [Train Model section](/part1/TRAIN.md).

***
[Home](/README.md) - [Label Data](/part1/LABEL.md) - [**Cloud Setup**](/part1/CLOUDSETUP.md) - [Train Model](/part1/TRAIN.md) - [Setup Jetson](/part2/JETSON.md) - [Edge Inferencing](/part2/EDGEINFER.md) - [Horizon Hub](/part3/HZNHUB.md) - [Horizon Client](/part3/HZNCLIENT.md) - [Docker Model](/part4/DOCKERMODEL.md) - [Horizon Deploy](/part4/HZNDEPLOY.md)
***
