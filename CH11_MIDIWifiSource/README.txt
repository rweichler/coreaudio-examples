CH11_MIDIWifiSource

This example provides MIDI events over wifi that can run a MIDI app (such as CH11_MIDIToAUGraph) running on OS X, provided you connect the network source in /Applications/Utilities/Audio MIDI Setup, as described in the book.

March 13, 2014: This example has been modernized for Xcode 5.1, and has been converted to ARC. The following lines are different from what's printed in the book:


CH11_MIDIWifiSourceViewController.m
Removed lines 66-71:
- (void)dealloc
{
	[_window release];
	[_viewController release];
    [super dealloc];
}


CH11_MIDIWifiSourceViewController.xib:
The buttons' backgrounds have been explicitly colored to resemble white and black piano keys, since iOS 7 buttons are indistinguishable from labels.


main.m (not shown in book since it is created for you by Xcode template):
Removed line 13:
    NSAutoreleasePool *pool = [[NSAutoreleasePool alloc] init];
Removed line 15:
    [pool release];
