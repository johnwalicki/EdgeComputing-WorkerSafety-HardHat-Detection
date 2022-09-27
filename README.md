# This tutorial has been archived

# Edge Computing Worker Safety Hard Hat Detection
Protect workers with a TensorFlow Hard Hat object detection model running on a Jetson Nano

## Overview

In this code pattern, we will describe how to implement a workplace safety use case using open source edge computing technologies and IBM's management architecture for deploying AI workloads to edge devices.

In many factory environments, when employees enter a designated area, they must be wearing proper Personal Protective Equipment (PPE) such as a hard hat. This pattern demonstrates a solution which monitors the designated area and issues an alert only when an employee has been detected and is not wearing a hard hat. To reduce load on the network, the video stream object detection will be performed on edge devices managed by Open Horizon and IBM Edge Application Manager.

To implement the architecture, the following components are required:

- Models need to be trained to identify a person wearing a hard hat. This is accomplished using IBM Cloud Annotations and Watson Machine Learning.

- The models need to be containerized and deployed to the edge. This is accomplished using [Open Horizon](https://www.lfedge.org/projects/openhorizon/)

- Models need to be deployed to the camera to identify a human which will trigger the camera to start streaming. This is done using [IBM Edge Application Manager](https://developer.ibm.com/components/ibm-edge-application-manager/).


## Architecture diagram

The following diagram shows the workflow for the workplace safety hard hat detection system.

![Edge Architecture Diagram](/images/edge-objectdetection-arch-diagram.png)

## Learning Objectives:
In this code pattern you will learn how to:

### Part 1

- Label a dataset of hard hat images with White / Blue / Yellow / Person objects using Cloud Annotations
- Create an instance of Cloud Object Storage (COS) in IBM Cloud
- Upload the hard hat dataset to COS
- Create a Watson Machine Learning instance
- Install Cloud Annotations command line interface - cacli
- Train a Tensorflow model using Watson Machine Learning
- Download the model with the cacli
- git clone object-detection-react
- Test model on your laptop

### Part 2

- Set up a Jetson Nano with Ubuntu
- Attach a USB webcam and use a 5V barrel power supply to provide sufficient power
- Download the hard hat model with the cacli
- git clone object-detection-react
- Test model on the Jetson

### Part 3

- Set up a laptop with HZN Exchange Hub Services
- Install docker on your Jetson Nano
- Install Open Horizon HZN anax client
- Register the Jetson into the Hub using the Open Horizon HZN anax client

### Part 4

- Build a docker image which contains the model
- Register the workload pattern on the Exchange server
- Deploy the pattern to the edge device


## Prerequisites
This tutorial can be completed using an IBM Cloud Lite account.

- Create an [IBM Cloud account](https://cloud.ibm.com)
- Log into [IBM Cloud](https://cloud.ibm.com/login)
- Nvidia Jetson Nano
  - If you do not have a Jetson Nano or Jetson TX2, you can still complete Sections 1,2,3

## Part 1 - Build a Hard Hat Object Detection Model

### Section 1 - Label a dataset of hard hat images with White / Blue / Yellow / Person objects

This section shows you how to use Cloud Annotations to label a dataset of hard hat images with White / Blue / Yellow / Person objects

- Instructions : [Label Hard Hat Data](part1/LABEL.md)

### Section 2 - Create IBM Cloud resources

This section shows you how to create an instance of Cloud Object Storage (COS) in IBM Cloud. Create a COS bucket and upload the hard hat dataset to COS.  Finally create Watson Machine Learning instance.

- Instructions : [Create IBM Cloud Resources](part1/CLOUDSETUP.md)

### Section 3 - Train and Test a Hard Hat Detection Model

This section demonstrates how to install the Cloud Annotations cacli, train a Tensorflow model, download the model, set up a sample localhost web application and test model on your laptop.

- Instructions : [Train your Hard Hat model](part1/TRAIN.md)

## Part 2 - Configure a Jetson Nano

### Section 4 - Jetson Nano setup

This section shows you how to configure a Jetson Nano to run object detection.

- Instructions : [Configure Nvidia Jetson Nano](part2/JETSON.md)

### Section 5 - Deploy and Test Hard Hat Object Detection

This section shows you how to download and test the hard hat model.

- Instructions : [Deploy / Test Model on the Jetson](part2/EDGEINFER.md)

## Part 3 - Open Horizon

### Section 6 - Open Horizon Exchange Hub

This section guides you through the set up of a laptop with HZN Exchange Hub Services

- Instructions : [Open Horizon Exchange Hub Services](part3/HZNHUB.md)

### Section 7 - Open Horizon client setup

Learn how to install Open Horizon HZN anax client and register the Jetson HZN anax client into your hub.

- Instructions : [Open Horizon agent on the Jetson](part3/HZNCLIENT.md)

## Part 4 -

### Section 8 - Containizer your model in a Docker image

This section shows you how to build a docker image with a model

- Instructions : [Build a Docker Image](part4/DOCKERMODEL.md)

### Section 9 - Register and deploy the Pattern to the edge

This final section demonstrates how to register the workload pattern on the Exchange server and deploy the pattern to the edge device.

- Instructions : [Deploy Horizon Pattern](part4/HZNDEPLOY.md)

___
[**Home**](/README.md) - [Label Data](/part1/LABEL.md) - [Cloud Setup](/part1/CLOUDSETUP.md) - [Train Model](/part1/TRAIN.md) - [Setup Jetson](/part2/JETSON.md) - [Edge Inferencing](/part2/EDGEINFER.md) - [Horizon Hub](/part3/HZNHUB.md) - [Horizon Client](/part3/HZNCLIENT.md) - [Docker Model](/part4/DOCKERMODEL.md) - [Horizon Deploy](/part4/HZNDEPLOY.md)
___

Enjoy!  Give me [feedback](https://github.com/johnwalicki/EdgeComputing-WorkerSafety-HardHat-Detection/issues) if you have suggestions on how to improve this workshop.

## License

This workshop and code examples are licensed under the Apache Software License, Version 2.  Separate third party code objects invoked within this code pattern are licensed by their respective providers pursuant to their own separate licenses. Contributions are subject to the [Developer Certificate of Origin, Version 1.1 (DCO)](https://developercertificate.org/) and the [Apache Software License, Version 2](http://www.apache.org/licenses/LICENSE-2.0.txt).

[Apache Software License (ASL) FAQ](http://www.apache.org/foundation/license-faq.html#WhatDoesItMEAN)
