CH06_ExtAudioFileConverter

This example uses an Extended Audio File Services to convert an audio file in any Core Audio-supported format to 16-big big-endian LPCM in an .aif file. The path to the file to convert is set as the kInputFileLocation macro at the top of main.c.

The program runs as a command-line executable and takes no arguments, meaning you need to either run it from the command line in the Derived Data build directory, or directly from Xcode.

March 13, 2014: This example has been modernized for Xcode 5.1, and has been converted to ARC. There are no code changes compared to what's in the book.