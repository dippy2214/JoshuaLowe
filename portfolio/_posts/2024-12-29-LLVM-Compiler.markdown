---
title: LLVM Compiler
layout: page
accent_image: ../../../../images/Portfolio-Background.jpg
---

This project is a basic compiler built in LLVM for their simple kaleidoscope language. It is something I began towards the end of summer after second year and continued on and off through till christmas in third year, and took me through some very interesting areas of programming. I don't consider this project finished, but learning how the systems our languages are build on was fascinating and I would like to revisit this area of programming at some point to flesh out what I was working on. A proper way to automatically hook this up to a development environment like VSCode is still my final end goal.

Follow this link to see the project code on github! [Github: LLVM Compiler](https://github.com/dippy2214/MyLanguage2)
{:.faded}

<img src="../../../../images/Compiler/LLVM-IR.png" alt="LLVM IR representation!" width="500" height="auto">

LLVM IR outputting evaluation of functions. It displays temporary values like addtmp when adding values together, can show error messages for unexpected syntax and understands function calls.
{:.faded} 

In it's current form this project can take lines of code written into the console and show the evaluated LLVM intermediate representation back to the console, showing that LLVM has evaluated the line of code correctly. Functions that have been defined can then be evaluated, and math operations will be run with a correct order of operations.

Without a doubt that hardest part of this project for me was trying to actually link LLVM to a project for me to actually get started. Every resource I could find for it was based on linux, which at the time I didn't have, and I had never dealt with linking such a massive library (or even anything significant at all) before. I make no exaggeration when I say that this took me months and spawned multiple side projects purely based around learning and familiarising myself with how the linker worked and how to use it (see (Github: Vector3 Library)[https://github.com/dippy2214/Vector3-Library] for the short summary of that project. In short, I remade a vector3 library similar to what unity provides, linked it to some other test programs to verify everything was working, and took the opportunity to learn about overloading operators while I was at it).

There are still major roadblocks to working on this project properly that I never quite resolved. I need to compile it through the command line making use of CMake, and I never got syntax highlighting properly working (searching through hundreds of fake errors to try to find an actual typo is a nightmare). Despite this, I have learned so much from this project. Skills like using CMake, using the C++ linker, creating system path variables, and a fundamental understanding of how compilers evaluate code and turn it into something useable were incredibly interesting to discover and I am definitely happy I chose to do this.

