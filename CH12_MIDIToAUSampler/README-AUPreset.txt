The AUPreset files used by this example need to live in specific locations, as described in chapter 12. You can and should use AU Lab to create these files with your own audio.

In the interest of reproducibility, I'm including my own preset files with this version of the download code. To use these, you would need to do the following:

1. Put chris-coreaudio-c2.caf in ~/Library/Audio/Sounds/
2. Put ch12-aupreset.aupreset in ~/Library/Audio/Presets/Apple/AU Sampler/
3. The .aupreset is a property list file, so you can edit it in Xcode, Property List Editor, or any text editor. Edit the <file-references> section so that it has the correct path to chris-coreaudio-c2.caf (which you moved into your ~/Library/Audio/Sounds folder in step 1).
4. Change line 128 of main.c to provide the full path to your .aupreset file (which you moved in step 2).

