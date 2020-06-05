# A Python Module for interfacing with DJI Tello EDU in Cleartext SDK mode

This Python module handles the networking interfaces to control DJI Tello EDU in SDK mode and handling of telemetry data from Tello EDU. This library must use in conjuction with [Tello SDK 2.0](https://dl-cdn.ryzerobotics.com/downloads/Tello/Tello%20SDK%202.0%20User%20Guide.pdf). Please refer to Tello SDK 2.0 for the commands to control Tello EDU. 

Before using these codes, please ensure your machine has Python 3.0 and libh264decoder libraries.

## Tello Class

This tello module provides the interfacing via a Robomaster Class. 

    tello.Tello(self,tello_ip='192.168.10.1',command_port=8889,video_port=11111,telem_port=8890)

Constructor class for a Tello Object. All parameters are optional if the interfacing ports remain default to the Tello SDK 2.0. 

## Tello Object's Methods

A Tello Object provides the following public methods:

    Tello.connect(self)

> connect enters the Tello into cleartext SDK mode by sending "command" to Tello as specified by the tello_ip. This is first method to use and need not send "command" again. Returns True if successful.   

    Tello.instruct(self, instruction)

> instruct send instruction to Tello. This is to be used after Robomaster enters SDK mode. Please refer to [Tello SDK 2.0](https://dl-cdn.ryzerobotics.com/downloads/Tello/Tello%20SDK%202.0%20User%20Guide.pdf) for the format of instruction. 

    Tello.video_mode_on(self)

> video__mode_on instructs Tello to stream video out. Returns true if successful.


    Tello.readframe(self)

> read frame returns a numpy array containing a frame of h264 decoded video.


## Tello Object's Variables

Tello Object has the following public variables. These public variables are meant to provide telemetry data of the Tello robot.

Variable | Telemetry Push 
---------|----------------
Tello.batterylevel (float) | battery level 
Tello.tof (float) | reading of TOF sensors 


## Codes Examples

File Name | Objective
----------|----------
[tello_short_sample.py](https://github.com/65Drones-SDK/Tello-Video-Camera/raw/master/tello_short_sample.py)| Show basic use of Tello
[Tello with Yolo](https://github.com/65Drones-SDK/Tello-Yolo)| Show YOLO object detection using Tello Camera


(c)2020, 65Drones Pte Ltd
