# Preparing Windows environment

This document provides the steps to install the software required to begin the exercises on a Windows machine.  The instructions were written for a Windows 7 Professional machine.  Exceptions have been noted for Windows 8 and Windows 10. The sequence is as follows:

1.	Install Java JDK 1.9
2.	Edit the JAVA_HOME variable and edit the system PATH
3.	Install GIT
4.	Install cURL
5.	Install node.js
6.	Install API Connect
7.	Install Docker
8.	Install cloudfoundry CLI
9.	Install the IBM Container plugin for cloudfoundry

**Important:** You will need an IBM Bluemix account and a github account to complete the exercises that follow these setup instructions.

## Part 1: Install Java JDK 1.8

1.	In a browser, open https://www.oracle.com
2.	In the list of menu options, hover over Downloads.
3.	Under Popular Downloads, click Java for Developers.
4.	Click the download button for Java Platform (JDK) 8u111 (Note: your minor version may be different)
5.	In the section entitled Java SE Development Kit 8u111, click Accept License Agreement.
6.	Select the .exe file for Windows x64 (jdk-8u111-windows-x64.exe).  The file is downloaded to the machine’s Download directory.
7.	 Run the Windows executable.  Navigate to the Download directory. Double click jdk-8u111-windows-x64.exe
8.	At the Welcome screen, click Next.
9.	Accept the features to install.  Accept the default install location C:\Program Files\Java\jdk1.8.0_111\.  Click Next.
10.	Upon successful installation, click Close.
11.	Verify that the installation was successful.  Open a command prompt.  Change directories to C:\Program Files\Java\jdk1.8.0_111\. You should see 6 directories, 6 files, and 2 zip files.

## Part 2:  Edit the system PATH.  

Add JAVA_HOME to the Path by editing an environment variable.

1.	Add or modify the JAVA_HOME environment variable to C:\Program Files\Java\jdk1.8.0_111
2.	Add JAVA_HOME to the end of the Path system variable.
3.	Close the Environment Variables window.
4.	Restart the computer.
5.	Verify that your installation of Java is recognized. Open a command prompt and type:
java –version
6.	You should see information about the Java version, Java runtime, and Java HotSpot.

