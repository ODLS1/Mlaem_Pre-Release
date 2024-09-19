## Mlaem Pre-Release

This repository contains a pre-release version of the MLAEM analytic element groundwater modeling software.

### Roadmap
The draft roadmap for the development of Mlaem can be found [here](Roadmap.md).

### Download
To download the software, click on the green "<> Code" button and select "Download ZIP". Open the zip file from your file manager, extract the files, and move them to the location where you want to run Mlaem. On Windows, you may get a warning that "Windows protected your PC". Click on the tiny "More info" link on the left side of the window containing the message and then click "Run anyway". The Mlaem executable has been built entirely from source code using minimal library dependencies (all trusted, all source code) and should pose minimal risk. The Mlaem team will work with Microsoft to properly "certify" Mlaem as "safe" for Windows and will attempt to do the same for MacOS (for MacOS, follow instructions on the web for how to work around this issue).

### Installation
Follow the steps for your operating system (Windows, MacOS, or Linux).

#### Windows
Run the file `Mlaem_Win11_240914.exe" by double-clicking on the file in the FileManager.

#### MacOS
Check if you have `Homebrew` installed by opening a terminal window and typing `brew --help`. If you get a list of options, then Homebrew is installed. If not, follow the Homebrew installation instructions from the web <https://brew.sh/>.

When Homebrew has been successfully installed, install the `SDL2` library (which may take 30 minutes on older Macs):

    brew install SDL2

Next, check the type of Mac that you have by clicking on the Apple logo on the upper-left of the screen and selecting "About this Mac".

If the chip type is an Apple M-series (Apple M1, M2, etc.) then run the `Mlaem_MacOS_14-6_M2_240918` file from the directory where you installed Mlaem, and the program should start (after working around the missing "developer signature" issue mentioned above).

If the chip type is an Intel series, then you will need to install the compilers that were used to create Mlaem. Issue the following command:

    brew install gcc@9

This may take a full hour on older Macs.

After the compiler has been installed, run the `Mlaem_MacOS_10-13_Intel_240915` file from the directory where you installed Mlaem, and the program should start (after working around the missing "developer signature" issue mentioned above).

#### Linux
Linux users will need to build Mlaem from source code. Please establish an account on GitHub and then submit an issue for this project (see the "Reporting Issues" section below and follow step 6, skipping the events file) to request access to the source code repository (the source code repository has detailed build instructions).

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
    - [ ] Provide the name of the executable you used (e.g. `Mlaem_Win11_240607.exe`)
    - [ ] Attach the `issue_events.txt` file you created to the new issue
    - [ ] Click the green `Submit new issue` button to create the issue.

Mlaem developers will be automatically notified by GitHub and will tag and prioritize the issue (and will try to resolve high-priority issues quickly).

### Making Feature Requests
Please make feature requests by following step 6) in the issue creation process described above (but skip the "events file" step).

### Thank You
Thank you for taking the time to submit issues and feature requests for the pre-release vesion of Mlaem!

