## Label a dataset of hard hat images with White / Blue / Yellow / Person objects

This section shows you how to use Cloud Annotations to label a dataset of hard hat images with White / Blue / Yellow / Person objects.

### Lab Objectives

In this lab you will learn how to:

- Label a dataset of hard hat images with White / Blue / Yellow / Person objects using Cloud Annotations

### Hard Hat Image Data Set

Create a set of videos with individuals wearing hardhats in several industrial factory settings. Make sure to include varied scenarios with different lighting conditions. If you have different colored hats that you want to recognize, you might record video of people wearing blue, white, yellow hard hats. Use a tool to capture frames at the desired time interval from the videos in your data set.  Label each frame with objects that are of interest - blue, white, yellow hard hats and people.  Draw bounding boxes around the objects. Repeat this step for all frames.

To proceed with this code pattern example, several hundred annotated and labeled hard hat images are provided in this repository.

![Worker Safety Hard Hat Labeled Image](/images/WorkerSafety-HardHat-Labeled-Image.png)

### Cloud Annotations

Cloud Annotations makes labeling images and training machine learning models easy. Whether you’ve never touched a line of code in your life or you’re a TensorFlow ninja, the [Cloud Annotations docs](https://cloud.annotations.ai/docs) will help you build what you need.

The Cloud Annotations tool will help you [prepare the training data](https://cloud.annotations.ai/docs#preparing-training-data).  To sound the alarms, our worker safety use case needs to identify **localized hard hat objects** in the frames.

A classification model can tell you what an image is and how confident it is about it’s decision. An localized object detection model can provide you with much more information:
- **Location** : The coordinates and area of where the object is in the image.
- **Count** : The number of objects found in the image.
- **Size** : How large the object is with respect to the image dimensions.

Cloud Annotations stores the annotated labeled metadata in a file named ```_annotations.json``` and images in a directory named ```images```. Cloud Annotations stores this training set in IBM Cloud Object Storage.

### Download the Hard Hat training dataset

[Download](/dataset/hardhat-dataset.zip) the Hart Hat annotated labeled metadata and images (50MB zipfile) to your system.  In the next section we will upload the training data to IBM Cloud Object Storage (COS).

***
You are now ready to set up your IBM Cloud resources, so proceed to the next [Cloud Setup section](CLOUDSETUP.md).
