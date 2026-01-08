---
title: Networked Tanks
layout: page
accent_image: ../../../../images/Portfolio-Background.jpg
---

This SFML project was created for my network programming module in my university course. Through this project I learned about network architectures and protocols, as well as latency mitigation techniques in games. The implementation of prediction and interpolation algorithms was very interesting, and helped players feel less lag while the server maintained authority. Another key part of this project was the use of a factory pattern to make the packets being sent back and forth in runtime, to efficiently pack as much data as possible per network tick. I definitely enjoyed and learned a lot from this networked project!

<img src="../../../../images/Networked-Tanks/gameplay-video-4.gif" alt="Gif showing basic gameplay" width="500" height=auto>

Follow this link to see the project code on github! [Github: FNAF Bros Brawl](https://github.com/dippy2214/assessment-project-dippy2214)
{:.faded}

It is important to note the game is built off example code given to us in lectures. The game part of this project is not my own creation, and is a fairly simple product which I added a few additional features to, but all code to handle networking and syncing in the game is entirely mine.

This is a project which I had a lot of fun with, and which I felt I learned a lot from. I came into this work with a baseline knowledge of bluetooth systems (from the [Wiimote Project](/portfolio/2025/02/25/Wiimote-Project.html)), which I think helped me a lot in understanding the basic architectures and shape of the code. A lot of design patterns seemed quite familiar to me, but there was still a lot to learn about the core networking problems in games.

One of the hardest parts of this project to tune just right was the prediction and interpolation. I tried quite a few things with both of these to get them just right, often breaking them in the process, and ended up on a method that I think works well. It predicts a consistent linear path/rotation over a set distance, and perhaps adjusting how far the prediction goes based on latency would be a better solution. However, this technique is seen in the industry and serves the task well for a server authoritative environment like my game.

<img src="../../../../images/Networked-Tanks/clumsy-latency-testing.gif" alt="Gif showing latency testing with clumsy" width="500" height=auto>

Another key point in this project, visible above, is the thorough testing that went into it. It is important when developing networked software to not only test how it holds up on local host, but also adverse network conditions - which I achieved through an app called Clumsy. Since my project ran on TCP making use of Clumsy's full testing suite was not necessary (although I did anyway out of curiosity and for my final presentation), but ensuring the program responded reasonably to high latency conditions on clients was very important. My program responds to server authority, but bullets are synced as precisely as possible to make sure the player feels like things are fair on both ends. The tanks can desync at higher latency for clients, but only the client with high latency will notice this (unfortunately Clumsy doesn't let me single out specific program instances for testing different latencys on each host).

I really enjoyed working on this project - the slightly lower level of development without a game engine felt really good to me. I hope I get another chance to work more in depth with networking, as some of the guest lectures we had as part of this module were really fascinating and didn't just talk about games!


