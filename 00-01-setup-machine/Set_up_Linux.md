## Set up a linux platform
This document provides the set up for a Linux machine. The sequence is as follows:  

  
1. Install Java JDK 1.8  
2. Edit the system PATH  
3. Install GIT  
4. Install cURL  
5. Install node.js  
6. Install API Connect Developer Toolkit  
7. Install docker  
8. Install cloudfoundry CLI  
9. Install the IBM Container plugin for cloudfoundry  

**Important:** You will need an IBM Bluemix account and a github account to complete the exercises that follow these setup instructions.

### Part 1: Install Java JDK 1.8 

The rest of the instructions apply to the image you have just created. Thus, 'In a browser...' means a browser on the image.

1. In a browser open [https://www.oracle.com]( https://www.oracle.com).  
2. In the list of menu options, hover over **Downloads** (if you cannot see it, reduce the zoom of the browser until it appears).  
3. Under Popular Downloads to the left, click **Java for Developers**.  
4. Click the download button for **Java Platform (JDK) 8u111** (Note: your minor version may be different).  
5. Under the section entitled Java SE Development Kit 8u111, click the button for **Accept License Agreement**.  
6. Select the **tgz** file for Linux 64-bit (jdk-8u111-linux-x64.tar.gz).  
7. **Save** the file.  

You now have the compressed file on your image. The next step is to move it to the correct location and unzip it.  

1. Create a directory for the file. In the Terminal, type the following:  
`sudo mkdir /usr/local/java`
2. Change to the download directory:  
`cd ~/Downloads`
3. You copy recursively (-r) the file in this directory to the location you want:  
`sudo cp -r jdk-8u111-linux-x64.tar.gz /usr/local/java`
4. Change to the new java directory:  
`cd /usr/local/java`
5. Verify that the tar.gz file was copied:  
`ls`
5. Unzip the file (if you want to see the list of unzipped files, replace _xf_ with _xvf_):  
`sudo tar xf jdk-8u111-linux-x64.tar.gz`
6. Verify that the extraction was successful:  
`cd jdk1.8.0_111`  
`ls`  
You should see 6 directories, 6 files, and 2 zip files.

### Part 2: Edit the system PATH
You add JAVA_HOME to the PATH by editing the profile file.  

1. Open the **profile** file in an editor:  
`sudo gedit /etc/profile`
2. **Add** these lines to the bottom of the file:  
`JAVA_HOME=/usr/local/java/jdk1.8.0_111`  
`PATH=$JAVA_HOME/bin:$PATH`  
`export JAVA_HOME`  
`export PATH`  
3. **Save** and **close** the profile file.  

The final step is to provide the information about the new PATH to the system. You do this with three update-alternative commands for Java, javac, and javaws:  

1. Update the java information (the final argument is the priority):  
`sudo update-alternatives --install "/usr/bin/java" "java" "/usr/local/java/jdk1.8.0_111/jre/bin/java" 1`
2. Update the compiler information:  
`sudo update-alternatives --install "/usr/bin/javac" "javac" "/usr/local/java/jdk1.8.0_111/bin/javac" 1`
3. Update the javaws information:  
`sudo update-alternatives --install "/usr/bin/javaws" "javaws" "/usr/local/java/jdk1.8.0_111/bin/javaws" 1`
4. Verify that your installation of Java is recognized. Type:  
`java -version`
5. You should see information about the java version, Java runtime, and Java HotSpot.

### Part 3: Install GIT

1. Run the following command (At the message _Do you want to continue_, type **Y**):  
`sudo apt-get install git`
2. When the installation is complete, verify that it was successful by typing  
`git –-version`
3. Verify that the response is _git version 2.7.4_ (your version number may be different).

### Part 4: Install cURL

1. Run the following command (At the message ‘Do you want to continue’, type **Y**):  
`sudo apt-get install curl`
2. When the installation is complete, verify that it was successful by typing  
`curl https://www.google.com`
3. Verify that the response is HTML for the Google home page.  
**NOTE**: If the response is _The document has moved_, then cURL was successfully installed, but the url is not correct. According to your geography, you need to change the extension. 

### Part 5: Install node.js
Ubuntu  includes Node.js in its default repositories.  The version that was used for this installation was _	4.2.6_. The exact version is not c  

1. Install it by typing the **apt install** command (At the message ‘Do you want to continue’, type **Y**):  
	`sudo apt install nodejs-legacy`
2. Verify the installation:  
`node -v`
3. The response is the version number (for example, v4.2.6).
4. Install the Node Package Manager (npm) (at the message ‘Do you want to continue’, type **Y**):  
`sudo apt install npm`
5. Verify the installation:  
`npm version`
6. You should see  JSON object similar to this:  
```
{ npm: '3.5.2',
  ares: '1.10.1-DEV',
  http_parser: '2.5.0',
  icu: '55.1',
  modules: '46',
  node: '4.2.6',
  openssl: '1.0.2g-fips',
  uv: '1.8.0',
  v8: '4.5.103.35',
  zlib: '1.2.8' }
```
### Part 6: Install API Connect Developer Toolkit
Use npm to install API Connect Developer Toolkit:  

1. Type `sudo npm install -g apiconnect`  
**NOTE**: This installation takes several minutes. You may see warnings about deprecated packages. You can ignore these for this installation.

### Part 7: Install Docker

1. Type  
`docker`  
Since it is not installed yet, the response suggests that you install it using apt install docker.io.  
2. Type the following (at the message _Do you want to continue_, type **Y**):  
`sudo apt install docker.io`  
3. Add the user to the docker group. The group may have been created automatically, in which case the first command will generate a warning message. You can ignore this and continue with the second command:  
`sudo groupadd docker`  
`gpasswd dockrr -a bmxuser`
4. When the installation has completed type  
`sudo docker run hello-world`  
You should see the response starting `Hello from Docker!`.  
**NOTE**: You may need to run the command a second time to see the correct response.  

### Part 8: Install cloudfoundry CLI

1. Open a browser to [https://github.com/cloudfoundry/cli/releases]( https://github.com/cloudfoundry/cli/releases).  
2. Click the link for **Debian 64 bit**.  
3. When the dialog opens, asking what to do with the file, accept the default to open it with Software Install. Click **OK**.  
4. The Ubuntu Software installer opens and shows **cf-cli** together with an install button. Click **Install**.  
5. When the install has completed, verify it in the Terminal by typing `cf -v`.  
6. Verify that the response shows the version number of the CLI.

### Part 9: Install the IBM Container plugin for cloudfoundry

1. Use cloudfoundry to install the container plugin (type'**y**' when asked whether you want to install):  
`cf install-plugin https://static-ice.ng.bluemix.net/ibm-containers-linux_x64`  
2. Answer '**Y**' to the warning about binaries.

This completes the setup of the machine.
