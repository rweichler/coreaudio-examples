CH08_AUGraphInput

This example creates an audio pass-through application by creating an AUHALOutput audio unit for input and an  AUDefaultOutput audio unit for output and connecting them by way of the CARingBuffer. The CARingBuffer class is from Apple and is not provided in this zip file -- see CARingBuffer-README for how to get it based on your current version of Xcode (as of this writing, Xcode 5.1 is current, and you will find it as part of the "Core Audio Utility Classes" sample project in Xcode's documentation viewer)

The program runs as a command-line executable and takes no arguments, meaning you need to either run it from the command line in the Derived Data build directory, or directly from Xcode.

March 13, 2014: This example has been modernized for Xcode 5.1, and has been converted to ARC. There are no code changes compared to what's in the book.