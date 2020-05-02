---
layout: post
title: 'An Intro to Docker'
author: Chandrika
tags: ['programming']
image: img/docker.png
date: '2020-05-06T23:46:37.121Z'
draft: false
---

Have you ever built an application but it doesn't run all platforms? Or been sick of installing different dependencies and libraries for each service/component in the application? Went through the nine hills just to deploy, scale and manage a simple application??

Then DOCKER is waiting for you!!!

WHAT THE HELL IS A DOCKER?

Docker is a set of platform as a service products that uses OS-level virtualization to deliver software in packages called containers.
Well…………………...thats the GOOGLE definition for you!
To wrap it up simply,
Basically it is just a BOX!!!
Imagine a printer box, we insert a paper and get printed text or colors on it. So how is it working ? Perhaps all the colors and required material is already present in the printer.

Or consider a car wash, car is sent in, many process like washing, cleaning etc happen and at the end we get a shiny clean car (or a less rusty one).

So docker is like a printer box or car wash setup in this instance, taking an input and giving an output basically.
It is basically a box with an application and its related dependencies, libraries etc inside it
But why docker??
Imagine we are building a zoo, we toss all animals like monkeys, Lion and Crocodiles in one big park with only one kind of food and only one kind of environment, lets say, land. The bananas eaten by monkeys can’t be used by Lions and crocodiles, the meat for Lions can’t be eaten by monkeys. Monkeys want trees and crocodiles need a water space in the environment.
In similar way, if we are building an application that has services like a database and framework etc The libraries and dependencies used by databases (cassandra, postgresql, mongodb etc) may not be compatible/suitable for frameworks (strapi, nodejs express etc).
Eg:Like mongodb 4.26 might not be compatible/suitable for node js 4.16.4

To make it easy to develop, run and maintain an application and to operate on all the platforms we came up docker.
The problem in zoo example can be solved by providing each animal, a separate boundary with the required food and environment.  
In docker we have those separate boundaries called containers. We place each service in one container with all the libraries and dependencies required for it.

Container is a completely isolated environment with their own processes, network interfaces and their own mounts. Wait, doesnt it look familiar? Yes,you are right if you guessed it, they remind us of Virtual machines, If its similar to VMs, why on Earth do we need to use Containers??
Well, Each VM has a separate OS along with libraries, dependencies and application, which increases overload and utilization, making it difficult to operate it in small PCs(though we might not use). Whereas Containers share the same OS, considerably less overload and utilazation than VMs. Hence they are just the darlings preferred for application development, deployment and management.

Images:
These are readymade templates of services like mongoDb, nodejs etc to run in containers. We can either use existing images from docker.io or create our own.
Creating an Image of the service helps in shipping it for deployments. Then it is just running a simple command to get the server up and running. We dont have to worry about creating environment, installing dependencies and what not.
Simple Commands:
Suppose we want to run an image in a container, we use run command.
docker run redis

docker version: Lists the version details.

docker ps: Lists the Running containers

docker ps -a: Lists the Running & Not Running containers

docker rm:
docker rm [container ID]  
To remove a container make sure it is stopped first using stop command.

docker images: List the images

docker rmi: Removes the image

docker pull: To just download the image but not run, use pull
