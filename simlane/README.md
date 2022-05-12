# SimLane Dataset

## Link

Data Files (list and images): [https://simlane.s3.amazonaws.com/simlane_data_list.zip](https://simlane.s3.amazonaws.com/simlane_data_list.zip)

Test Labels: [https://simlane.s3.amazonaws.com/simlane_test_label.zip](https://simlane.s3.amazonaws.com/simlane_test_label.zip)

## Description

SimLane dataset is a virtual dataset for lane detection in autonomous driving. Unlike other existing datasets (e.g., TuSimple, BDD100K, etc.), SimLane focuses on risky scenarios during driving. In particular, the dataset consists of 9 categories of environmental variations that an autonomous vehicles will drive on. The number of clips is 160. Each clip lasts about 2-3 seconds.

The SimLane dataset is collected from the [LGSVL simulator](https://github.com/lgsvl/simulator). The ground truths are automatically generated with LGSVL's Laneline Sensor and the HD Maps. The resolution of frames is (1920, 1080).


## Data Organization

SimLane is organized as the following directory structure.

```
|LaneDetection_Binary_Picked
|   Risk Category XXX
|       Scene XXX0
|           frame_1.png
|           frame_2.png
|           ...
|           frame_{n-1}.png
│           frame_{n}.png
|       Scene XXX1
|           frame_1.png
|           frame_2.png
|           ...
|           frame_{n-1}.png
│       frame_{n}.png
|list
|   test.txt    # list of test frames
|test_labe.json    # test labels following TuSimple's format
```

## Risk Description

This first release of the SimLane dataset covers the following nine risky environmental variations:

- Dawn (Hours): the agent drives during the dawn in low light conditions. Under folder ```hour_dawn```.
- Night (Hours): the agent drives during the night in low light conditions. Under folder ```hour_night```.
- No Variation: the agent drives under no risky variations. It serves as the baseline. Under folder ```novar```.
- Road Damage: the agent drives on the road with damaged surface. Under folder ```road_damage```.
- Road Graffiti: the agent drives on the road with randomly painted graffiti patterns. See [https://www.cnn.com/travel/article/graffiti-highway-closing-trnd/index.html](https://www.cnn.com/travel/article/graffiti-highway-closing-trnd/index.html) for a real-world example. Under folder ```road_graffiti```.
- Road Wetness: the agent drives on the wet road. Under folder ```road_wetness```.
- Foggy (Weather): the agent drives in foggy weather. Under folder ```weather_foggy_more```.
- Rainy (Weather): the agent drives on a rainy day. Under folder ```weather_rainy_more```.
- Worn-out Lane Marks: the agent drives on roads where some previous lane marks are not wiped out after maintenance. Under folder ```Wornout_LM```.


## A Video Demonstration

The below video shows one road wetness clip that causes an Openpilot agent (in simulation mode) to deviate from its lane and crash into a truck in the right lane.

https://user-images.githubusercontent.com/9076986/162335203-d71005c3-d727-49c4-a1ba-1f5805b75351.mp4

[![Watch the video](https://i.imgur.com/vKb2F1B.png)](https://youtu.be/vt5fpE0bzSY)
## Some Differences with Existing Datasets

1. The view direction of the camera is very close to the driving direction；

2. The lanes are around the center of sight, and we encourage the autonomous driving vehicle to focus on the current lane and left/right lanes. These lanes are essential for the control of the car.


## Reference

It would be great to cite our research article if SimLane dataset helps you project:

```

@inproceedings{
simlanedsn22,
title={SimLane: A Risk-Orientated Benchmark for Lane Detection},
author={Xinyang Zhang and Zhisheng Hu and Shengjian Guo and Zhenyu Zhong and Kang Li},
booktitle={The 52nd Annual IEEE/IFIP International Conference on Dependable Systems and Networks - Industry Track},
year={2022},
}
```
