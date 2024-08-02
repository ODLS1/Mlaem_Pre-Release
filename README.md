## Mlaem Pre-Release

This repository contains a pre-release version of the MLAEM analytic element groundwater modeling software.

### Roadmap
The draft roadmap for the development of Mlaem can be found [here](Roadmap.md).

### Download
To download the software, choose one of two methods:
1) (Easiest) Click on the green `<> Code` button and select `Download ZIP`. Open the zip file from your file manager and run the desired executable.
2) (Smallest Download) Click on name of the desired files in the far left side of the file list (e.g. the `Mlaem_Win11_240716.exe` and `settings.json` files) and click on `Raw` (or the copy/download icons) to download them.

You may get one of two warning messages from Microsoft Windows.
1) If you downloaded the `ZIP` file, then you may get a warning that "Windows protected your PC". Click on `More info` and then click `Run anyway`.
2) If you directly download the executable, you may get the message "Make sure that you trust...". Select the `Show More` option followd by `Keep Anyway` to download the file.

The Mlaem executable has been built from "scratch" using minimal library dependencies (all trusted, and all source code) and should pose minimal risk. The Mlaem team will work with Microsoft to properly "certify" Mlaem as "safe" for Windows.

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
