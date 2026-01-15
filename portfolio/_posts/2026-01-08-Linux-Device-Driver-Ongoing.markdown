---
title: Linux Wiimote Device Driver
layout: page
accent_image: ../../../../images/Portfolio-Background.jpg

---

This project is device driver made on linux for the nintendo wii remote (written in C). I chose the wiimote as it is a device I already know relatively well, and the focus of this project was to be a test of my learning on device drivers rather than the device itself. To make this I spend my time outside of uni teaching myself how device drivers work, and this project combines that learning to create a driver which expands on a regular HID driver using raw input, uses linux's input API for communication with user and has a sysfs entry for device settings.

Follow this link to see the project code on github! [Github: Linux Device Driver](https://github.com/dippy2214/Wiimote-Driver)
{:.faded}

Throughout this project I made a particular effort to follow the naming conventions and best practices of the linux kernel. Being my first proper project in C, a couple of things felt unfamiliar to me (such as the use of !! to convert any number into a 0 or 1, effectively making integers into bools), but I found the language quite intuitive and even preferred it to C++, my main specialization. 

One of the problems I had to overcome in this project was the decision of how the user should interact with the device. There are many options for this, between procfs and sysfs, plus linux's input API. In the end I chose a combination of sysfs and the input API. this let the wiimote be globally compatible with developer standards and gave easy compatibility with it's inputs, and the sysfs file can be used to change device settings such as report mode, rumble and LED lights. This decision follows the current standard for device drivers, and I am happy I was able to evaluate these systems and come to a correct and useful answer.

In general the whole process was quite intuitive for me. I find the linux systems to be very well designed for developers and well documented, making the experience much nicer than it could otherwise have been as a beginner - after I knew what to look for. The only part of the process that wasn't intuitive was vim, which I had decided to use as the text editor for this project. The benefits of knowing a universally standard commmand line text editor became apparent to me after I started using ssh to access my raspberry pi, and I thought that this would be the perfect project to try it out properly. I enjoyed this quite a lot, and the hotkeys only feel better each time I try them, so I will definitely be back to this for more in future projects.
