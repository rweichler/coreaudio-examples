CH12_MIDIToAUSampler

This example receives MIDI events and forwards them to an AUSampler audio unit to play them as notes. It requires a MIDI device such as a musical keyboard, typically connected to the Mac via a USB MIDI interface.

The program runs as a command-line executable and takes no arguments, meaning you need to either run it from the command line in the Derived Data build directory, or directly from Xcode.

March 13, 2014: This example has been modernized for Xcode 5.1, and has been converted to ARC. There are no code changes compared to what's in the book.