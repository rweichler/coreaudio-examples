these have been adapted to better suit my workflow.

i.e.:

* i have deleted all of the xcode project files.
* the style isnt ridiculously ugly.
* replace tabs with 4 spaces


you will have to hand compile them yourself from the command line.

typically, something like:

```bash
clang main.c -framework Foundation -framework AudioToolbox
```

will work.
