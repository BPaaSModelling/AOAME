# Using AOAME locally

## Prerequisites

To run AOAME locally you first need to install the following software:

Git: <https://git-scm.com/downloads>

JDK: <https://adoptium.net/temurin/archive/?version=17> Make sure you install the current version of the project: **Temurin 17.0.7+7**

Either IntelliJ: <https://www.jetbrains.com/idea/download/> (requires academic license)

or Eclipse: <https://www.eclipse.org/downloads/> or only Maven: <https://maven.apache.org/>

Optionally WebStorm: <https://www.jetbrains.com/webstorm/> (requires academic license)

Node.js: https://nodejs.org/en/blog/release/v16.4.2  
Important: Install the node version that is required by the WebApp project in package.json. Check it via the link: [WebApp repo package.json](https://github.com/BPaaSModelling/OntologyBasedModellingEnvironment-WebApp/blob/master/package.json)  
![Ein Bild, das Schrift, Text, Handschrift, Typografie enthält. Automatisch generierte Beschreibung](media/de719ec34e76cd354f816c9942a430fa.png)

If you want to make changes to the code of the WebService it is recommended to install IntelliJ or Eclipse which comes with its own version of Maven. If you do not plan on making changes to the WebService it is also possible to install Maven on its own.

When installing Eclipse make sure to choose “Eclipse IDE for Enterprise Java and Web Developers”.

WebStorm is not needed for running AOAME locally but it can be used to make changes on the WebApp.

## Setup

Start by running the *setup_local.bat* script.  
(link to script: <https://github.com/BPaaSModelling/AOAME_Scripts>)

This will use git to download the three repositories: *fuseki-heroku-test*, *OntologyBasedModellingEnvironment-WebService* and *OntologyBasedModellingEnvironment-WebApp.*

After the script has finished, you will need to build the WebService and the WebApp before they can be used.

# Building the WebService

## Using IntelliJ

Start IntelliJ, open the WebService project: click *File*, *Open*, provide the path to WebService. The WebService is inside of newly created *aoame* folder *OntologyBasedModellingEnvironment-WebService.*

To build the project, click *Run* and *Edit Configurations*. Then, add the following configuration in IntelliJ and run it.

![Ein Bild, das Text, Screenshot, Software, Multimedia-Software enthält. Automatisch generierte Beschreibung](media/b9272fc3f8e3dc466663c5f51b40a981.png)

## Using Eclipse

Start Eclipse and click *File* then *Import…*![](media/ab35623fca096f8ed0f4e7e706deca72.png)

Select *Projects from Folder or Archive*. Then click on *Next*.

![](media/6d7c73468e82a5148f7df757566b3fc6.png)

The *setup_local.bat* script should have created a folder called *aoame* which contains a folder called *OntologyBasedModellingEnvironment-WebService.* Select the *OntologyBasedModellingEnvironment-WebService* folder by clicking *Directory…* and navigating to it.

After you have selected the directory click *Finish*.

![](media/78d72e6861cd432b2df37716aedbace0.png)

Now you need to setup a run configuration. To do that click on the down arrow then on *Run As* and the on *Maven build.*

![](media/114b186aea5287f2cc9e110d43eb89a2.png)

In the *Goals* field write *package.* Then click on *Run* to start the Maven build.

![](media/d225d1b3f97fe426dae0ea456557454b.png)

The next time you want to build the WebService you can run Maven by clicking on *OntologyBasedModellingEnvironment-WebService* inside the dropdown menu.

![](media/2bbbec65e82c0473e2809e64a2247031.png)

## Using Maven directly

If you use Maven directly you can build the WebService by running *mvn verify.*

*  
*

# Running/Debugging the WebService

## Using IntelliJ

Open *Run configrations* again, click on the *+* sign to add a new *JAR Application*.

Provide the *Path to JAR* according to your setup.  
Enter *Program arguments*, as shown below.

![Ein Bild, das Screenshot, Text, Software, Multimedia-Software enthält. Automatisch generierte Beschreibung](media/ec006f24da8950d00e22a034a276a1d2.png)![Ein Bild, das Text, Screenshot, Software, Multimedia-Software enthält. Automatisch generierte Beschreibung](media/0e487bff81b68d77a71b14028bb7e884.png)

Add Run Maven package to *Before launch,* right below. This will build the project before every launch.

![Ein Bild, das Text, Schrift, Screenshot enthält. Automatisch generierte Beschreibung](media/4e81c2d68899d36f834e0c5b15a9b3cb.png)

Finally, press run or debug buttons.

![Ein Bild, das Text, Schrift, Screenshot, Design enthält. Automatisch generierte Beschreibung](media/bb5569cc2e5e796833bca8f3fd9e6931.png)

# Building the WebApp

## Using WebStorm

First open the folder *OntologyBasedModellingEnvironment-WebApp* inside WebStorm. Then click on *Add Configuration…*

![](media/333617297572574caddb4dd8cf3a8054.png)

Click on the plus symbol at the top left of the dialog.

![](media/ac287b0db2ea82aff035e7c6547858f2.png)

Select *npm* on the dropdown.

![](media/742751fe05cfa548562da84f6eb3b658.png)

On the *Scripts* dropdown select *build.* You have now added a configuration to build the WebApp.

![](media/ea92175e2d2513a7e44b8044af182596.png)

To start building the WebApp make sure that *build* is selected on the dropdown then click on the green arrow to the right of the dropdown.

![](media/25c8462c5bca5b372061b62d84930091.png)

You can also add a second configuration with *heroku-start*. This can be used to start the WebApp through WebStorm.

![](media/60242dbde1711737379b10c948a1f4ca.png)

## Using the Command line

If you do not want to use WebStorm you can use the command *ng build* to build the WebApp.

# Starting AOAME

To start fuseki, the WebService and the WebApp at the same time you can use the *start_local.bat* script.

To start fuseki on its own run the *fuseki-server.bat* script inside the *fuseki-heroku-test* folder.

To start the WebService on its own run the *start webserver.bat* script inside the *OntologyBasedModellingEnvironment-WebService* folder.

To start the WebApp on its own run *node server.js* in a command prompt inside the *OntologyBasedModellingEnvironment-WebApp* folder.

# Pushing the artifact to GitHub and AOAME

To push your version to GitHub follow the steps below:

1\. Ensure you have access to the required repositories for your project. Depending on the scope, it might be 1-3 repos:

<https://github.com/BPaaSModelling/OntologyBasedModellingEnvironment-WebApp>

<https://github.com/BPaaSModelling/OntologyBasedModellingEnvironment-WebService>

To push a new ontology you will need access to:  
<https://github.com/BPaaSModelling/Ontology4ModelingEnvironment>

2\. Create a personal access token to push it from Intellij/WebStorm/Eclipse, unless you have another authentication method like the ssh key. Usually, the GitHub account password doesn’t work.

Open GitHub -\> Settings -\> Developer Settings -\>Personal access tokens -\> Tokens (classic) -\> Create one token with default repo access -\> copy the token, you will need it later.

3\. Open Intellij/WebStorm/Eclipse. Go to Git -\> Connect to the respective repository -\> Use your token as a password when connecting.

4\. Create a new branch for your version, commit all your changes, and push.

![](media/6d9de8b321c5a6833363c129b4a5df26.png)

5\. Now, merge your branch into the master branch.

In Intellij or WebStorm, right-click the master branch and click "checkout the master". Now, you can merge your branch into the master branch (screenshot below). Once it is done, please test that everything works as expected. If testing is successful, push the new master branch.

![](media/1ef3f813a04304340b264a67411c046d.png)

If you need to push to the Ontology4ModelingEnvironment repo, first you need to merge the master into your own branch.

Create a Pull request directly from GitHub that will be merged when approved (see screenshots).

![Image preview](media/868da44782ed4f759a2e5894f22d6d61.png)

![Image preview](media/457cdc90f5c3e9580e15afd8f21c46d2.png)
