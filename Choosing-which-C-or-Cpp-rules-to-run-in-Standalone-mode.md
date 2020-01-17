Starting with version 4.13, it is possible to configure which C/C++ rules are executed.

## Disabling a rule
To disable a rule, select an instance of the rule in the Error List and click the `Disable SonarLint rule` command on the context menu:

[[images/SLVS_ErrorList_DisableCFamily_v4_13.png|alt=Disable SonarLint rule menu command]]

You can view and change the current rule settings by clicking the "Edit rules settings" on the SonarLint `Tools`, `Options` page:

[[images/SLVS_ToolsOptions_Edit_Rules_v4_13.png|alt=Edit rules settings button on the SonarLint Tools Option page.]]

When the rule settings are changed (either by using the `Disable SonarLint rule` command or by directly editing and saving the settings.json file), SonarLint will automatically re-analyse all open documents.

The SonarLint Output window tab contains text output describing the processing that has taken place e.g.:

[[images/SLVS_ReanalysisOutputWindow_v4_13.png|alt=SonarLint output window example text]]

### settings.json file format and location
The `settings.json` file is stored in user's roaming profile `%APPDATA%\SonarLint for Visual Studio`. It applies to all supported versions of Visual Studio. If the machine is domain-joined, then the settings file will be automatically copied to any other machine in the domain that the user logs on to.

The format of the settings file is as follows:
```
{
  "sonarlint.rules": {
    "c:S1135": {
      "level": "On",
      "severity": "Info"
    },
    "cpp:S1199": {
      "Level": "Off",
      "severity": "Minor"
    },
    "cpp:SingleGotoOrBreakPerIteration": {
      "level": "On",
      "parameters": {
        "maxNumberOfTerminationStatements": "1"
      },
      "severity": "Major"
    }
  }
}
```

The settings file can be used to enable or disable specific C/C++ rules. Currently it cannot be used to enable/disable rules for any other languages, or to change the settings for parameterized rules.

The format of the rule key in the file is `[c|cpp]:[rule id]`. The full list of rules is available at https://rules.sonarsource.com/.

The severity of the rule can also be configured (although currently this only affects the label in the `Category` column in the Error List). Valid values are `Blocker`, `Critical`, `Major`, `Minor` and `Info`.

The parameter values for rules that have parameters can also be configured in the file.

If the settings file does not contain an entry for a rule then the default setting for the rule in the SonarWay Quality Profile will be used.

**Note:** if the solution is in [Connected Mode](https://github.com/SonarSource/sonarlint-visualstudio/wiki/Connected-Mode) then the settings file is ignored.