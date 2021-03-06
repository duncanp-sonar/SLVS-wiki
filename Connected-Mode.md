# Overview
You can connect SonarLint to SonarQube >= 6.7 or SonarCloud to benefit from the same rules and settings that are used to inspect your project on the server. SonarLint then hides in VS the issues that are marked as **Won’t Fix** or **False Positive**.

## Supported project types
The following Visual Studio project types are supported: C# (.csproj), VB.NET (.vbproj), and C++ (*.vxcproj).
CMake projects are not supported.

_Note: support for *.vcxproj files was added in v4.15._

# Setting up connected mode
#### Step (1) Open the Team Explorer Home tab and click on the SonarQube icon

![Team Explorer home page showing SonarQube icon](https://github.com/SonarSource/sonarlint-visualstudio/blob/master/docs/wiki/ConnectedMode/CM_TeamExplorerHomePage_v4_14.png)

This will display the SonarQube Connections tab:

![SonarQube Connections tab](https://github.com/SonarSource/sonarlint-visualstudio/blob/master/docs/wiki/ConnectedMode/CM_SonarQubeTeamExplorerTab_v4_14.png)

#### Step (2) Click on `Connect...` to display the connection dialogue:

![SonarQube connection dialogue](https://github.com/SonarSource/sonarlint-visualstudio/blob/master/docs/wiki/ConnectedMode/CM_ConnectionDialogue_v4_14.png)

The SonarQube tab is used for connecting to both SonarQube and SonarCloud. To connect to SonarCloud you should enter `https://sonarcloud.io` as the SonarQube server URL.

#### Step (3) Select the server and enter your credentials
You can connect using either a User Token, or a user name and password. We strongly recommend using User Tokens.
The documentation on creating User Tokens is here: 
[SonarQube](https://docs.sonarqube.org/latest/user-guide/user-token/) ; [SonarCloud](https://sonarcloud.io/documentation/user-guide/user-token/)

When using a User Token, enter the token in the "Username/Token" field text box in SLVS and leave the "Password" text box blank.

#### Step (4) Select the Organization (SonarCloud only)
If you are connecting to SonarCloud, you will also be prompted to choose which of your organizations the project belongs to:

![SonarCloud Organixation selection dialogue](https://github.com/SonarSource/sonarlint-visualstudio/blob/master/docs/wiki/ConnectedMode/CM_OrgDialogue_v4_14.png)

You can also connect to public third-party organizations by entering the organization key in the `Other Organizations` tab:

![Other organizations tab](https://github.com/SonarSource/sonarlint-visualstudio/blob/master/docs/wiki/ConnectedMode/CM_Org_OtherOrgs_v4_14.png)

To find the organization key for a third-party organization, browse to the project you want to bind to on [SonarCloud](https://sonarcloud.io/projects). The organization key is displayed on the project page:

![Example project page on SonarCloud](https://github.com/SonarSource/sonarlint-visualstudio/blob/master/docs/wiki/ConnectedMode/CM_ExampleOrgKeyOnSonarCloud.png)

#### Step (5) Select the Sonar project to bind to
The final step is to select the Sonar project want to bind the solution to.
To select a project, either double-click on it, or right-click on it and select `Bind` from the context menu:

![SonarQube project selection list](https://github.com/SonarSource/sonarlint-visualstudio/blob/master/docs/wiki/ConnectedMode/CM_ProjectSelection_v4_14.png)

SonarLint will then fetch the required settings from the server and create local configuration files.

### Connected Mode configuration files
TODO

# Updating the local configuration files
The local Connected Mode configuration files can get out of step with settings on the SonarQube server/SonarCloud e.g. if the Quality Profile for the project is changed on the server.

SonarLint will automatically check whether the server configuration has changed whenever the bound solution is opened in Visual Studio and will ask you whether you want to update the local configuration to match:

![Out of date project configuration warning message](https://github.com/SonarSource/sonarlint-visualstudio/blob/master/docs/wiki//ConnectedMode/CM_OutOfDateConfig_v4_14.png)

Alternatively, you can manually trigger an update from a context menu from the SonarQube tab in the Team Explorer window:

![Connected mode update settings context menu](https://github.com/SonarSource/sonarlint-visualstudio/blob/master/docs/wiki//ConnectedMode/CM_RefreshBinding_v4_14.png)

# Removing a solution from Connected Mode
There is not an "unbind" command to disconnect a solution from SonarQube/SonarCloud. Instead, simply delete the `.sonarlint` folder and its contents.
