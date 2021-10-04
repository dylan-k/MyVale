

# MyVale

My collection of style-guide rules to use with Vale while writing.

## Installation (Read All the Way Through)

- [install `vale`](https://docs.errata.ai/vale/install) and confirm via `vale -v`
- do `cd ~/.config/` 
- clone this repo to become `~/.config/vale/` directory
- some styles are here as git submodules to keep them update, so:
  - `git submodule update --init --recursive` to initialize the submodules
  - `git pull --recurse-submodules` any time to update submodules
- hardlink the config file from the git repository folder to its required location. The hardlink ensures version-control for the file, while keeping it for Vale to use at the default location. (alternately: `vale --config='some/file/path/.vale.ini')
  - mac/linux: `ln ~/.config/vale/.vale.ini ~/.vale.ini`
  - windows: `New-Item -ItemType HardLink -Path "C:\Users\USERNAME\.vale.ini" -Target "C:\Users\USERNAME\.config\vale\.vale.ini"`
- note the value of `stylespath` in the `vale.ini` file and revise as needed

## Configuration

- alias in `~/.bash_aliases` to edit Vale settings with Sublime Text:  
`alias valestyles="cd ~/.config/vale/ && subl ."`


### Setup for Visual Studio Code

- Install the Vale extension from https://marketplace.visualstudio.com/items?itemName=errata-ai.vale-server
- working windows settings:
```
  "vale.server.serverURL": "",
  "vale.core.useCLI": true,
  "vale.valeCLI.path": "vale",
  "vale.server.lintContext": -1,
  "vale.server.provideFixes": false,
  "vale.valeCLI.config": "C:\\Users\\dylan\\.vale.ini",
  "vale.valeCLI.minAlertLevel": "suggestion",
```
- Exclude the settings from VSCode's settings sync, because settings differ among environments.

### Setup for Sublime Text

To use Vale with the Sublime Text editor, install my fork of [SublimeLinter-contrib-vale](https://github.com/dylan-k/SublimeLinter-contrib-vale).

## Updates

Most of these styles come from other sources. Review each style's README file for instructions. The typical method: download the style's GitHub repository and copy its styles directory into ``styles``.

## Changes

If you change a style's .yml file, turn the rule off in `vale.ini` file and copy the .yml file to `styles/Custom`. Otherwise, you run the risk of replacing a deleted rule during an update. The goal is to merge and winnow the styles until the custom style is the only one.

Don't replace any styles you've already removed. After updates, review the ignored style list and delete related files.

## Testing

This is useful for testing a style rule https://vale-studio.errata.ai/

## Sources

- https://github.com/testthedocs/vale-styles
- https://github.com/errata-ai/styles

Tasks:


- [ ] move these tasks to GitHub issues
- [ ] remove redundant rules that occur across styles
- [ ] remove contradictory rules
- [ ] remove unwanted rules
- [ ] combine into one custom style
- [ ] make a rule for spelling exceptions
- [ ] test readability rules
- [ ] hyphen rules
- [ ] exclude some rules at start of sentences
- [ ] upgrade American-spelling.yml to include the ones I do...

__
dk
