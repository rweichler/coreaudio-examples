CH10_iOSPlayThrough

This example uses an AURemoteIO audio unit to play captured audio from the mic through to the speaker or headphones, and optionally uses a render callback to apply a ring modulator effect.

Note that the AudioSession functions used in this example were deprecated after the book was published. AVAudioSession, in the AV Foundation framework, is intended as a drop-in replacement.

Note that versions of iOS released after the book's publication require explicit user approval to use the microphone. The first time this app is run, the AURemoteIO unit will produce silence because it is waiting for this approval. Once approval is given and the app is re-started, the AURemoteIO unit will be able to capture from the mic. To do this request up front, before attempting to create the AUGraph, you can use AV Foundation's -[AVCaptureDevice requestAccessForMediaType:completionHandler:], which was introduced in iOS 7.

March 13, 2014: This example has been modernized for Xcode 5.1, and has been converted to ARC. The following lines are different from what's printed in the book:

CH10_iOSPlayThroughAppDelegate.m:

Changed lines 43-4 from:
	printf ("Interrupted! inInterruptionState=%u\n", inInterruptionState);
	CH10_iOSPlayThroughAppDelegate *appDelegate = (CH10_iOSPlayThroughAppDelegate*)inUserData;
to:
	printf ("Interrupted! inInterruptionState=%u\n", (unsigned int)inInterruptionState);
	CH10_iOSPlayThroughAppDelegate *appDelegate = (__bridge CH10_iOSPlayThroughAppDelegate*)inUserData;


Changed line 127 from:
                                      self),
to:
                                      (__bridge void *)(self)),

Removed line 151:
		[noInputAlert release];



main.m (not shown in book since it is created for you by Xcode template):
Removed line 13:
    NSAutoreleasePool *pool = [[NSAutoreleasePool alloc] init];
Removed line 15:
    [pool release];
