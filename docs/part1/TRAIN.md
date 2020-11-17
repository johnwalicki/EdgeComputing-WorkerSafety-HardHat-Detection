## Train and Test a Hard Hat Detection Model

This section demonstrates how to install the Cloud Annotations cacli, train a Tensorflow model, download the model, set up a sample localhost web application and test model on your laptop.

### Lab Objectives

In this lab you will learn how to:

- Install Cloud Annotations cacli
- Train a Tensorflow model
- Download the model with the cacli
- git clone object-detection-react
- Test model on your laptop

### Cloud Annotations cacli Install

Now that the Hard Hat training data set has been uploaded to IBM Cloud Object Storage, we can train our model using the Cloud Annotations command line interface, ```cacli```

The cacli is available for Linux, Mac, Windows.  Follow the [download and installation instructions](https://cloud.annotations.ai/docs#installing-the-cli)

### Cloud Annotations - Login / Train

- Login to your IBM Cloud account using ```cacli login``` and answer the OTP prompts
```
$ cacli login
```
  ![cacli login](/images/cacli-login.png)

- Train your hard hat object detection model
```
$ cacli train
```
- Select your ```hardhat-detection-<your_initials>``` Bucket.
  ![cacli train](/images/cacli-train1.png)
- Note the training run **Model ID**  
  ![cacli train](/images/cacli-train2.png)
- List training runs
```
$ cacli list
```
  ![cacli list](/images/cacli-list.png)
- Monitor the progress of your training runs
```
$ cacli progress model-58sdpqyx
```
  ![cacli progress](/images/cacli-progress.png)
- Wait for the model training to complete (15-30 minutes)
  ![cacli complete](/images/cacli-complete.png)
- Download the model
```
$ cacli download model-58sdpqyx
success download complete
```
  ![cacli download](/images/cacli-download.png)

### Set up a Object Detection web application on your local system

The [Cloud Annotations github repository](https://github.com/cloud-annotations) includes an [object detection react](https://github.com/cloud-annotations/object-detection-react) web application that you can install locally.

- Follow the [README.md instructions](https://github.com/cloud-annotations/object-detection-react/blob/master/README.md)
- (or) Run these commands:
```
$ git clone git@github.com:cloud-annotations/object-detection-react.git
$ cd object-detection-react
$ npm install
```
- Copy the **model_web** directory created by the ```cacli download``` and paste it into the ```public``` folder of this repo directory.   On my Linux system I just create a symlink.

- Start the server
```
$ npm start
```

## Test the Hard Hat model on your laptop

Now that the **object detection react** web application is running, open http://localhost:3000 to view it in the browser. Share your laptop camera with the browser tab.

Find your hard hat and observe the hard hat model prediction.

![author with a hardhat](/images/Sample-HardHat-Detection-Author.png)

### Congratulations

You are now ready to set up your Nvidia Jetson Nano, so proceed to the next [Jetson Setup section](/part2/).
