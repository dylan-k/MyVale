



MyVale
================================================================================

A personal collection of style-guide rules for use with the [Vale prose linter](https://vale.sh/docs/install).

Use *MyVale* to check and enforce writing conventions across your documents. This repository contains custom and borrowed rules, along with a configuration file that Vale uses by default. It serves as an example of how to work with Vale using personalized style rules.

With this config, Vale is used alongside LTeX+:
  - Prefer Vale to check prose against a style guide.
  - Prefer LTeX+ to check grammar and spelling.


Prerequisites
--------------------------------------------------------------------------------

  - [Vale](https://vale.sh/docs/install)
    : install via Scoop or another package manager
    : confirm install via `vale -v`

  - [Vale extension for VSCode](https://marketplace.visualstudio.com/items?itemName=ChrisChinchilla.vale-vscode)
    : Shows writing and linting suggestions while editing.


Get Started
--------------------------------------------------------------------------------

Clone this repo into Vale's global configuration directory. Vale checks a default location per OS:

| OS      | Global config directory                        |
|---------|------------------------------------------------|
| Windows | `%LOCALAPPDATA%\vale\`                         |
| macOS   | `~/Library/Application Support/vale/`          |
| Linux   | `$XDG_CONFIG_HOME/vale/` (usually `~/.config/vale/`) |

Run `vale ls-dirs` to confirm the path on your system, then clone:

```bash
git clone git@github.com:dylan-k/MyVale.git "$(vale ls-dirs | head -1)"
```

Or manually:



```bashexample for Linux
================================================================================
git clone git@github.com:dylan-k/MyVale.git ~/.config/vale
```

Since `.vale.ini` lives inside the repo and Vale already looks in this directory, no symlinks are needed.

Finally, sync packages:

```
vale sync
```


Configs
--------------------------------------------------------------------------------

### Custom alias (optional)

You can add an alias to quickly edit Vale settings:

```bash
alias valestyles="cd ~/.config/vale && code ."
```

Adjust this to match your preferred editor, operating system, and so on.

### Using MyVale with VS Code

To integrate Vale into Visual Studio Code, install the [Vale extension](https://marketplace.visualstudio.com/items?itemName=errata-ai.vale-server) and configure it to use your MyVale styles. In VS Code settings, set the Vale configuration path to point to your .vale.ini file, which is located in the MyVale repository you cloned. This allows VS Code to check your writing against the custom rules defined in MyVale while you edit your documents.

**Tip:** Exclude your Vale settings from VS Code's settings sync if you plan to use different paths or configurations on different machines.


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


References
--------------------------------------------------------------------------------

  - [Vale Documentation](https://vale.sh/docs)
  - [Vale Boilerplate](https://github.com/errata-ai/vale-boilerplate)
  - [TestTheDocs/vale-styles](https://github.com/testthedocs/vale-styles)
  - [errata-ai/styles](https://github.com/errata-ai/styles)
