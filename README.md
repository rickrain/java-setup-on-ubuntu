# Setup a Java development environment on Ubuntu
The guidance below is an _opinionated_ (my opinion) set of steps to setup and configure a simple Java development environment on [Ubuntu Desktop](https://ubuntu.com/download/desktop).  The guidance includes

- installing the Java Development Kit (JDK) and Java Runtime Environment (JRE), and
- configuring Visual Studio Code Java extensions

> This has been tested and verified on Ubuntu 20.04 (LTS) running on physical hardware.  However, it should work the same on a virtual machine.

## Pre-requisites
The following are required to leverage and use this content:
- Ubuntu Desktop, v20.04 (LTS)
- Visual Studio Code, v1.57.1 (or later)

## Install JDK and JRE
Since I use VS Code as my IDE, I tend to default to the [VS Code supported languages documentation](https://code.visualstudio.com/docs/languages/overview) to learn what I need to support development in a particular language.  As expected, I found the [Java in Visual Studio Code](https://code.visualstudio.com/docs/languages/java) page with guidance to get started.  Unexpectedly, I learned that the _Coding Pack for Java_ that bundles together everything you need is only available for Windows and macOS.  Meaning, I'm on my own to install a JDK, JRE, and VS Code Java extensions. :confused:

With all the Java distributions available, it's not an obvious choice on which one to go with.  My exploration led me to finally go with [Microsoft's Build of OpenJDK](https://www.microsoft.com/openjdk).  This build is supported on macOS, Windows, and Linux.  However, what really got my attention was the "General Availability" note indicating the binaries are ready for "production", as explained in [this blog post](https://devblogs.microsoft.com/java/announcing-general-availability-of-microsoft-build-of-openjdk/).  Satisfied with my findings, I proceeded to install **OpenJDK 11** using the native installer for Ubuntu 18.04 (and newer) following [these steps](https://docs.microsoft.com/en-us/java/openjdk/install#install-on-ubuntu-1804).

> Be sure to update the URL in the `wget` command to specify your Ubuntu version, "20.04" in my case.  You can see all the Ubuntu versions that packages exist for [here](https://packages.microsoft.com/config/ubuntu/). 


## Install and configure VS Code Java extensions
The Java extensions to install are just the extensionsions from the [Java Extension Pack](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack).  You may choose to install all or just a few.  At a minimum, I suggest installing the following extensions.

- [Language Support for Java (TM) by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.java), providing intellisense, code-completion, syntax highlighting, etc.

  > NOTE: Since I used the native installers above to install the JDK and JRE, I didn't have to mess with configuring the `JDK_HOME` and `JAVA_HOME` environment variables.

- [Debugger for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-debug), enabling you to run and/or debug your Java application.
- [Java Test Runner](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-test), providing unit testing support of your code.


## References
Some related references are listed below:
- Follow and/or contribute to [microsoft/openjdk](https://github.com/microsoft/openjdk) on GitHub.
- [Java on Azure tutorials](https://code.visualstudio.com/docs/java/java-on-azure).
