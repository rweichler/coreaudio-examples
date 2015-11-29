CH10_iOSBackgroundingTone

This example uses an Audio Queue to play a sine wave, which changes frequency based on whether the app is in the foreground or background.

Note that the AudioSession functions used in this example were deprecated after the book was published. AVAudioSession, in the AV Foundation framework, is intended as a drop-in replacement.

March 13, 2014: This example has been modernized for Xcode 5.1, and has been converted to ARC. The following lines are different from what's printed in the book:

CH10_iOSBackgroundingToneAppDelegate.m
Changed line 79 from:
	CH10_iOSBackgroundingToneAppDelegate *appDelegate = (CH10_iOSBackgroundingToneAppDelegate*)inUserData;
to:
	CH10_iOSBackgroundingToneAppDelegate *appDelegate = (__bridge CH10_iOSBackgroundingToneAppDelegate*)inUserData;

Changed lines 93-4 from:
	printf ("Interrupted! inInterruptionState=%u\n", inInterruptionState);
	CH10_iOSBackgroundingToneAppDelegate *appDelegate = (CH10_iOSBackgroundingToneAppDelegate*)inUserData;
to:
	printf ("Interrupted! inInterruptionState=%u\n", (unsigned int)inInterruptionState);
	CH10_iOSBackgroundingToneAppDelegate *appDelegate = (__bridge CH10_iOSBackgroundingToneAppDelegate*)inUserData;

Changed line 117 from:
                                      self),
to:
                                      (__bridge void *)(self)),

Changed line 140 from:
                                    self,
to:
                                    (__bridge void *)(self),

Changed line 151 from:
    NSLog (@"bufferSize is %u", bufferSize);
to:
    NSLog (@"bufferSize is %u", (unsigned int)bufferSize);

Removed lines 223-7:
- (void)dealloc
{
    [_window release];
    [super dealloc];
}



main.m (not shown in book since it is created for you by Xcode template):
Removed line 13:
    NSAutoreleasePool *pool = [[NSAutoreleasePool alloc] init];
Removed line 15:
    [pool release];
