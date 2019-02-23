---
layout: post
title: "Street Parking using Deep Learning and Computer Vision"
description: "Detects vacant and occupied parking space on a street and sends a text whenever a space is available to park"
excerpt: "Pre-trained Mask-RCNN from Matterport can be easily used to detect cars in a parking. In order to utilize it I recorded a video of the parking near my apartment. Even with my hands shaking due to cold, the overall prototype successfully detect an available parking space vacancy."
date: 2019-01-29 16:20 +0900
---

Pre-trained Mask-RCNN from Matterport can be easily used to detect cars in a parking. In order to utilize it I recorded a video of the parking near my apartment. Even with my hands shaking due to cold, the overall prototype successfully detect an available parking space vacancy.

img:![](test_vid.gif)


Pardon me for shaking hands. It was cold outside

Observe the change of color in the other parking spots. It is primarily due to moving camera while recording, the car parked in the area gets out from the marked spot. Using Twilio API, we can easy generate a number and use it to send a custom message to our own cell phone whenever there's a vacancy available to park. There's a great medium post here which describes the process flow. The underlying assumption is that, the first frame will determine the parking spots and no car in the first frame should be a moving one.


![](assumption_test1.gif)
Assumption: The first frame will determine the parking spots and no car in the first frame should be in motion


This is very inconvenient. We can't expect to take our cell phone out and get bluffed by a moving car just because it was in the first frame. So, we need to think of something better. What about identifying the static cars by observing them for 5 seconds and assuming that they are parked in the authorized parking area only. This way, no moving cars would hamper our system.

![](better_test1.gif)
Observe the passing by car at the beginning of the video. Our new method is working great!


The approach is pretty simple. I just took two frames and compared them for a possible motion using frame subtraction. Next I eroded the area occupied by the moving vehicle so that MASK-RCNN would not capture it.







For full code, check park_clever.ipynb by visiting the Git repo hereThis frame makes the operations performed in the above code very intuitive I guess



Let's check how well our system performs in night, just for the fun :)
![](night_blur_test.gif)
Credits to Mask RCNN, works pretty well even at night with a bad quality input video


What if we use IPhone 7 plus ? let's see:

![](night_better_test.gif)
Far better! It's funny how the leftmost car gets identified by MASK-RCNN with full confidence as soon as the headlights of the 'Camry' focus on it


Easy, right! Now all I have for you guys is to check my other Yolo repository to see how we can speed up the process using batch-processing. Essentially, I am asking you to read multiple frames, keep them in buffer and then send them for processing to GPU at once to maximize GPU utilization. This way you might be able to take advantage of colab's 12 GB of free K80.
Have fun and do let me know if you come up with any further cool ideas! You can find the code on my Git. The code is runnable on Google Colab.
