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
To ignore the warning about running a file that may have Malware, go to `Settings`, `Privacy & Security` and scroll to the bottom. You should see `"Mlaem_MacOS_Apple" was blocked to protect your Mac.` Click `Open Anyway` and then `Open Anyway` again when the `Open "Mlaem_MacOS_Apple"?` window appears and use your fingerprint or password to allow the app to run. When Mlaem finally starts, allow it to access files. Mlaem may quit unexpectedly the first time it runs (this may be due to the security interruptions during startup). If that happens, ignore the message and start Mlaem again.

##### MacOS Intel Processor (e.g., 2.7 GHz Intel Core i5, etc.)
To ignore the "developer signature" warning, control-click on the `Mlaem_MacOS_Intel` file from a Finder window and choose `Open` from the shortcut menu.

##### MacOS Issues
1) If you get the message "permission denied" when trying to run Mlaem, then it is possible that the permissions on the Mlaem executable were accidentally changed (for example, by copying the executable from one location to another). Fix this from the Terminal by navigating to the directory where the execuatble is located and typing `chmod +x Mlaem_MacOS_Apple` (or `chmod +x Mlaem_MacOS_Intel`, depending on your chip type).
2) Mlaem may not run successfully by double-clicking on the app. This issue can be resolved by running Mlaem for the first time from the Terminal app, as described above. Once the app has been started once, double-clicking on it should work in the future. However, double-clicking will set your "Home" folder as the startup location for Mlaem, so you will need to either navigate to the location where you want to store your Mlaem files when opening files from within Mlaem, or store your Mlaem files in your Home folder.

#### Linux
Open a Linux Terminal and install the `glew` package (for managing the hardware interface to OpenGL). For example, on Ubuntu Linux use the command `sudo apt install libglew`. Next, navigate to the directory where you unzipped the Mlaem ZIP file downloaded from GitHub. Type `./Mlaem_Linux_x86_64` to start Mlaem. Alternatively, you may be able to run Mlaem by double-clicking the executable name in the Linux file manager.

### User Tutorial
The old (circa 1998) [user tutorial](Tutorial.pdf) is available to help users get started with Mlaem. However, please note that it is out-of-date and has not been updated for the modern GUI, which is still under development.

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

#### ---------------------------------- Release Notes ----------------------------------

##### Version 6.A3 (Alpha 3, October 11, 2024)
* Fixed bug in opening invalid files that could result in overwriting a file (added a test to protect against future issues).
* Added capabilty to save an image of the plot by itself (without windows on top of the plot) in `Project`->`Save Image of Plot`
* Fixed event playback issues on Windows and MacOSApple.

##### Version 6.A2 (Alpha 2, October 10, 2024)
* Fixed inability to switch grid type from the Grid Dialog
* Fixed crash when clicking on multiple tools or layers in succession
* Added ability to set a title for the plot (available through the menu in `View` -> `Set Plot Title`)

##### Version 6.A1 (Alpha 1, October 8, 2024)
* Fixed crash and issues with trace module. Mlaem should now always be in Trace when the Results tools are used.
* Created a setting under the `Settings` -> `Wells` menu that can be selected to only allow entry of one well at a time
    - If desired, you can paste the line `"limit entry to one well at a time": true,` into the "settings.json" file in the directory where Mlaem is located.
* The Edit tool ("E") can now highlight elements with the right mouse button
* Elements are now drawn over the plot contours, not vice-versa
* When right-clicking with the Trace tool, it will repeat the last command (as opposed to performing another trace)

##### Version 6.A0 (Alpha 0, September 30, 2024)
* Initial pre-release of Mlaem on Windows, MacOS-Apple, MacOS-Intel, and Linux

