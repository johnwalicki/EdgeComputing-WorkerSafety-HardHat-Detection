*Quick links :*
[Home](/README.md) - [Label Data](/part1/LABEL.md) - [Cloud Setup](/part1/CLOUDSETUP.md) - [Train Model](/part1/TRAIN.md) - [Setup Jetson](/part2/JETSON.md) - [**Edge Inferencing**](/part2/EDGEINFER.md) - [Horizon Hub](/part3/HZNHUB.md) - [Horizon Client](/part3/HZNCLIENT.md) - [Docker Model](/part4/DOCKERMODEL.md) - [Horizon Deploy](/part4/HZNDEPLOY.md)
***

# Edge Computing Worker Safety Hard Hat Detection - Section 5

## Train and Test a Hard Hat Detection Model

This section shows you how to download and test the hard hat model on your Jetson Nano.

### Lab Objectives

In this lab you will learn how to:

- Download the hard hat model with the cacli
- git clone object-detection-react
- Test model on the Jetson

### Inferencing on the Jetson

In a previous section you uploaded hard hat image training data and trained a object detection model using the Cloud Annotations command line interface, cacli, Tensorflow and Watson Machine Learning.  You also downloaded the model and tested the model on your laptop using a browser and your laptop web camera.

This section will repeat some of those steps on the Jetson Nano.

### Cloud Annotations cacli Install

Our model is already trained so we can use the Cloud Annotations command line interface, ```cacli``` to download it.

The cacli is available for Linux, Mac, Windows.  Follow the [download and installation instructions](https://cloud.annotations.ai/docs#installing-the-cli)

### Cloud Annotations - Login / List Models

- Login to your IBM Cloud account using ```cacli login``` and answer the OTP prompts
```
$ cacli login
```
  ![cacli login](/images/cacli-login.png)

- List training runs and trained models
  ```
  $ cacli list
  ```
    ![cacli list](/images/cacli-list.png)

### Download your hard hat object detection model

- Download the model
```
$ cacli download model-58sdpqyx
success download complete
```
  ![cacli download](/images/cacli-download.png)

### Install node.js

Before we can run the Object Detection web application on your Jetson Nano, these commands install Node.js

```bash
$ curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
$ sudo apt-get install -y nodejs
```

### Set up a Object Detection web application on your Jetson Nano

The [Cloud Annotations github repository](https://github.com/cloud-annotations) includes an [object detection react](https://github.com/cloud-annotations/object-detection-react) web application that you can install locally.

- Follow the [README.md instructions](https://github.com/cloud-annotations/object-detection-react/blob/master/README.md)
- (or) Run these commands:
```
$ git clone git@github.com:cloud-annotations/object-detection-react.git
$ cd object-detection-react
$ npm install
```
- Move the **model_web** directory created by the ```cacli download``` into the ```public``` folder of this repo directory. On the Ubuntu Linux system I just create a symlink.

- Start the server
```
$ npm start
```

## Test the Hard Hat model on your Jetson Nano

Now that the **object detection react** web application is running, launch Chromium on your Jetson Nano and open http://localhost:3000 to view it in the browser. Share your Jetson web camera with the browser tab.

Find your hard hat and observe the hard hat model prediction running on the Jetson!

![author with a hardhat](/images/Jetson-HardHat-Detection-Author.png)

### Congratulations - Object Detection on the Edge!

You are now ready to set up Open Horizon Exchange Hub Services, so proceed to the next [Horizon Hub Setup section](/part3/HORIZONHUB.md).

***
[Home](/README.md) - [Label Data](/part1/LABEL.md) - [Cloud Setup](/part1/CLOUDSETUP.md) - [Train Model](/part1/TRAIN.md) - [Setup Jetson](/part2/JETSON.md) - [**Edge Inferencing**](/part2/EDGEINFER.md) - [Horizon Hub](/part3/HZNHUB.md) - [Horizon Client](/part3/HZNCLIENT.md) - [Docker Model](/part4/DOCKERMODEL.md) - [Horizon Deploy](/part4/HZNDEPLOY.md)
***
