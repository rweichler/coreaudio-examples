CH11_MIDIWifiSourceViewController

This example gets MIDI packets from a connected device (typically a MIDI keyboard connected via a MIDI-to-USB adapter with and then into the iOS device via the Camera Connection Kit) and sends MIDI note events to the AUSampler audio unit.

March 13, 2014: This example has been modernized for Xcode 5.1, and has been converted to ARC. The following lines are different from what's printed in the book:

AppDelegate.m:
Removed lines 35-39
- (void)dealloc
{
	[_window release];
    [super dealloc];
}

Changed line 89 from:
	printf("MIDI Notify, messageId=%d,", message->messageID);
to:
	printf("MIDI Notify, messageId=%d,", (int)message->messageID);

Changed line 226 from:
    self.window = [[[UIWindow alloc] initWithFrame:[[UIScreen mainScreen] bounds]] autorelease];
to:
    self.window = [[UIWindow alloc] initWithFrame:[[UIScreen mainScreen] bounds]];



main.m (not shown in book since it is created for you by Xcode template):
Removed line 13:
    NSAutoreleasePool *pool = [[NSAutoreleasePool alloc] init];
Removed line 15:
    [pool release];
