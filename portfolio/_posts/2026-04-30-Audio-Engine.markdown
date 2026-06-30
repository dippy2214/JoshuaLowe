---
title: Audio Engine
layout: page
accent_image: ../../../../images/Portfolio-Background.jpg
---

This project represents my coursework for my fourth year audio programming project in my time at uni. I chose to make an audio engine due to my interest in coding systems rather than implementation, and went far beyond the scope of the brief to create something that I found really satisfying. This project was built into my 3D C++ rasteriser project, and besides some use of my existing transform class it runs completely independently.

Follow this link to see the project code on github! [Github: Audio Engine](https://github.com/dippy2214/Rasteriser)
{:.faded}

The audio engine was designed with user interactions in mind. The user will request an audio source from the audio engine, and this is the primary interaction point with the engine for the user. The audio source exposes parameters to customise a volume rolloff curve and hearing ranges, an is3D bool to toggle 3D or 2D audio and parameters to tell the engine if the audio source is active or looping. The audio source memory is intended to be managed by the user, but this is a design decision that I think I would  change if I was making this engine again. The engine in its current form has a limit on the number of audio sources and it would be easier for the user to take these from an internal pool and expose only what is necessary. Audio sources are not tied to voices in theory, as I wanted to leave the option for culling and prioritising audio sources automatically in the future, but in practice the engine will stop creating new audio sources and warn the user if there are no more voices.

The other point of interaction the user has with the engine is through audio mixers. These are managed internally by the engine and exposed to the user, who can add as many audio effects as needed to this mixer which will be added to audio from all audio sources which have been attached to this mixer (The engine creates a default empty mixer for all new audio sources, which can also be changed by the user). I am very happy with how this system integrates with the engine and user interaction, and this felt very satisfying to get right.

<iframe width="560" height="315" src="https://www.youtube.com/embedded/ILEx-FsjA7s?autoplay=1&mute=1">
</iframe>

This video shows an audio demonstration, showing basic playing of audio as well as a 64 sound at once stress test (each sound is played at a fraction of normal volume to preserve our ears)
{:.faded}

Internally, the audio engine is designed to be thread safe and build off functionality from sokol audio. It utilizes only stb vorbis to read audio files, despite supporting both .wav and .ogg. This is because upon build the program utilizes ffmpeg to compress all .wav files into .ogg files. This acts as build compression, but is a trade off that I would not have made having more time to work on this project. This is because .ogg is a lossy compression format, and there are many situations where audio designers would rather have a high quality .wav file, especially for short sound effects that often get played in video games. In this project the specific implemention served more as a way to pack more features in efficiently as opposed to a real useful functionality, and I would definitely revisit this if I were to make this again outside of a university context.

There is a lot of interesting parts to this that I could talk about if not for respect for the time of those reading here, such as the engine processing ITD and ILD, working in 3D audio, learning how ring buffer implementations work and best practices for making types in C++ and how keywords get used. I learned to create pre-build processes and this project definitely expanded my understanding of make files, and I think that how much I enjoyed this module in uni really shines through in this project.