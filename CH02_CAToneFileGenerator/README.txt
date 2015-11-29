CH02_CAToneFileGenerator

This example writes a sound wave to a AIFF file, sample-by-sample.

The program runs as a command-line executable and takes as its argument the frequency to produce (in Hz), meaning you need to either run it from the command line in the Derived Data build directory, or supply arguments as part of the Xcode scheme. The resulting file is saved in  the local directory (which will be the Derived Data build directory if you run from Xcode)

March 13, 2014: This example has been modernized for Xcode 5.1, and has been converted to ARC. The following lines are different from what's printed in the book:

main.m:
Removed line 11:
    NSAutoreleasePool * pool = [[NSAutoreleasePool alloc] init];

Changed line 41 from:
	audioErr = AudioFileCreateWithURL((CFURLRef)fileURL,
to
	audioErr = AudioFileCreateWithURL((__bridge CFURLRef)fileURL,

Removed line 106:
	[pool drain];
