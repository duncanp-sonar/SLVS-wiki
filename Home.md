# SonarLint for Visual Studio

SonarLint is an IDE extension that helps you detect and fix quality issues as you write code. Like a spell checker, SonarLint squiggles flaws so they can be fixed before committing code. You can get it directly from the VS Marketplace and it will then detect new bugs and quality issues as you code (for C#, VB.NET,JavaScript, and C++).

SonarLint is also available for VS Code, Eclipse and IntelliJ (the languages supported vary from IDE to IDE).

## How it works

Simply open a project containing C#, VB, C++ or JS files.

For C# and VB.Net, new issues will be reported as you type. You do not have to select 'Run Code Analysis' from the 'Analyze' menu - the rules are run automatically.
Note: by default, VS is configured to only run Roslyn analyzers on files that are currently open. You can choose to have the analysis run on the entire solution as described in the [Microsoft docs](https://docs.microsoft.com/en-us/visualstudio/code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code?view=vs-2019), although this is obviously more processor-intensive.


For C++ and JavaScript, new issues will be reported when you save the file. Issues are highlighted in your code, and also listed in the 'Error List'.

You can access the detailed rule description directly from the issue in the Error List, using the `Show Error help` option on the contextual menu.

## Rules

Check the rules to see what SonarLint can do for you:

- [C# rules](https://rules.sonarsource.com/csharp)
- [VB.NET rules](https://rules.sonarsource.com/vbnet)
- [JavaScript rules](https://rules.sonarsource.com/javascript)
- [C/C++ rules](https://rules.sonarsource.com/cpp)

You will benefit from the following code analyzers: [SonarC#](https://redirect.sonarsource.com/plugins/csharp.html), [SonarVB](https://redirect.sonarsource.com/plugins/vbnet.html), [SonarCFamily for C/C++](https://redirect.sonarsource.com/plugins/cpp.html) and [SonarJS](https://redirect.sonarsource.com/plugins/javascript.html).


## Requirements

For C#, VB.NET and C/C++ the only thing you need to install is the VSIX.

To enables support for JavaScript analysis, see [Support for Additional Languages](https://github.com/SonarSource/sonarlint-visualstudio/wiki/Support-for-Additional-Languages)

### Standalone mode
By default SonarLint runs in standalone mode i.e. completely independently of SonarQube/SonarCloud.

#### Choosing which C#/VB.NET rules to run in Standalone mode
Note: configuring which C++ or JavaScript rules run is not currently supported.

The SonarC# and SonarVB rules are implemented as [Roslyn VSIX analyzers](https://docs.microsoft.com/en-us/visualstudio/code-quality/install-roslyn-analyzers?view=vs-2019), and you can configure which rules are executed using the normal [ruleset](https://docs.microsoft.com/en-us/visualstudio/code-quality/use-roslyn-analyzers?view=vs-2019#rule-sets) mechanism in VS.

#### Choosing which C/C++ rules to run in Standalone mode
See [Choosing which C/C++ rules to run in Standalone mode](https://github.com/SonarSource/sonarlint-visualstudio/wiki/Choosing-which-C-or-Cpp-rules-to-run-in-Standalone-mode).

#### Choosing which JavaScript rules to run in Standalone mode
It is not currently possible to configure which Javascript are run.


### Connected mode
In connected mode, the solution is linked to a project in SonarQube/SonarCloud. See [Connected Mode](https://github.com/SonarSource/sonarlint-visualstudio/wiki/Connected-Mode) for more information.

Note: Connected mode is currently only supported for C#, VB.NET, and C++ projects.

## Contributions

If you would like to see a new feature, please create a new thread in the forum ["Suggest new features"](https://community.sonarsource.com/c/suggestions/features).

Please be aware that we are not actively looking for feature contributions. The truth is that it's extremely difficult for someone outside SonarSource to comply with our roadmap and expectations. Therefore, we typically only accept minor cosmetic changes and typo fixes.

With that in mind, if you would like to submit a code contribution, please create a pull request for this repository. Please explain your motives to contribute this change: what problem you are trying to fix, what improvement you are trying to make.

Make sure that you follow our [code style](https://github.com/SonarSource/sonar-developer-toolset#code-style) and all tests are passing.

## Have Question or Feedback?

For SonarLint support questions ("How do I?", "I got this error, why?", ...), please first read the [FAQ](https://community.sonarsource.com/t/frequently-asked-questions/7204) and then head to the [SonarSource forum](https://community.sonarsource.com/c/help/sl). There are chances that a question similar to yours has already been answered. 

Be aware that this forum is a community, so the standard pleasantries ("Hi", "Thanks", ...) are expected. And if you don't get an answer to your thread, you should sit on your hands for at least three days before bumping it. Operators are not standing by. :-)

## License

Copyright 2017-2019 SonarSource.

Licensed under the [GNU Lesser General Public License, Version 3.0](http://www.gnu.org/licenses/lgpl.txt)
