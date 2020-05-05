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
- Navigate to the extracted files on your computer
- Drag the ```_annotations.json``` into the bucket.
- A progress bar and a confirmation will display.

<table style="width: 100%">
    <colgroup>
       <col span="1" style="width: 33%;">
       <col span="1" style="width: 33%;">
       <col span="1" style="width: 33%;">
    </colgroup>
<tr>
<td>
<img src="/images/COS-Upload-1.png">
</td>
<td>
<img src="/images/COS-Upload-2.png">
</td>
<td>
<img src="/images/COS-Upload-3.png">
</td>
</table>

- Hold off on uploading the ```images``` folder until the next step where you will be able to upload the entire folder.
- Press the **Next** button.
- On the next panel, scroll down and press the **View bucket configuration** button.
- On the next panel, in the left navigation sidebar, click on **Objects**
- Then, expand the **Upload** dropdown, and choose **Folders**
  ![COS Folder Upload](/images/COS-Upload-Folder-1.png)
- In the popup dialog, click on **Select folders**
- A operating system file dialog will open, navigate and select the **images** folder that you have extracted.
- A progress bar and a confirmation will display as the files are uploaded.
  ![COS Folder Upload](/images/COS-Upload-Folder-2.png)
- Congratulations - You have uploaded the hardhat model dataset to IBM Cloud Object Storage.

### Create an Watson Machine Learning Instance

- Visit the [IBM Cloud Catalog](https://cloud.ibm.com/catalog/services/machine-learning)
- Search for **Watson Machine Learning**
  ![Catalog WML](/images/IBM-Cloud-Catalog-search-WML.png)
- Click on the Machine Learning tile
  ![WML Service](/images/IBM-Cloud-Catalog-WML.png)
- Click on the **Create** button
  ![WML Create](/images/IBM-Cloud-WML-Create.png)
- You now have a **Watson Machine Learning** instance which will be used to train your Hard Hat model.
  ![WML Instance](/images/IBM-Cloud-WML-Instance.png)

***
You are now ready to train your Tensorflow hard hat model, so proceed to the next [Train Model section](/part1/TRAIN.md).

***
[Home](/README.md) - [Label Data](/part1/LABEL.md) - [**Cloud Setup**](/part1/CLOUDSETUP.md) - [Train Model](/part1/TRAIN.md) - [Setup Jetson](/part2/JETSON.md) - [Edge Inferencing](/part2/EDGEINFER.md) - [Horizon Hub](/part3/HZNHUB.md) - [Horizon Client](/part3/HZNCLIENT.md) - [Docker Model](/part4/DOCKERMODEL.md) - [Horizon Deploy](/part4/HZNDEPLOY.md)
***
