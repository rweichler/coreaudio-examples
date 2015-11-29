CHANGES for "Learning Core Audio: A Hands-On Guide to Audio Programming for Mac and iOS" sample code

March 13, 2014

All projects:
-------------
With the release of Xcode 5.1 and iOS 7.1, we are updating all projects to use "Latest OS X" or "Latest iOS" as their target SDK, rather than risk breakage as newer versions of Xcode drop older versions of the OS X and iOS SDKs. We are also modernizing the project files to use LLVM and LLDB, the supported compiler and debugger as of Xcode 5.1.

Because it has been a source of confusion for some readers, we are also moving all Foundation-based examples to use Automatic Reference Counting (ARC). This means the downloadable code no longer matches the book, in that all uses of retain/release, autorelease pools, and explicit calls to dealloc been removed, and that toll-free bridging casts now take the appropriate __bridge modifier. But we've found that ARC is now sufficiently entrenched that some people don't recognize these pre-ARC memory management techniques.

There are no code changes other than those required to handle ARC or resolve new compiler warnings (most of which are just explicit casts).

Each project now has its own README.txt file describing the project. These files include the individual changes made as part of this update.

Individual examples:
--------------------

We've re-colored the piano keyboard buttons in the CH11_MIDIWifiSource .xib, since iOS 7 made them not look like buttons.

CH12_MIDIToAUSampler now includes the .aupreset file and source sound used when writing the book, though we still recommend building your own preset with AU Lab. This same preset has always been included with the CH12_MIDIToAUSamplerIOS example, since the iOS version needs to find the preset within its own app bundle, unlike OS X, which searches known filesystem paths.


+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

January 23, 2013

CH06_AudioConverter/
	main.c
--------------------
After line 205, added
	free (outputBuffer);
to release memory that was malloc()ed on line 163.	
(thanks Matt Daugherty)

CH07_AUGraphSpeechSynthesis/
	main.c
----------------------------
After line 196, added
	DisposeAUGraph(player.graph);
to release the AUGraph.
(thanks Seth Willits)

CH08_AUGraphInput/
	main.cpp
------------------
Changed line 58 from:
	if ((player->firstOutputSampleTime > 0.0) &&
to
	if ((player->firstOutputSampleTime > -1.0) &&

Changed line 104 from:
	if ((player->firstInputSampleTime > 0.0) &&
to
	if ((player->firstInputSampleTime > -1.0) &&
to properly check against the -1 flag value that is set on these counters before they're first used (see the -1 initializations on lines 481 and 320, respectively).
(thanks Ron Lee)

CH08_AUGraphInput/
	CH08_AUGraphInput.xcodeproj
-------------------------------
The project's references to the CARingBuffer.h and CARingBuffer.cpp files now uses an absolute reference to the /Library/Developer/CoreAudio/PublicUtility folder, which is their expected location as of Xcode 4.5 and up. Search Xcode documentation for "Core Audio Utility Classes", a pseudo sample code project, for the latest version of these classes. The Readme.rtf supplied with the classes indicates that this is their new expected path (replacing /Developer/Extras/CoreAudio/PublicUtility, where they were automatically installed prior to Xcode 4.3, and where the book describes them being).

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

August 29, 2012:

All projects:
-------------
Now that Xcode 4.4 has dropped support for OS X 10.6 as a base SDK, we have updated all the OS X project files to build for the OS X 10.7 SDK. The deployment target is still 10.6. iOS projects are still "Latest iOS", and work on iOS 5.1, the current public version as of this writing.

CH02_CAToneFileGenerator/
		main.m
-------------------------		
Changed line 106 from:
	NSLog (@"wrote %ld samples", sampleCount);
to
	NSLog (@"wrote %ld samples", sampleCount);
to match the bit-depth of the sampleCount argument
(thanks "jarryd")


CH07_AUGraphSineWave/
		main.c
----------------------
Changed line 96 from:
	input.inputProcRefCon = &player;
to
	input.inputProcRefCon = player;
to correct the pointer type of player, and eliminate a crash when the sleep() exits.
(thanks Stefan Frauenfelder and Dmitri Kharlamov)


CH10_iOSBackgroundingTone/
		CH10_iOSBackgroundingToneAppDelegate.m
-----------------------------------------------		
Changed line 63 from:
	(data)[frame] = (SInt16) (sin (2 * M_PI * (j / cycleLength)) * 0x8000);
to
	(data)[frame] = (SInt16) (sin (2 * M_PI * (j / cycleLength)) * SHRT_MAX);
to eliminate malformed waves at certain frequencies / sample rates.
(thanks Markus Boigner)


