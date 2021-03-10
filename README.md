# agikit template

Converted from Peter Kelly's AGI Contest 2 Template version 1.11

This is an agikit-compatible version of the AGI Contest 2 Template.  It serves a few purposes:

* Demonstrate how to lay out a project for agikit
* Serve as a starting point for game development with agikit
* Provide an easy way to test agikit itself

## Getting started

To get started with this template, download the code (either from the Github "Code" button up top, or by checking out the source code using git).

Then, in Visual Studio Code, install the "agikit" extension.  Once that's installed, open the project folder in Visual Studio Code.  You should be able to open the files in `src/logic` and see syntax highlighting, hover over variables, etc.

To build and run the game, press `Ctrl`-`Shift`-`P` (or `Command`-`Shift`-`P` on a Mac) and search for "AGI".  You should see an option for "Run AGI game with ScummVM".  Assuming you've installed ScummVM in a standard location, this should hopefully just work; if it doesn't, you might need to go into your Visual Studio Code preferences and configure the ScummVM path.

## File and directory layout

agikit doesn't follow the file and directory layout from AGI Studio.  Here are the specific changes
from the AGI Studio layout:

* Built game files are in a subdirectory called `build` rather than the root directory of the
  project.  This makes it easier to add the build artifacts to a `.gitignore` or similar file to
  avoid checking them into version control.
* The `src` directory has several subdirectories: `logic`, `pic`, `sound`, and `view`.  This is
  where the source files of each type live.  The subdirectories are there to hopefully make the
  project easier to navigate in a text editor.
* Also in the `src` directory are `object.json` and `words.txt`.  These are used to build the
  `OBJECT` and `WORDS.TOK` in your built game.
* Source files inside the `src` directory use file extensions to tell agikit (and your OS, and your
  text editor) what file type they are.  Specifically, `.agilogic`, `.agisound`, `.agiview`, and
  `.agipic` extensions are used.  This makes it easier for text editors to select the right syntax
  highlighting and activate the right editor features when opening AGI source files.
  * PIC, VIEW, and SOUND source files are actually just binary files on disk.  They're exactly the
    data from the compiled volume (but not compressed, and without their resource headers).
    Right now, agikit doesn't support editing these directly, but I hope to add that in the future.
* The filename before the extension should be exactly the resource number - for example, LOGIC 0
  should have the filename `0.agilogic`.  Other files used in `#include` directives can have
  whatever name you want.
