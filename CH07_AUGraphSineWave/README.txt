CH07_AUGraphSineWave

This example uses the default output Audio Unit connected to a render callback function to produce a sine wave in real-time. The frequency of the sine wave is set as the sineFrequency macro at the top of main.c.

The program runs as a command-line executable and takes no arguments, meaning you need to either run it from the command line in the Derived Data build directory, or directly from Xcode.

March 13, 2014: This example has been modernized for Xcode 5.1, and has been converted to ARC. There are no code changes compared to what's in the book.