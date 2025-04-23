



MyVale
================================================================================

A personal collection of style-guide rules for use with the Vale linter.

Use *MyVale* to check and enforce writing conventions across your documents. This repository contains custom and borrowed rules, along with a configuration file that Vale uses by default. It serves as an example of how to work with Vale using personalized style rules.


Prerequisites
--------------------------------------------------------------------------------

  - [Vale](https://vale.sh/docs/install) should be installed (for example, via Scoop or another package manager). Confirm that Vale is available on your system's `PATH`:

  ```bash
  vale -v
  ```

  - Git (or a Git client) should be installed to clone and manage this repository.

  - (Optional) Visual Studio Code with the [Vale extension for VSCode](https://marketplace.visualstudio.com/items?itemName=ChrisChinchilla.vale-vscode).


Installation
--------------------------------------------------------------------------------

### Clone the repository

Navigate to your `.config` directory (or the Windows equivalent):

```bash
cd ~/.config/
```

Then, clone the repository:

```bash
git clone git@github.com:dylan-k/MyVale.git vale
```

This command creates a `~/.config/vale/` directory that holds your custom style rules.

### Link the configuration file

Vale searches for your global `.vale.ini` in different directories, depending on your operating system:

  - **Windows**: `%LOCALAPPDATA%\vale\.vale.ini`
  - **macOS**: `$HOME/Library/Application Support/vale/.vale.ini`
  - **Unix**: `$XDG_CONFIG_HOME/vale/.vale.ini`

Run `vale ls-dirs` to see the exact locations Vale checks on your system.

Create a hard link (`.vale.ini`) so changes remain under version control:

**Linux/macOS**:

```bash
ln ~/.config/vale/.vale.ini ~/.vale.ini
```

**Windows (PowerShell)**:

```powershell
New-Item -ItemType HardLink -Path "$Env:USERPROFILE\.vale.ini" -Target "$Env:USERPROFILE\.config\vale\.vale.ini"
```

### Verify the StylesPath setting

Check the value of `StylesPath` in your `.vale.ini` file. By default, it should point to `~/.config/vale/styles`. Update if necessary.

### Initialize your local config

Once you have your local `.vale.ini` in the directory of your choice, run

```
vale sync
```

from the command line to load or initialize it.


Configuration Tips
--------------------------------------------------------------------------------

### Custom alias (optional)

You can add an alias to quickly edit Vale settings:

```bash
alias valestyles="cd ~/.config/vale && code ."
```

Adjust this  to match your preferred editor, operating system, and so on.

### Using MyVale with VS Code

To integrate Vale into Visual Studio Code, install the [Vale extension](https://marketplace.visualstudio.com/items?itemName=errata-ai.vale-server) and configure it:

```json
// Example settings.json snippet (Windows)
"vale.server.serverURL": "",
"vale.core.useCLI": true,
"vale.valeCLI.path": "vale",
"vale.server.lintContext": -1,
"vale.server.provideFixes": false,
"vale.valeCLI.config": "%USERPROFILE%\\.vale.ini",
"vale.valeCLI.minAlertLevel": "suggestion"
```

**Tip:** Exclude your Vale settings from VS Code's settings sync if you plan to use different paths or configurations on other machines.


Updating Styles
--------------------------------------------------------------------------------

These rules come from various sources. To update most of them, run this command:

```
vale sync
```

Store any other styles in `~/.config/vale/styles`.


Customizing Rules
--------------------------------------------------------------------------------

You can learn from existing [examples of Vale styles](https://vale.sh/explorer), borrowing rules as needed. Use the [Vale Studio](https://studio.vale.sh/) to validate your style definitions.

1. **Copy a rule file**\
   Copy the `.yml` file from its original directory into the `styles/Custom` folder.
2. **Disable the original rule**\
   In your `.vale.ini`, add the original rule to the ignore list (or set it to `false`).
3. **Delete the original file**\
   Remove the `.yml` file so that updates from the external source won't overwrite your custom changes.
4. **Commit changes**\
   Commit and push your modified rule to source control.

> **Goal:** Eventually merge and refine all borrowed sets until you rely solely on your custom style rules.


References
--------------------------------------------------------------------------------

  - [Vale Documentation](https://vale.sh/docs)
  - [Vale Boilerplate](https://github.com/errata-ai/vale-boilerplate)
  - [TestTheDocs/vale-styles](https://github.com/testthedocs/vale-styles)
  - [errata-ai/styles](https://github.com/errata-ai/styles)
