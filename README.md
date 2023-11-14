# AOAME
This repository contain the whole app structured with sub-repositories. 

Using AOAME locally
Prerequisites
To run AOAME locally you first need to install the following software:  
Git: https://git-scm.com/downloads  
JDK: https://adoptopenjdk.net/  
Either IntelliJ: https://www.jetbrains.com/idea/download/ (requires academic license)
or Eclipse: https://www.eclipse.org/downloads/ or only Maven: https://maven.apache.org/  
Optionally WebStorm: https://www.jetbrains.com/webstorm/ (requires academic license)  
Node.js: https://nodejs.org/
Important: Install the node version that is required by the WebApp project in package.json.
 
If you want to make changes to the code of the WebService it is recommended to install IntelliJ or Eclipse which comes with its own version of Maven. If you do not plan on making changes to the WebService it is also possible to install Maven on its own.
When installing Eclipse make sure to choose “Eclipse IDE for Enterprise Java and Web Developers”.
WebStorm is not needed for running AOAME locally but it can be used to make changes on the WebApp.
Setup
Start by running the setup_local.bat script.
(link to script: https://github.com/BPaaSModelling/AOAME_Scripts)
This will use git to download the three repositories: _fuseki-heroku-test_, _OntologyBasedModellingEnvironment-WebService_ and _OntologyBasedModellingEnvironment-WebApp_.
After the script has finished, you will need to build the WebService and the WebApp before they can be used.
 
Building the WebService
Using IntelliJ
Start IntelliJ, open the WebService project: click _File_, _Open_, provide the path to WebService. The WebService is inside of newly created _aoame_ folder _OntologyBasedModellingEnvironment-WebService_.
To build the project, click Run and _Edit Configurations_. Then, add the following configuration in IntelliJ and run it.
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/3aadbba3-c726-4a23-a6fb-180bb8b933d4)

 
**Using Eclipse**
Start Eclipse and click _File_ then _Import_… 
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/be0be20d-5b7e-47a5-9974-407d07cd7791)


Select _Projects from Folder or Archive_. Then click on _Next_.
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/d6aad423-12fc-485f-8d2f-df780ed55a94)

The _setup_local.bat_ script should have created a folder called _aoame_ which contains a folder called _OntologyBasedModellingEnvironment-WebService_. Select the _OntologyBasedModellingEnvironment-WebService_ folder by clicking _Directory_… and navigating to it.
After you have selected the directory click _Finish_.
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/7d790bea-854d-40d3-a6ec-629250c1275f)

Now you need to setup a run configuration. To do that click on the down arrow then on _Run As_ and the on _Maven build_.
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/8968a4d0-f97a-47a8-9973-75f61f1e5118)

 
In the _Goals_ field write _package_. Then click on _Run_ to start the Maven build.
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/02816d54-429c-468b-812e-ef4f79463c25)

The next time you want to build the WebService you can run Maven by clicking on _OntologyBasedModellingEnvironment-WebService_ inside the dropdown menu.
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/c749bb25-1f75-4ac0-945c-f4912aef1e9e)

Using Maven directly
If you use Maven directly you can build the WebService by running _mvn verify_.
 
Running/Debugging the WebService
Using IntelliJ
Open _Run configrations_ again, click on the _+_ sign to add a new _JAR Application_.
Provide the _Path to JAR_ according to your setup.
Enter _Program arguments_, as shown below.
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/e25d8a94-11cc-41fb-b435-e07aeb963105) ![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/61331218-80d7-4e76-a8d3-56df0da59e47)

Add Run Maven package to _Before launch_, right below. This will build the project before every launch. 
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/3fb01650-ee0f-45c0-b3a2-6f2ab4e88ac1)

Finally, press run or debug button.
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/f78f289d-cce8-4e83-a816-f0139a769e6f)

 
Building the WebApp
Using WebStorm
First open the folder _OntologyBasedModellingEnvironment-WebApp_ inside WebStorm. Then click on _Add Configuration_…
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/3e7c550b-8165-4733-aaa7-a88663a477ea)

Click on the plus symbol at the top left of the dialog.
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/40a2a21d-f63f-472d-bd2a-a8e4b59d43ba)

Select _npm_ on the dropdown.
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/3271c84e-fcad-4d27-a158-d7d55baf5d51)

On the _Scripts_ dropdown select _build_. You have now added a configuration to build the WebApp.
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/6465ae00-00e9-46b4-82e6-0d7df08d69e7)

To start building the WebApp make sure that _build_ is selected on the dropdown then click on the green arrow to the right of the dropdown.
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/2c6f4d92-4463-4228-8491-383921087a79)

You can also add a second configuration with _heroku-start_. This can be used to start the WebApp through WebStorm.
![image](https://github.com/BPaaSModelling/AOAME/assets/18686110/330aab2f-70aa-4bc7-9960-e29c01eec2f3)

Using the Command line
If you do not want to use WebStorm you can use the command _ng build_ to build the WebApp.
 
Starting AOAME
To start fuseki, the WebService and the WebApp at the same time you can use the _start_local.bat_ script.
To start fuseki on its own run the _fuseki-server.bat_ script inside the _fuseki-heroku-test_ folder.
To start the WebService on its own run the _start webserver.bat_ script inside the _OntologyBasedModellingEnvironment-WebService_ folder.
To start the WebApp on its own run _node server.js_ in a command prompt inside the _OntologyBasedModellingEnvironment-WebApp_ folder.

