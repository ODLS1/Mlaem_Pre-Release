## Mlaem Pre-Release

This repository contains a pre-release version of the MLAEM analytic element groundwater modeling software.

### Roadmap
The draft roadmap for the development of Mlaem can be found [here](Roadmap.md).

### Download
To download the software, click on the green "<> Code" button and select "Download ZIP". Open the zip file from your file manager, extract the files, and move them to the location where you want to run Mlaem. On Windows, you may get a warning that "Windows protected your PC". Click on the tiny "More info" link on the left side of the window containing the message and then click "Run anyway". On MacOS, you may get a warning about the developer signature -- see the instructions below.

The Mlaem executable has been built entirely from source code using minimal library dependencies (all trusted, all source code) and should pose minimal risk. The Mlaem team will work with Microsoft and Apple to properly certify Mlaem as trusted software in the future.

### Installation
Follow the steps for your operating system (Windows, MacOS, or Linux). 

#### Windows
Double-click on the file `Mlaem_Win11_240930.exe" in the File Manager in the location where you put the extracted ZIP files from GitHub (the Win11 executable should run on both Windows 10 and Windows 11).

#### MacOS
Determine your Mac processor by clicking on the Apple logo on the upper-left of your screen and selecting "About this Mac" and follow the instructions for your processor type below.

##### MacOS Apple M-Series Processor (e.g., Apple M1, M1 Pro, M2, etc.)
Double-click on the file `Mlaem_MacOS_Apple.app` in a Finder window in the folder where you put the extracted ZIP files from GitHub. To ignore the warning about running a file that may have Malware, go to `Settings`, `Privacy & Security` and scroll to the bottom. You should see `"Mlaem_MacOS_Apple" was blocked to protect your Mac.` Click `Open Anyway` and then `Open Anyway` again when the `Open "Mlaem_MacOS_Apple"?` window appears and use your fingerprint or password to allow the app to run. When Mlaem finally starts, allow it to access files. The app will likely quit unexpectedly the first time it runs (this may be due to the security interruptions during startup) -- ignore the message and double-click the app to finally start Mlaem.

##### MacOS Intel Processor (e.g., 2.7 GHz Intel Core i5, etc.)
Double-click on the file `Mlaem_MacOS_Intel.app` in a Finder window in the folder where you put the extracted ZIP files from GitHub. To ignore the "developer signature" warning, control-click on the `Mlaem_MacOS_Intel.app` file and choose Open from the shortcut menu.

##### MacOS Issues
On some Macs, Mlaem may not run successfully by double-clicking on the app. This issue can be resolved by opening a terminal window, navigating to the folder where the app is located, typing `cd Mlaem_MacOS_Apple.app` (or `cd Mlaem_MacOS_Intel.app`) and then direclty running the executable by typing `./Mlaem_MacOS_Apple_240930` (or `./Mlaem_MacOS_Intel_240930`). Once the app has been started once, double-clicking on it should work in the future.

#### Linux
Open a Linux Terminal and install the `glew` package (for managing the hardware interface to OpenGL). On Ubuntu Linux, the command is `sudo apt install libglew`. Next, navigate to the directory where you unzipped the Mlaem ZIP file downloaded from GitHub. Type `./Mlaem_Linux_240930`. Alternatively, you may be able to run Mlaem by double-clicking the executable name in the Linux file manager.

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
    - [ ] Provide the name of the executable you used (e.g. `Mlaem_Win11_240930.exe`)
    - [ ] Attach the `issue_events.txt` file you created to the new issue
    - [ ] Click the green `Submit new issue` button to create the issue.

Mlaem developers will be automatically notified by GitHub and will tag and prioritize the issue (and will try to resolve high-priority issues quickly).

### Making Feature Requests
Please make feature requests by following step 6) in the issue creation process described above (but skip the "events file" step).

### Thank You
Thank you for taking the time to submit issues and feature requests for the pre-release vesion of Mlaem!