## Part 3:  Install GIT
1.	Download GIT for Windows from [https://git-scm.com/download/win](https://git-scm.com/download/win)
2.	Run the executable named Git-2.1.1.0-64-bit.exe
3.	Read the GNU General Public License and click Next.
4.	Accept the installation location.  Click Next.
5.	Accept the default components for installation.  Click Next.
6.	Create a shortcut.  Click Next.
7.	Adjust the PATH environment by selecting the option labeled Use Git from the Windows Command Prompt.  Click Next.
8.	Configure the line ending conversions by selecting Checkout Windows-style, commit Unix-style line endings. Click Next.
9.	Select Use MinTTY as the terminal emulator with Git Bash.  Click Next.
10.	Keep the default extra options Enable file system caching and Enable Git Credential Manager.  Click Next.
11.	Do not select any experimental options.  Click Install.
12.	Click Finish.
13.	Open a command prompt and change to C:\Program Files\Git\bin.  Type git –version
14.	You should see the response git version 2.11.windows.1

## Part 4:  Install cURL
1.	Create a folder named:  C:\curl
2.	Go to [http://curl.haxx.se/download.html](http://curl.haxx.se/download.html) and download the following the zip file for the Win64 version of cURL:
Scroll to the Win64-Generic section.  Locate the latest Win64 ia64 zip version with SSL support. Click the version number to start the download.
3.	Save the zip file
4.	Unzip the downloaded zip file.  Move curl.exe to C:\curl
5.	Go to [http://curl.haxx.se/docs/caextract.html](http://curl.haxx.se/docs/caextract.html)  and download the digital certificate file named cacert.pem.
6.	Move cacert.pem to C:\curl.  Rename the file curl-ca-bundle.crt.
7.	Add C:\curl to the Windows PATH environment variable so the curl command is available from any location at the command prompt.
8.	Verify the installation is complete. Open a command prompt and enter curl [https://www.google.com](https://www.google.com). The request returns the html in the command window.

## Part  5:  Install node.js
1.	Go to [https://nodejs.org/en/](https://nodejs.org/en/)
2.	There are two versions listed. Download the recommend version.
3.	Start the Windows installer package for node-v6.9.2-x64.msi.  Click Run.
4.	At the Welcome window, click Next.
5.	Accept the end-user license agreement. Click Next.
6.	Accept the destination folder.  Click Next.
7.	Accept any custom setup options. Click Next.
8.	Click Install.
9.	Click Finish when notified the installation was successful.
10.	Verify the installation.  At a command prompt, enter npm version
11.	You should see a JSON object like the following:

![](images/JSON.png)

## Part  6:  Install API Connect

Use npm to install API Connect.
1.	Open a command prompt. Type npm install -g apiconnect.  This installation takes several minutes to complete.  You can ignore any warnings about deprecated packages.

## Part  7:  Install Docker

### For Windows 10
Install Docker for Windows.  Follow [https://docs.docker.com/docker-for-windows](https://docs.docker.com/docker-for-windows) for specific directions.

If you have 64 bit Windows 7 or higher, follow these directions to install Docker with Toolbox.

1.	You must have virtualization enabled on your machine.  This is not an issue if you are running Windows 10.  However, if you are running Windows 7 or Windows 8, you must read and follow one set of these directions.

	### Windows 8 or 8.1
	Choose Start > Task Manager.  Navigate to the Performance tab.  Under CPU, you should see Virtualization: Enabled.
	If virtualization is not enabled, then follow the manufacturers documentation.  The steps to configure BIOS settings are specific to the hardware you have. It varies from one hardware manufacturer to another, and, even different models from the same manufacturer can have different steps.  Refer to the documentation or website for your hardware make and model.  Or, you can check on the Intel website for guidance from Intel about their VT-x product technology.
	### Windows 7
	You should check your system’s BIOS to see if hardware virtualization is enabled. If it is not enabled, enable it through the BIOS.
	You must run the Microsoft Hardware-Assisted Virtualization Detection Tool which can be found at `https://www.microsoft.com/en-us/download/details.aspx?id=592`

	a.	Download the MHAVDT.  Be sure to select havdetectiontool.exe and the user guide.
	b.	Run the detection tool by clicking havdetectiontool.exe
	c.	Accept the license agreement.  Click Next.
	d.	You should see a message This computer is configured with hardware-assisted virtualization.
	e.	Select No, I don’t want to send data.  Click OK.
2.	Follow [https://docs.docker.com/engine/installation/windows/](https://docs.docker.com/engine/installation/windows/) and scroll down to the Docker Toolbox section.
3.	Click the link for Docker Toolbox  https://www.docker.com/products/docker-toolbox
4.	Click Download (be sure to click the Windows option, not the Apple option)
5.	Scroll down and find the Downloads section.  Click the latest DockerToolbox-1.12.3.exe version.
6.	Open the exe and save the file
7.	Run the DockerToolbox-1.12.3.exe
8.	At the Welcome screen, click Next. You can clear the checkbox to help improve Docker Toolbox.
9.	Accept the default destination folder.  Click Next.
10.	Accept the list of components.  Click Next.
11.	Accept the additional tasks (shortcut, add docker binaries to PATH, and upgrade Boot2Docker VM).  Click Next.
12.	Review settings and click Install.
13.	Clear the checkbox to view shortcuts.  Click Finish.
14.	Verify your docker installation.
	a.	From the Start Menu, navigate to All Programs >  Docker.
	b.	Click Docker Quickstart Terminal
	c.	There a number preliminary steps and downloads that must happen. Wait for a message indicating the interactive shell can start and the $ prompt is available.
	d.	Type docker run hello-world.
	e.	You should see a response starting Hello from Docker!
## Part  8: Install cloudfoundry CLI
1.	Open a browser to [https://github.com/cloudfoundry/cli/releases](https://github.com/cloudfoundry/cli/releases)
2.	Click the link for Windows 64 bit
3.	Select the option to save the installer file cf-cli-installer_6.22.2_winx64.zip.  Click OK.
4.	Extract the installer zip file.
5.	Click cf_installer.exe to begin the installation.
6.	Select Only for me as the installation option. Click Next.
7.	Accept the default destination location.  Click Next.
8.	Verify settings and click Install.
9.	Click Finish.
10.	Verify installation.  Open a command prompt.  Enter cf -v   You should see the version number of the CLI.
## Part  9:  Install the IBM Container plugin for cloudfoundry
1.	Use cloudfoundry to install the container plugin
cf install-plugin https://static-ice.ng.bluemix.net/ibm-containers-windows_x64.exe
2.	Type y when asked to install the plugin.
3.	Type y if warned about binaries.
4.	You should receive a message that Plugin IBM-Containers v0.8.964 successfully installed.
This completes the setup of your computer.
