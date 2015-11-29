CH03_CAStreamFormatTester

This example inspects Core Audio's support for a given combination of file format and audio format, logging the supported format flags and bit-depths.

The program runs as a command-line executable and takes no arguments, meaning you need to either run it from the command line in the Derived Data build directory, or directly from Xcode.

March 13, 2014: This example has been modernized for Xcode 5.1, and has been converted to ARC. The following lines are different from what's printed in the book:

Removed line 5:
    NSAutoreleasePool * pool = [[NSAutoreleasePool alloc] init];

Removed line 46:
    [pool drain];
