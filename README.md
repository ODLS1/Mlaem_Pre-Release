## Mlaem Pre-Release

This repository contains a pre-release version of the MLAEM analytic element groundwater modeling software.

### Roadmap
The draft roadmap for the development of Mlaem can be found [here](Roadmap.md).

### Download
To download the software, click on the green "<> Code" button and select "Download ZIP". Move the ZIP file to the location where you want to run Mlaem, and then extract the files. When you run Mlaem for the first time on Windows, you may get a warning that "Windows protected your PC". Click on the tiny "More info" link on the left side of the window containing the message and then click "Run anyway". On MacOS, you may get a warning about a missing developer signature or malware -- see the instructions for your Mac processor type below.

The Mlaem executable has been built entirely from source code using minimal library dependencies (all trusted, all source code) and should pose minimal risk. The Mlaem team will work with Microsoft and Apple to properly certify Mlaem as trusted software in the future.

### Installation
Follow the steps for your operating system (Windows, MacOS, or Linux). 

#### Windows
Double-click on the file `Mlaem_Win11.exe" in the File Manager in the location where you put the extracted ZIP files from GitHub (the Win11 executable should run on both Windows 10 and Windows 11).

#### MacOS
Determine your Mac processor by clicking on the Apple logo on the upper-left of your screen and selecting "About this Mac" and follow the additional instructions for your processor type below.

The preferred method to run Mlaem is to open the Terminal app, navigate to the folder where you put the extracted ZIP files from GitHub, and typing `./Mlaem_MacOS_Apple` (or `./Mlaem_MacOS_Intel`, depending on your processor type) to start Mlaem. Navigating the folder (or directory) structure in the Terminal requires a few commands: `cd [folder name]` to go up the folder "tree", `cd ..` to go back down the folder tree, and `ls` to list the contents of a folder.

##### MacOS Apple M-Series Processor (e.g., Apple M1, M1 Pro, M2, etc.)
To ignore the warning about running a file that may have Malware, go to `Settings`, `Privacy & Security` and scroll to the bottom. You should see `"Mlaem_MacOS_Apple" was blocked to protect your Mac.` Click `Open Anyway` and then `Open Anyway` again when the `Open "Mlaem_MacOS_Apple"?` window appears and use your fingerprint or password to allow the app to run. When Mlaem finally starts, allow it to access files.

##### MacOS Intel Processor (e.g., 2.7 GHz Intel Core i5, etc.)
To ignore the "developer signature" warning, control-click on the `Mlaem_MacOS_Intel` file from a Finder window and choose `Open` from the shortcut menu.

##### MacOS Issues
1) Mlaem will occassionally fail to start up on both Mac platforms. You can ignore the error message and then try to start Mlaem again.
2) If you get the message "permission denied" when trying to run Mlaem, then it is possible that the permissions on the Mlaem executable were accidentally changed (for example, by copying the executable from one location to another). Fix this from the Terminal by navigating to the directory where the execuatble is located and typing `chmod +x Mlaem_MacOS_Apple` (or `chmod +x Mlaem_MacOS_Intel`, depending on your chip type).
3) Mlaem may not run successfully by double-clicking on the app. This issue can be resolved by running Mlaem for the first time from the Terminal app, as described above. Once the app has been started once, double-clicking on it should work in the future. However, double-clicking will set your "Home" folder as the startup location for Mlaem, so you will need to either navigate to the location where you want to store your Mlaem files when opening files from within Mlaem, or store your Mlaem files in your Home folder.

#### Linux
There are two "flavors" of Linux executables available. One is designed to run with XWindows protocol (which uses OpenGL GLX), and one with Wayland (which uses OpenGL EGL). You can determine which one you are usig by opening a Linux terminal typing the following command:

    echo $XDG_SESSION_TYPE

Next, navigate to the directory where you unzipped the Mlaem ZIP file downloaded from GitHub. Type `./Mlaem_Linux_EGL_x86_64` to start Mlaem on Wayland, or type `./Mlaem_Linux_GLX_x86_64` to start Mlaem on XWindows. On Linux, as on windows, you should be able to run Mlaem by double-clicking the executable name in the Linux file manager.

### Getting Started
Mlaem has a few principles that govern the way it operates.
1) Models are entered in "Input Mode", which defaults to the gray screen (or bright basemap) and has a large number of tools available.
2) Elements are entered using the various tools in the tookit.
    * Select a tool
    * Choose default options in the dialog that pops up when the tool is selected
    * Enter elements by clicking on the screen
3) The primary documentation for the program is currently through the extensive "tool tips" that are available by hovering over tools and buttons.
4) Click the "Solve" button to generate a solution for the model you created.
    * The screen will switch to "Results Mode", which defaults to a black screen (or darkened basemap)
    * Use the tools in Results Mode to inspect the results or to create pathline traces
5) Save results by choosing `Project->Save` (which will save your model to an input file that can be read later) and/or by selecting `Project->Save Image of Plot` (which will save a `.png` image of your results without the various dialogs and windows).

#### User Tutorial
The old (circa 1998) [user tutorial](Tutorial.pdf) is available to help users get started with Mlaem. However, please note that it is out-of-date and has not been updated for the modern graphical user interface (GUI).

### Reporting Issues
Due to its pre-release nature, users are likely to encounter issues when using the software and are encouraged to report them following the steps below.

1) Open the `settings.json` file, which should be located in the same directory as the executable.
2) Removed the "comment" `--` by changing the line `"--record events file": "issue_events.txt",` to `"record events file": "issue_events.txt",`.
3) Start Mlaem and follow the sequence of steps that demonstrate the issue. Once the issue has been demonstrated, select `Project` -> `Stop Recording Events`. If your issue results in a fault or "crash", then in most cases the event recorder should successfully have written out the events file (although this is not guaranteed).
4) Change the line: `"record events file": "issue_events.txt",` to `"play events file": "issue_events.txt",`.
5) Start Mlaem again and do not touch the keyboard or mouse. Mlaem should play the events from the events file you recorded and duplicate the issue.
6) When you have confirmed duplication of the issue with the events file, create a new Issue on the GitHub `Mlaem_Pre-Release` site:
    - [ ] Click on the `Issues` tab on the upper-left and then on the green `New issue` button
    - [ ] Describe the problem you encounted
    - [ ] Provide the name of the executable you used (e.g. `Mlaem_Win11.exe`)
    - [ ] Attach the `issue_events.txt` file you created to the new issue
    - [ ] Click the green `Submit new issue` button to create the issue.

Mlaem developers will be automatically notified by GitHub and will tag and prioritize the issue (and will try to resolve high-priority issues quickly).

### Making Feature Requests
Please make feature requests by following step 6) in the issue creation process described above (but skip the "events file" step).

### Thank You
Thank you for taking the time to submit issues and feature requests for the pre-release vesion of Mlaem!

#### ------------------------------- Release Notes -------------------------------

##### Version 6.A8 (Alpha 8, April 27, 2025)
* Combined the `Aquifer` and `Measured Head` tabs in `Grid Dialog`.
* Changed `fistar` to `F-Head` in Grid Dialog for consistency with console.
* Remove the current input tool when the Console is focused.
* Check for duplicate measured head (`MHEAD`) points.
* Show the Layer Info Dialog by default.
* Allow grid of `MHEAD` and `ATARD` `LRES`, `RRES`, and `FHEAD` without solution.
* Fixed bug: aquifer inhomogeneities not created directly after "OK" in dialog.

##### Version 6.A7 (Alpha 7, April 13, 2025)
* Fixed bug: handle press/release of button/key if panning with `ctrl+left mouse`.
* Fixed formatting for numbers in dialogs to show exponents when needed.
* Added `"limit entry to one object at a time"` option in `settings.json`.
* Apply darker dimming when a modal dialog is active.
* Emit "beep" sound after click outside modal dialog, show message afer 2 clicks.
* Always limit entry to one Global Aquifer or Reference Point at a time.
* Added abilty to right-click to hilight any object with any or no tool selected.
* Changed behavior: do not write out aquifer or reference point if not set.
* Improved error handling
    - Always show a system dialog with error information when Mlaem aborts.
    - Always write out the current model when Mlaem aborts.
* Improved default values in many dialogs.
* Made entering and editing discontinuous curvilinear strings the defalt.
* Fixed bug: Mlaem not aware when global aquifer changed.
* Can automatically log errors and event files (set option in `settings.json`).
* Fixed `SAVE`, `READ`, `SSAVE`, and `SREAD` commands in `TRACE`.
* Enabled traces to persist after leaving Results Mode and then returning.
* Fixed crash when using the `RF` move tool when no `RF` point had been enetered.
* Improved behavior of Results Mode tools and coupling with console.
* Added hot keys for Solve, Grid, and Plot dialogs.
* Fixed window maximization issue when playing events.
* Created tool to optimize tests.
* Bug fix: ability to select grid type from console (and input files).

##### Version 6.A6 (Alpha 6, November 7, 2024)
* Fixed issue in "Flow Net" option after adding or changing an element.
* Improved default contours for flow net to always plot the 0 value for Psi.

##### Version 6.A5 (Alpha 5, November 4, 2024)
* Enhanced Plot Dialog to allow customization of flow net plots.
* Added "Flow Net" option to Grid dialog (and moved around grid items to the various tabs).
* Changed transient wells (<TWELL> command in the WELL module) to use the Specific Storage Coefficient instead of the Specific Yield Coefficient, updated HELP.

##### Version 6.A4 (Alpha 4, October 28, 2024)
* Substantially increased the speed of the solve and the grid.
* Added an "Information" window with current coordinates and aquifer properties. This window automatically appears in Results Mode and can be toggled with the `F4` key (auto-toggle when moving to Results Mode can be turned off in the `Settings` menu).
* Added a tool to generate pathline traces that are captured by a well (this is called the "WG Tool" for Well-Generate).
* Added a "View Results Tool" to view various computed results for the model at a selected point (which can be edited).
* Added ability to choose to trace from the base of the aquifer, from the saturated top of the aquifer, or from an elevation (both for Trace and WGen tools)
* Added information messages when trying to use the Inspect Tool on elements/places where it will not generate information.
* Made the Command Console smaller.

##### Version 6.A3 (Alpha 3, October 11, 2024)
* Fixed bug in opening invalid files that could result in overwriting a file (added a test to protect against future issues).
* Added capabilty to save an image of the plot by itself (without windows on top of the plot) in `Project`->`Save Image of Plot`.
* Fixed event playback issues on Windows and MacOS.

##### Version 6.A2 (Alpha 2, October 10, 2024)
* Fixed inability to switch grid type from the Grid Dialog.
* Fixed crash when clicking on multiple tools or layers in succession.
* Added ability to set a title for the plot (available through the menu in `View` -> `Set Plot Title`).

##### Version 6.A1 (Alpha 1, October 8, 2024)
* Fixed crash and issues with TRACE module. Mlaem should now always be in TRACE when the Results tools are used.
* Created a setting under the `Settings` -> `Wells` menu that can be selected to only allow entry of one well at a time.
    - If desired, you can paste the line `"limit entry to one well at a time": true,` into the "settings.json" file in the directory where Mlaem is located.
* The Edit tool ("E") can now highlight elements with the right mouse button.
* Elements are now drawn over the plot contours, not vice-versa.
* When right-clicking with the Trace tool, it will repeat the last command (as opposed to performing another trace).

##### Version 6.A0 (Alpha 0, September 30, 2024)
* Initial pre-release of Mlaem on Windows, MacOS-Apple, MacOS-Intel, and Linux.

##### Earlier Changes
* Added auto-save and auto-load of plots and grids for layers and types
* Changed the way the reference point works
