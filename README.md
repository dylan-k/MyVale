

# MyVale

My collection of style-guide rules to use with Vale while writing.

## Installation (Read All the Way Through)

- [install `vale`](https://docs.errata.ai/vale/install) and confirm via `vale -v`
- do `cd ~/.config/`
- clone this repo to `~/.config/vale/` `git clone git@github.com:dylan-k/MyVale.git vale`
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
- Exclude the settings from VSCode's settings sync, because settings differ across environments.

## Updates

Most of these styles come from other sources. Review each style's README file for instructions. The typical method: download the style's GitHub repository and copy its styles directory into ``styles``.

## Changes

To change a rule:
- copy the rule's `/yml` file into the `custom` directory
- modify the rule as needed
- add the original rule to the ignores list in .vale.ini
- delete the original rule file
- commit/push to git repo

If you change a style's .yml file, turn the rule off in `vale.ini` file and copy the .yml file to `styles/Custom`. Otherwise, you run the risk of replacing a deleted rule during an update.

My goal is to merge and winnow the borrowed style sets until my custom set is the only one.



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
