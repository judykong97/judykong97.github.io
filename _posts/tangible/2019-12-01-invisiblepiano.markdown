---
title: Invisible Piano
permalink: /projects/:title
fulltitle: "Invisible Piano: A Wearable Musical Instrument"
subtitle: Wearable Musical Instrument
category: Wearable Devices
layout: post
date: 2019-12-01
img: invisiblepiano.jpg
thumbnail: invisiblepiano-thumbnail.jpg
alt: image-alt
project-date: December 2019
description: In this project, I designed and prototyped a wearable musical instrument with Arduino - instead of pressing physical keys, you simply need to tap on finger tips to play music. 
story: This project is the final project for the course 05-833 Gadgets, Sensors and Activity Recognition, taught by <a href="https://www.cs.cmu.edu/~hudson/">Prof. Scott Hudson</a>.
---

<iframe width="100%" height="400" src="https://www.youtube.com/embed/UQiSj42o4Xg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Motivation

Music has always been an vital part of many people's lives. However, as many musical instruments such as guitars and pianos are always huge in volumn, it's always cumbersome to carry them around. 

### Introduction

![img]({{site.baseurl}}/img/projects/invisiblepiano/onhand.jpg)

Invisible Piano is a project that allows users to "play music in the air", by using one's finger tips as the "piano keys". When you tap on different fingers using your thumb, the device recognizes which finger was touched, and thus you can play wonderful music without using any huge musical instrument, but instead just with your body. 

### Implementation

This project was developed with an Arduino Nano. The ten "rings" to wear on a user's fingers are each connected to the Arduino, with each thumb connected to ground and all other fingers each connected to a different analog input pin. The controller identifys which finger has been touched by looking at the different input voltage from all the fingers, and with some smoothing to avoid jumping around, plays the key corresponding to that finger. 

![img]({{site.baseurl}}/img/projects/invisiblepiano/artifact.jpg)

### Tools & Technologies

Arduino

### Code

[Invisible Piano](https://github.com/judykong97/InvisiblePiano)
