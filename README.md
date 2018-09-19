# Jira-SetUp-MacOS
This is a tutorial and how to set-up Jira Software Service on MacOS.

## Introduction
When I got my licenses for Jira Software I was originally having trouble configuring it with my Mac.This is tutorial is
to guide fellow developers set-up Jira Software Server on their Mac. My objective to is to create a detailed 
step-by-step guideline to make the process the least confusing as possible. Let's proceed ! 

## Install or Update JAVA

### Verify Working Version of JAVA
To check you have a working version of Java, in command line run `java -version`

A working version of Java will output the following:

```
MacBook-Pro-2:~ user$ java -version
java version "1.8.0_131"
Java(TM) SE Runtime Environment (build 1.8.0_131-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.131-b11, mixed mode)

```


### Downloading and Installing JAVA 
Otherwise, if you do **NOT** have a working version of Java you must download and install Java.

1. To install Java , click on the following [Java SE Development Kit 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
2. `Accept License Agreement`, and download the `Mac OS X` under the 'Product/ File Description' Category
3. Double click the `.dmg` downloaded file and once the installer has loaded click `install`.
4. After installation, close the current terminal and open a new terminal. Run the command, `java -version`. Your output should be something similar to the oupit above for a `working version of Java`.

### Setting JAVA Enviroment Variable

Open up terminal, which will be by default in your `home` directory.

In terminal run, `ls -a ` , which will output your hidden files. Then open the file `.bash_profile`.

If the file `.bash_profile` does NOT exist you can simply create one by running the command `touch .bash_profile`

Open, `.bash_profile`, and modify to set JAVA_HOME

```
# JAVA_HOME Set-Up
export JAVA_HOME = /Library/Java/JavaVirtualMachines/jdk1.8.0_101.jdk/Contents/Home
```

## Downloading JIRA for MacOS

1. To download Jira Software Server, click on the following [Download Jira Software](https://www.atlassian.com/software/jira/download)
2. Set Operating System option for `OS X` and then click on `Download`
3. Click on the downloaded zip file to unzip the folder.
4. Move the unzipped folder to `Desktop`.

## Set JIRA Home Directory 

1. Inside your unziped folder go to the location , `user > Desktop > atlassian-jira-software-7.12.1-standalone > atlassian-jira > WEB-INF > classes`
2. Inside the `classes` folder look for the file `jira-application.properties`.
3. Make a new folder in `Desktop` called `JiraHome`. 
4. Now open the file `.jira-application.properties`, and set the path `jira.home` to the path of `JiraHome` folder.

`.jira-application.properties` file should look like this: 

```
# Do not modify this file unless instructed. It is here to store the location of the JIRA home directory only and is typically written to by the installer.
jira.home = /Users/user/Desktop/JiraHome
```

Note: When you start JIRA Server files and logs will be created inside the `JiraHome` folder. 

## JIRA TOMCAT Server

### Start Shell Script 
Locate the  `start.sh` file. 

Open up terminal and go to `user > Desktop > atlassian-jira-software-7.12.1-standalone > atlassian-jira > `

To make sure you're in the correct working directory, run the following on terminal: 
```$xslt
$pwd 
/Users/user/Desktop/atlassian-jira-software-7.12.1-standalone/bin
```

Inside the `bin` directory, run `sh starup.sh`

When you run `sh startup.sh`, the following should occur:

```$xslt
MacBook-Pro-2:bin user$ sh startup.sh
                .....
          .... .NMMMD.  ...
        .8MMM.  $MMN,..~MMMO.
        .?MMM.         .MMM?.

     OMMMMZ.           .,NMMMN~
     .IMMMMMM. .NMMMN. .MMMMMN,
       ,MMMMMM$..3MD..ZMMMMMM.
        =NMMMMMM,. .,MMMMMMD.
         .MMMMMMMM8MMMMMMM,
           .ONMMMMMMMMMMZ.
             ,NMMMMMMM8.
            .:,.$MMMMMMM
          .IMMMM..NMMMMMD.
         .8MMMMM:  :NMMMMN.
         .MMMMMM.   .MMMMM~.
         .MMMMMN    .MMMMM?.

      Atlassian JIRA
      Version : 7.12.1
                  

If you encounter issues starting or stopping JIRA, please see the Troubleshooting guide at http://confluence.atlassian.com/display/JIRA/Installation+Troubleshooting+Guide


Server startup logs are located in /Users/user/Desktop/atlassian-jira-software-7.12.1-standalone/logs/catalina.out
Using CATALINA_BASE:   /Users/user/Desktop/atlassian-jira-software-7.12.1-standalone
Using CATALINA_HOME:   /Users/user/Desktop/atlassian-jira-software-7.12.1-standalone
Using CATALINA_TMPDIR: /Users/user/Desktop/atlassian-jira-software-7.12.1-standalone/temp
Using JRE_HOME:        /Library/Java/JavaVirtualMachines/jdk1.8.0_131.jdk/Contents/Home
Using CLASSPATH:       /Users/user/Desktop/atlassian-jira-software-7.12.1-standalone/bin/bootstrap.jar:/Users/user/Desktop/atlassian-jira-software-7.12.1-standalone/bin/tomcat-juli.jar
Using CATALINA_PID:    /Users/user/Desktop/atlassian-jira-software-7.12.1-standalone/work/catalina.pid
Existing PID file found during start.
Removing/clearing stale PID file.
Tomcat started.

```

### Shutdown Shell Script 

To stop the TOMCAT Server , inside the `bin` directory, run `sh shutdown.sh`

## Start Using JIRA

As previously mentioned, to use JIRA you must run the Start Shell Script `sh startup.sh`

Now open up your browser, and type `localhost:8080` 

It should render, the Atlassian Logo with a message displaying `Atlassian Jira is starting up `


### First Time Users

1. Once Jira has started up, it will redirect you to the `Jira setup` screen.
2. Recommend, clicking on `Set it up for me` and click `Continue to MyAtlassian`
3. The next screen, will ask you to select your product in our case we select `Jira Software` and then click `select` under the Licence Type Jira Software (Server). Proceed, by clicking on `Generate License`.
4. You will be prompted at the `Administrator account setup`. Complete all the fields. Then click `Next`.
5. `Finishing your setup` will show up.
5. `Let's get started`

**VOILA YOU'RE READY TO USE JIRA SOFTWARE SERVER!**





