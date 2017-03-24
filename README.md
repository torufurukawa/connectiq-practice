connectiq launches the Connect IQ simulator, which can be used to run and test apps on your computer before running them on your device. In the simulator, your app will only have access to those APIs that are available on the currently simulated device. For example, an API only available in Connect IQ v2.2.x or higher, such as PersistedContent, will not be available on devices that run earlier versions of Connect IQ.

monkeyc calls the Monkey C compiler. The compiler can take code from multiple files and link them together into a single Connect IQ executable (a PRG file). The optional -z argument allows resource files to be passed in. If your project uses multiple resource files separate them with the system path separator (‘;’ in Windows and ‘:’ in OSX). This allows the addition of bitmaps, drawables, fonts, strings, and menus to your executable. See the samples directory for a sample resource file. The usage is:

> monkeyc -o <output.prg> -m <manifest.xml> [-z resource.xml;resource2.xml] <file1.mc> [file2.mc]...
monkeydo runs a Connect IQ executable in the simulator. You must have previously started the simulator with connectiq. The usage is:
> monkeydo myApp.prg
Here is an example of a basic build and run cycle from the command line:

> connectiq
> monkeyc -o myApp.prg -m manifest.xml myApp.mc
> monkeydo myApp.prg