## Connected mode

You can connect SonarLint to SonarQube >= 6.7 or SonarCloud to benefit from the same rules and settings that are used to inspect your project on the server. SonarLint then hides in VS the issues that are marked as **Won’t Fix** or **False Positive**.

When a connected solution is opened in Visual Studio, SonarLint will check whether the quality profile on the server has changed and ask you whether you want to update the local configuration to match. Alternatively, you can manually trigger a refresh from the SonarQube tab in the Team Explorer window.
[TODO - image]

### Setting up connected mode
#### Step (1) Open the `SonarQube` tab in the Team Explorer and click `Connect`:
[TODO - image]

The SonarQube tab is used for connecting to both SonarQube and SonarCloud. To connect to SonarCloud you should enter `https://sonarcloud.io` as the server address when prompted.

#### Step (2) Select the server and enter your credentials
You can connect using either user name and password, or a User Token.
The documentation on creating User Tokens is here: 
[SonarQube](https://docs.sonarqube.org/latest/user-guide/user-token/) ; [SonarCloud](https://sonarcloud.io/documentation/user-guide/user-token/)

When using a User Token, enter the token in the "Username/Token" field text box in SLVS and leave the "Password" text box blank.

[TODO -image]

#### Step (3) Select the Organization (SonarCloud only)
If you are connecting to SonarCloud, you will also be prompted to choose which of your organizations the project belongs to:

[TODO -image]
You can also connected to public third-party organisations.

#### Step (4) Select the Sonar project
The final step is to select the Sonar project want to bind the solution to:
[TODO -image]

### Supported project types
The following Visual Studio project types are supported: C# (.csproj), VB.NET (.vbproj), and C++ (*.vxcproj).
CMake projects are not supported.