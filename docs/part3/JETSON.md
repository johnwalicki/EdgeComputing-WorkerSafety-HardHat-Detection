*Quick links :*
[Home](/README.md) - [Label Data](/part1/LABEL.md) - [Cloud Setup](/part1/CLOUDSETUP.md) - [Train Model](/part1/TRAIN.md) - [**Setup Jetson**](/part2/JETSON.md) - [Edge Inferencing](/part2/EDGEINFER.md) - [Horizon Hub](/part3/HZNHUB.md) - [Horizon Client](/part3/HZNCLIENT.md) - [Docker Model](/part4/DOCKERMODEL.md) - [Horizon Deploy](/part4/HZNDEPLOY.md)
***

# Edge Computing Worker Safety Hard Hat Detection - Section 4

## Jetson Nano setup

This section shows you how to configure a Jetson Nano to run object detection.

### Lab Objectives

In this lab you will learn how to:

- Set up a Jetson Nano with Ubuntu
- Attach a USB webcam, use a 5V barrel power supply to provide sufficient power

### Set up a Jetson Nano Developer Kit

Nvidia provides thorough setup  [documentation on the Jetson Nano Developer Kit](https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit) so this guide will not attempt to reproduce those steps.  In addition, there are [numerous Internet resources](https://www.hackster.io/news/getting-started-with-the-nvidia-jetson-nano-developer-kit-43aa7c298797) that walk through the configuration and setup.

 ![Jetson Nano hardware picture](https://developer.nvidia.com/sites/default/files/akamai/embedded/images/jetsonNano/gettingStarted/jetson-nano-dev-kit-top-r6-HR-B01.png)

This tutorial will emphasize several parts of those guides that can assure a successful implementation of the Worker Safety and Hard Hat Detection model.

#### 5V Barrel Jack Power Adapter

The Jetson Nano can be powered by a Micro-USB 5V 2A power supply but the camera and GPU require additional power to operate. Avoid the frustration of indeterminate results and switch to a 5V barrel jack power supply (4A).  Closing the J48 jumper with a standard 2.54mm pitch jumper will switch the power from the micro USB jack to the barrel jack. Follow the [recommended instructions](https://forums.developer.nvidia.com/t/power-supply-considerations-for-jetson-nano-developer-kit/71637) to close jumper J48 on the Nano PCB.

Once you are powering the Jetson Nano with a 5V barrel jack power supply, you can enable the 'maximum performance model' and the system and inferencing should run faster.

```bash
sudo nvpmodel -m 0
```

### Attach a USB Web camera

Object Detection does not require the highest quality camera.  Most images will get scaled down. Find a reasonably priced webcam.  The Sony Play Station Eye Camera for PS3 is only a few dollars. Check for Linux compatibility when making your choice.

### Internet Connectivity

You will need an ethernet cable (the Jetson Nano developer kit does not include WiFi) or a WiFi USB dongle.

### Now the fun begins!

You are now ready to run the hard hat model on the Jetson edge device, so proceed to the next [Edge Inferencing section](/part2/EDGEINFER.md).


***
[Home](/README.md) - [Label Data](/part1/LABEL.md) - [Cloud Setup](/part1/CLOUDSETUP.md) - [Train Model](/part1/TRAIN.md) - [**Setup Jetson**](/part2/JETSON.md) - [Edge Inferencing](/part2/EDGEINFER.md) - [Horizon Hub](/part3/HZNHUB.md) - [Horizon Client](/part3/HZNCLIENT.md) - [Docker Model](/part4/DOCKERMODEL.md) - [Horizon Deploy](/part4/HZNDEPLOY.md)
***
