CH04_Recorder

This example uses an Audio Queue to record from the default input device to a .caf file.

The program runs as a command-line executable and takes no arguments, meaning you need to either run it from the command line in the Derived Data build directory, or directly from Xcode. The resulting file is saved in "output.caf" in the local directory (which will be the Derived Data build directory if you run from Xcode)

March 13, 2014: This example has been modernized for Xcode 5.1, and has been converted to ARC. There are no code changes compared to what's in the book.