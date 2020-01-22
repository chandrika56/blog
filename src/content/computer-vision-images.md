---
layout: post
title: 'Image Processing using Computer Vision'
author: Chandrika
tags: ['Image Processing']
image: img/ai-a-threat.png
date: '2020-01-06T23:46:37.121Z'
draft: false
---

> So you wanna learn to code for computer vision. Maybe you got a project or product to build Or just out of interest. (Im pretty sure its the first reason).

_WHY GO THROUGH THE TROUBLE OF LEARNING IT??_

_Lemme give a lil more motivation to learn. What the hell is cv and why do we need to know it?_

#### Some Uses of Computer Vision

<br/>

**Facial Recognition:** We can detect faces which helps in phone authentication or Security check. Google photos uses this to categorize the photos.<br/>
**Object Tracking:** To track an object about its movements,like in google maps.<br/>
**Object Detection:** Used in Autonomous cars to detect obstacles and avoid collision.<br/>

#### Basics of Operations on Arrays using Numpy

<br/>

Before jumping into the coding part using opencv we must have a basic knowledge on operations on arrays like indexing, slicing etc..

_But Why?_

Well how can we feed an image for processing? An image is made up of an array of pixels (kind of like small building bricks in legos). Each pixel has a numerical value assigned. So we need to have a basic knowledge on operations on arrays such indexing,slicing etc.. Numpy library supports these arrays and operations on them. We use import command is used to implement numpy library.

**Lets goof around with some Numpy library functions commands.**

**np.array()** ->List is converted to array<br/>
**np.zeros(shape=)** ->Gives an array with all values assigned with zeroes.<br/>
**shape** ->Gives number of elements in the array<br/>
**reshape(rows,col)** ->Converts the array into matrix of given shape.<br/>
**np.arange(start,end)** -> Results in array with values between start and end values<br/>
**array[row:col]** ->Slices the array to given row and column length.<br/>

#### Example Code Practice

<br/>

    > import numpy as np

    > list1=[14,56,5,6]
    > arr1=np.array(list1)
    > type(arr1)

    numpy.ndarray

<br/>

    > np.zeros(shape=(2,2))

    array([[0., 0. ],
           [0., 0.]])

<br/>

    > arr1.shape

    (4,)

<br/>

    > arr1.reshape((2,2))

    array([[14, 56],
           [ 5, 6]])

<br/>

    > bigarr=np.arange(0, 10).reshape((2,5))
    > bigarr

    array([[0, 1, 2, 3, 4],
          [5, 6, 7, 8, 9]])

<br/>

    > bigarr[:, 2]

    array([2, 7])

_For more practice on Numpy visit -https://numpy.org/devdocs/user/quickstart.html_

---

#### Show an Image

<br/>

We use a library called PIL(Python Imaging Library) and Matplotlib( For visualization) and import Image from PIL.<br/>

**Image.open(imageFilePath)** -> Opens and identifies the given image file<br/>
Each pixel has a shape. For example, (1080,1080,3) which is (pixel height,pixel width,color channels). The 3 color channels are red, green and blue(RGB).<br/>
**plt.imshow(PIL_image)** -> Displays the image

#### Display selective channels

<br/>

**plt.imshow(array[:,:,0])** -> Displays image with only Red channel. <br/>
**plt.imshow(array[:,:,1])** -> Displays image with only Green channel. <br/>
**plt.imshow(array[:,:,2])** -> Displays image with only Blue channel. <br/>

#### Display Gray image

<br/>

_What if we want a gray image like in old movies?_<br/>
The parameter cmap=’gray’ is used to convert color images into a gray image.
**plt.imshow(array[:,:,0],cmap=’gray’)** -> Displays image with grayscale values.

_Platform used:Jupyter_
