---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
title: C++ Rasteriser
layout: page
accent_image: ../../../../images/Portfolio-Background.jpg
---

For this project, I aimed to make a working software rasteriser from scratch. Inspired by a video by Sebastian Lague, I wanted to test my own abilities by trying to make this in C++ with the windows API. This project had a few major roadblocks to success, including accidentally drawing 3-point shapes as rectangles and even trying to make my own shader pipeline once I was done, and I learned a lot from this lower level C++ project.

<head>
<style>
.image-container {
  display: flex;
  justify-content: center;
  gap: 30px; /* Space between images */
}

/* Individual Image Box */
.image-box {
  text-align: center;
}

.image-box img {
  width: auto; /* Adjust size as needed */
  height: 250px;
  border: 2px solid;
  border-radius: 8px;
}

.image-box p {
  margin-top: 8px;
  font-size: 14px;
}
</style>
</head>

<div class="image-container">
  <div class="image-box">
    <img src="../../../../images/Rasteriser/evilMonkeyTextured.png" alt="monkey model rendered with texture!" width="300" height="120">
    <p>rendering monkey with texture</p>
  </div>
  <div class="image-box">
    <img src="../../../../images//Rasteriser/lightingMonkey.png" alt="monkey model rendered with lighting!" width="300" height="120">
    <p>rendering monkey model with lighting from unique camera perspective</p>
  </div>
</div>

The final product of this project could render .obj models with textures (see above), had a controllable camera and could output results to a .bmp image file as a screenshot. Once I finished with the software rasteriser I also modified this to have a custom shader pipeline inspired by my work in directX - although multithreading this so it would run at a reasonable speed proved too much for me at the time, and I have yet to go back to that wide world of memory leaks.

Follow this link to see the project code on github! [Github: Rasteriser](https://github.com/dippy2214/Rasteriser)
{:.faded}



The problem I mentioned in the Intro, rendering triangles as rectangles, turned out to be one of my big learning moments of this project - specifically not prematurely optimising.

<div class="image-container">
  <div class="image-box">
    <img src="../../../../images/Rasteriser/softwarerasteriser1.jpg" alt="monkey model rendered with square bug!" width="300" height="120">
    <p>rendering monkey model with square bug</p>
  </div>
  <div class="image-box">
    <img src="../../../../images/Rasteriser/softwarerasteriser2.jpg" alt="monkey model rendered properly!" width="300" height="120">
    <p>rendering monkey correctly</p>
  </div>
</div>

In short the issue was that I made an algorithm to render the triangles in a model alongside some optimisation to use AABB collision to cut down the number of pixels on the screen I was checking for being inside my triangle. This led to me having a silly mistake in the main algorithm which I didn't catch for quite a while because I thought the issue was to do with the optimisation itself, when in reality the optimisation was just limiting the area the problem affected.

The understanding I gained through this work of rendering to the screen, and the fundamental maths behind it, expanded a lot on my knowledge from working with cameras in a games context. I am very happy I went through with this project and had a lot of fun working through it, even if I was following along with a video more than much of my other personal work. Diving into the shader pipeline on my own at the end made me really appreciate the incredible expertise and problem solving that must have been required to create something like DirectX, and I consider this project to have been a great success and fantastic learning experience.

<div class="image-container">
  <img src="../../../../images/Rasteriser/cubeAnim3.gif" alt="cube animation gif" width="400" height="200">
</div>