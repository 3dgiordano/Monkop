<p align="center">
  <a href="https://www.monkop.com/">
    <img src="https://www.monkop.com/img/enterprise/Monkey-footer.svg">
  </a>

  <h3 align="center">Monkop</h3>

  <p align="center">
    Measure, analyze and optimize the performance of your Android and iOS apps.
    <br>
    <br>
    <a href="https://github.com/MonkopApps/Monkop/issues/new">Report bug</a>
    -
    <a href="http://blog.monkop.com/">Blog</a>
  </p>
</p>

## Table of contents

- [Getting Started](#getting-started)
    - [Create your account](#create-your-account)
    - [Upload your app to Monkop](#upload-your-app-to-monkop)  
    - [Ad Hoc mode for iOS apps](#ad-hoc-mode-for-ios-apps)
 
- [Understanding Monkop Report](#understanding-monkop-report)

- [Monkop CLI](#monkop-cli)

- [Integrations](#integrations)
   - [Performance Profiling with Espresso](#performance-profiling-with-espresso)       
   - [Jenkis](#jenkis)
   - [Travis](#travis)
   - [Github](#github)


## Getting Started

#### 1- Create your account
Go to [http://www.monkop.com/](http://www.monkop.com/) and the first thing you need to do is [set a new account](https://console.monkop.com/register.xhtml?faces-redirect=true). 

#### 2- Upload your app to Monkop
Upload your .ipa (iOS App) or .apk (Android App) and Monkop will test it for you. In less than 24 hrs you will receive a detailed report in your inbox!

#### Ad Hoc mode for iOS apps
For IOS apps you need to export your app in ad hoc mode before uploading it to Monkop. The following steps will help you accomplish this task:

**1) Archiving Your App**

Create an archive of your app. Xcode stores this archive in the Archives organizer.
Choose Product > Archive. The Archives organizer appears and displays the new archive.

![adHoc](http://www.monkop.com/img/github/adHoc.jpg)


**2) Exporting Your App to IPA**

To create an iOS App file for testing, select the archive in the Archives organizer.

![adHoc2](http://www.monkop.com/img/github/adHoc2.jpg)

Click the Export button, and select “Ad Hoc”. The app will be code signed with the distribution certificate.

![adHoc3](http://www.monkop.com/img/github/adHoc3.jpg)

Click the Next button until the process finishes.

![adHoc4](http://www.monkop.com/img/github/adHoc4.jpg)

In the dialog that appears, review the app, its entitlements, and the provisioning profile.
The ad hoc provisioning profile should contain the text: “Ad Hoc”.

Click the Export button and export the ipa file.



## Understanding Monkop Report
Every time you run a test, a new report is created. After that, Monkop emails you including the report link address. Here is a brief guide to understand the report sections and how to navigate it.

#### Overview

This section explains how to understand Monkop report after each execution (test-ride). This is how it looks like:

The report is a web page, so it can be accessible from any browser. It contains a left navigation panel and dashboard overview.

**Navigation Panel:** The left menu contains all sections and highlighted warnings and cautions. This panel enables users to navigate across:

**- Dashboard:** Contains market stats and selected devices

**- Executions:** The most important section, containing each device information like OS version, screen and hardware details, and also execution-related information such as: videos, screenshots, installation process, timing measures, resources and logs.

**- Information**: General information about the application under test, such as: version, compatibility, permissions requested, activities and included libraries.

**- Correctness, Performance, Resource usage, security and power sections:** each section containing analyzed behavior over all devices. Yellow / red indicators are values out of Monkop’s default thresholds, which are based on Google best practices and important market researches.

**- Errors:** Contains crashes reports, and logs when app is not responding (ANR).

This section contains a market chart, execution details, device selection segment (by screen density) and test-run information.

The following chart shows the latest Android market stats based on data [collected by Google](https://developer.android.com/about/dashboards/?utm_source=monkop).

#### Executions

This is the **most important section**, since it has each device-specific execution. It shows executions that user has manually selected, or those one that Monkop has automatically selected for him.

![Report1](http://www.monkop.com/img/github/Report1.png)

Clicking on any device, users will find device specific information about execution:

![Report2](http://www.monkop.com/img/github/Report2.png)

Below this information users will find all details about device performance, videos, screenshots and logs.

![Report3](http://www.monkop.com/img/github/Report3.png)

![Report4](http://www.monkop.com/img/github/Report4.png)


You can also download a more detailed [pdf guide here](https://static.monkop.com/documents/Explaining%20Report.pdf).


## Monkop CLI

![MonkopCLI](https://www.monkop.com/img/addons/cli.png)

Monkop CLI is a command-line tool that enables a new kind of automation in your build process, allowing you to run Monkop tests automatically in your development cycle (without disturbance). 

![MonkopCLIPipeline](http://www.monkop.com/img/github/MonkopCLIPipeline.jpg)

Monkop will test your mobile apps in different kinds of real devices while your team remains focused on others steps of your building process. All you need is a Monkop account and to follow these simple steps to enable your app to be tested.

#### Installing Monkop CLI

Monkop CLI is a Python (v2.7) script that handles all communication with Monkop’s API using [your account (APIKey)](https://console.monkop.com/apikey.xhtml?red=apikey). Once you have it, just download the latest version here: [monkop.com/cli](https://t.umblr.com/redirect?z=http%3A%2F%2Fmonkop.com%2Fcli&t=NjAwYTNkMDQ4YWJlNWNjNzA0OGJjOTA1YjZlMTM4ZjYzYjBkMGJjMSxxd1NzMGI2OA%3D%3D&b=t%3Aj2vXGmOlJnvqzl_PwMFFbw&p=http%3A%2F%2Fblog.monkop.com%2Fpost%2F145870436366%2Fmonkop-cli-for-your-build-pipeline&m=1)



#### Command Line Interface Options

You can get help from the command-line tool by calling monkop-cli -h

\> monkop-cli -h

  Usage: monkop-cli.py -k apikey [-t time] [-w] [-a appfile] [-st type]
                    [-sf scriptfile] [-c callbackurl] [-e extradata]
                    [-s transaction] [-h]


**General:**

 -k apikey            Your API Key ([https://console.monkop.com/apikey.xhtml](https://console.monkop.com/apikey.xhtml))
 
 -t time                Test duration in minutes (per device)
 
 -w                       Wait for completion
 
 -n                        Don’t return error code on test errors (status_code 
                             will be always 0)

**Application:**

 -a appfile           Public URL or local path to application file

**Script:**

 -st type              Type of script file. Valid values: ESPRESSO
 
 -sf scriptfile       Public URL or local path to script file

**Notification:**

 -c callbackurl    Public URL for notification purposes
 
 -e extradata     Extra data to be defined by customer, this data will be
                            returned in the notification callback

**Status:**

 -s transaction  Get transaction status

**Help:**

 -h, –help           Show this help message and exit
 
#### Run your first test

First you need your app ready, if you don’t have one, you still can test some 3rd-party app to see what happens: 

\> python monkop-cli.py -k [YOURAPIKEY](https://console.monkop.com/apikey.xhtml) -w -a “[http://static.monkop.com/setup/apps_demo/Google_IO_2016_4.4.6.apk](http://static.monkop.com/setup/apps_demo/Google_IO_2016_4.4.6.apk)”

#### Download and run in a single line with CURL

\> curl -sL [monkop.com/cli](https://t.umblr.com/redirect?z=http%3A%2F%2Fmonkop.com%2Fcli&t=NjAwYTNkMDQ4YWJlNWNjNzA0OGJjOTA1YjZlMTM4ZjYzYjBkMGJjMSxxd1NzMGI2OA%3D%3D&b=t%3Aj2vXGmOlJnvqzl_PwMFFbw&p=http%3A%2F%2Fblog.monkop.com%2Fpost%2F145870436366%2Fmonkop-cli-for-your-build-pipeline&m=1) \| python - -k [YOURAPIKEY](https://console.monkop.com/apikey.xhtml) -w -a  “[http://static.monkop.com/setup/apps_demo/Google_IO_2016_4.4.6.apk](http://static.monkop.com/setup/apps_demo/Google_IO_2016_4.4.6.apk)”

#### Prerequisites

Enable the use of the API Key on Add-ons:
[https://console.monkop.com/addOns.xhtml](https://console.monkop.com/addOns.xhtml)

Python 2.7 installed (already installed on most Linux distros and Mac OS X)
[https://www.python.org/download/releases/2.7/](https://www.python.org/download/releases/2.7/)

If the build runs over Windows, you may need to install CURL, and to have the CURL binary on same path of monkop-cli.py or accessible in path environment variable: [https://curl.haxx.se/download.html](https://curl.haxx.se/download.html)


#### Limitations

Monkop CLI for non-enterprise customers is only available for the Android Platform.


## Integrations

#### UI Automations 

##### Performance Profiling with Espresso

![Expresso](https://www.monkop.com/img/addons/espresso.png)

Monkop also supports  instrumentation frameworks like Espresso. This allows you to test and profile their apps on all Android OS versions and top device brands by attaching Espresso scripts and waiting for the test execution in our device-lab.

To use Espresso scripts on Monkop, follow these simple steps:

1) Sign in and upload your app

2) Upload your Espresso scripts using option #2 of the image below:
 
![EspressoOption](http://www.monkop.com/img/github/EspressoOption.png)
 
3) Wait for the results in your inbox.



#### Continuous Integration

When we use Continuous Integration tools, we start looking at automation, notifications and testing as part of our daily tasks. Basically devs love CI tools because they can sleep better at night eliminating hassles often caused by long integration cycles: broken builds, manual merging hell and regressions in a huge fragmented world.
Adding Monkop CLI after your build process will provide your team a dedicated bot that automatically installs your app on all relevant real devices (including different OS versions / screen sizes) and starts playing with it, looking for crashes and other common problems.
 

##### Jenkis

![Jenkis](https://www.monkop.com/img/addons/jenkins_logo.png)

With this Jenkins integration you will be able to add mobile tests on real devices to your builds and auto-tag releases with test results. 

**Setting up Monkop for Jenkins**

1.- Create a new freestyle job: 

![Jenkis1](http://www.monkop.com/img/github/Jenkins1.png)

2.- Create a command line build step.
  - Linux: “Execute shell” 
  - Windows: “Execute Windows batch command” 
  
![Jenkis2](http://www.monkop.com/img/github/Jenkis2.png)

setting the following commands inside:	

Windows:
\> curl -sL monkop.com/cli \| python - -k %monkopapikey% -a “path_to_build.apk”

Linux/Mac OS X:
\> curl -sL monkop.com/cli \| python - -k $monkopapikey -a “path_to_build.apk”

3.-  Consider setting monkopapikey as an environment variable using [EnvInject Plugin](https://wiki.jenkins.io/display/JENKINS/EnvInject+Plugin) and injecting the variable as a password in your job

![Jenkis3](http://www.monkop.com/img/github/Jenkins3.png)

> Note: Environment variables can be accessed using the syntax $monkopapikey (Linux/Mac OS X) or %monkopapikey%  (Windows). 

**Prerequisites**

Monkop CLI uses Python + CURL to use Monkop’s API in order to run tests, show results and also update build status (if needed). So the prerequisites are:

1- CURL: If you don’t have it, please install curl where Jenkins will run your build process.
2- Enable the use of the API getting your APIKey on your Monkop account under the ‘Add-ons’ option [https://console.monkop.com/addOns.xhtml](https://console.monkop.com/addOns.xhtml)
3- Python 2.7 installed (installed by default on Mac OS X and most Linux distros) [https://www.python.org/download/releases/2.7/](https://www.python.org/download/releases/2.7/)

Adding Monkop tests to your Jenkins pipeline will let your team automatically get key information on each build regarding how your app behaves on real devices while evaluating mobile-side performance. 

##### Travis

![Travis](https://www.monkop.com/img/addons/travis_logo.png)

###### Setting Up Monkop for Travis

1. Enable Monkop’s API in your Add-ons section: [https://console.monkop.com/addOns.xhtml](https://console.monkop.com/addOns.xhtml)

![Travis1](http://www.monkop.com/img/github/Travis1.png)

2. Add Monkop APIKey as a Travis-CI Variable in [Repository Settings](https://docs.travis-ci.com/user/environment-variables/#Defining-Variables-in-Repository-Settings) named **monkopapikey**:

![Travis2](http://www.monkop.com/img/github/Travis2.png)

3. Update your travis file **.travis.yml** 
We recommend using Monkop-cli in the **after_success** section, but each DevOp designs his or her own pipeline:

\> curl -sL monkop.com/cli \| python - -k $monkopapikey -a “path_to_build.apk”

\> Sample .travis.yml

language: android

jdk: oraclejdk7

android:
  components:
     - build-tools-19.0.0
     
after_success:
- curl -sL monkop.com/cli \| python - -k $monkopapikey -a “path_to_build.apk” 


**Note:** According to [travis-ci documentation](https://docs.travis-ci.com/user/customizing-the-build/), if Monkop-cli is invoked from a script step, any failure of the apk processing will make your travis build fail. On the other hand, if you set up Monkop-cli on after_success or after_script step, your Monkop tests will never affect your build result.

#### Version Control and SCM

##### Github
![Github](https://www.monkop.com/img/addons/github.png)

###### Pull request integration for GitHub
Monkop has a bot that contributes to your build steps and documentation with test results by automatically tagging / commenting on your pull requests inside your GitHub repository. All you need to do is give access to Monkop inside your GitHub account. 

**Using OAuth authentication method:**

1. Enable github add-ons in the Monkop console and authorize to give Monkop these permissions:

![Github1](http://www.monkop.com/img/github/Github1.png)

2.  You will be redirected to GitHub in order to authorize application:

![Github2](http://www.monkop.com/img/github/Github2.png)

3. Then you will see your GitHub account info inside Monkop’s console:

![Github3](http://www.monkop.com/img/github/Github3.png)

**Now all pull-requests in GitHub can be tagged by Monkop**

![Github4](http://www.monkop.com/img/github/Github4.png)

To revoke Monkop privileges, click the revoke access button in GitHub add-ons section in the Monkop console. This will redirect you to GitHub settings so you can revoke access anytime: 

![Github5](http://www.monkop.com/img/github/Github5.png)

As a result you will be adding Monkop to your pipeline, enabling your team to have each build under test using real devices, tagged and documented with just a few steps, running smoke / sanity tests, evaluating mobile side performance or running even more complex tests. 







