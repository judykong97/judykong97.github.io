---
title: StateLens
fulltitle: "StateLens: A Reverse Engineering Solution to Making Existing Dynamic Touchscreens Accessible"
subtitle: A Reverse Engineering Solution to Making Existing Dynamic Touchscreens Accessible
category: Accessibility for Visually Impaired
layout: post
date: 2019-10-01
img: statelens.jpg
thumbnail: statelens-thumbnail.jpg
alt: image-alt
project-date: October 2019
description: I took a big part in this 2-year long project as the second author of the paper, and contributed substantially in every phase of the project - from brainstorming, to the ideation and implementation of the computer vision pipeline, then to iterations and refinements, and finally technical evaluations and user study. 
story: This work has been published at <b>UIST 2019</b>. 
---

<iframe width="100%" height="400" src="https://www.youtube.com/embed/Kbw9YbtJdwY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Motivation

Blind people frequently encounter inaccessible dynamic touchscreens in their everyday lives that are difficult, frustrating, and often impossible to use independently. Touchscreens are often the only way to control everything from coffee machines and payment terminals, to subway ticket machines and in-flight entertainment systems.

We identified two major challenges in using dynamic touchscreen interfaces for visually-impaired users: 

- As the visual user interfaces change, interactions often occur over multiple different screens, and it's always hard for users to label certain parts of the interface using traditional methods. 

- It is easy to accidentally trigger interface actions while exploring the screen. 

### System Design

![img]({{site.baseurl}}/img/projects/statelens/system-design.png)

##### **Constructing state diagram**

StateLens uses a combination of Screen Detection, SURF and OCR to match the current video frame with reference states and decide whether to send to crowdsourcing pipeline and add it as new state.

##### **Generating path from user-specified task**

With user-specified task through conversational agent, StateLens generates a target (state, button) sequence to achieve the task.

##### **Identifying current screen**

StateLens uses SURF combined with detected user interaction points from camera to identify which state the user is currently on.

##### **Providing guidance to complete task**

Based on the detected state, StateLens reads out screen description and guide users to move their finger towards the target button.

![img]({{site.baseurl}}/img/projects/statelens/example-diagram.jpg)

#### Conversational Agent

The agent can be automatically generated from the state diagram of the interface and allows users to pre-specify the task to perform.

![img]({{site.baseurl}}/img/projects/statelens/conversational-agent.jpg)

#### 3D-Printed Accessories

The 3D-printed accessories allow users to explore touchscreen interfaces without accidentally triggering touches and then touch when they need to.

![img]({{site.baseurl}}/img/projects/statelens/design-interventions.png)

### Results

In our technical evaluation, StateLens achieved a relatively stable error rate of 5% in identifying the current state. The matching time is also fairly stable for different sizes of interfaces around 0.2 seconds.

In our user study, users spent an average of 110.1 seconds  to complete a task and the overall task completion rate was 94.7%. In subjective rating, users reported the StateLens app to be  easy to learn (5.5/7), comfortable to use (5.6/7), and very useful (6.1/7). They also found the audio feedback was in real-time and accurate (6.1/7).

#### State diagram construction accuracy by interface

![img]({{site.baseurl}}/img/projects/statelens/result-table.png)

#### Matching scalability and robustness

![img]({{site.baseurl}}/img/projects/statelens/scalability-robustness.jpg)

<br><br>

For more details, please check out our [paper]({{site.baseurl}}/files/papers/StateLens_UIST2019_Accessible.pdf) and [poster]({{site.baseurl}}/files/projects/statelens/poster.pdf).






