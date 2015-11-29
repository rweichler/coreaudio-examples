CH01_CAMetadata

This example illustrates getting metadata from an audio file like a song downloaded from iTunes or Amazon MP3. The available metadata may depend on file format, version of OS X, and what metadata the vendor has included in the file.

The program runs as a command-line executable and takes as its argument the path to an audio file, meaning you need to either run it from the command line in the Derived Data build directory, or supply arguments as part of the Xcode scheme.


March 13, 2014: This example has been modernized for Xcode 5.1, and has been converted to ARC. The following lines are different from what's printed in the book:

main.m:
Removed line 5:
    NSAutoreleasePool * pool = [[NSAutoreleasePool alloc] init];

Changed line 16 from:
	theErr = AudioFileOpenURL((CFURLRef)audioURL, kAudioFileReadPermission, 0, &audioFile); // 6
to
	theErr = AudioFileOpenURL((__bridge CFURLRef)audioURL, kAudioFileReadPermission, 0, &audioFile); // 6

Removed line 33:
    [pool drain];
