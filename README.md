

# MyVale

My collection of style-guide rules to use with Vale while writing.

## Installation (Read All the Way Through)

- make sure `vale` is installed i.e. `choco install vale`
- cd to `~/.config/` 
- clone this repo to become `~/.config/vale/` directory
- hardlink the config file from this working directory to its required location.  
  - mac/linux: `ln ~/.config/vale/.vale.ini ~/.vale.ini`
  - windows: `New-Item -ItemType HardLink -Path "C:\Users\USERNAME\.vale.ini" -Target "C:\Users\USERNAME\.config\vale\.vale.ini"`
- note the stylespath in that file, revise as needed

## Setup for Visual Studio Code

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

## Configuration

- alias in `~/.bash_aliases` to edit Vale settings with Sublime Text:  
`alias valestyles="cd ~/.config/vale/ && subl ."`
- To use these style rules within the Sublime Text editor, install my fork of [SublimeLinter-contrib-vale](https://github.com/dylan-k/SublimeLinter-contrib-vale).

## Changes

Rather than to change/edit a .yml file, disable it in your vale.ini file. If you're making a change, copy it to `styles/Custom` with the change. Otherwise, you run the risk of replacing a deleted rule during an update. My plan is to eventually have only the Custom style.

Be careful not to replace any styles
- cd to `~/.config/`  you've already removed.

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
- [x] add readability rules
- [x] check for headings in title case
- [x] add a good example doc for testing
- [ ] hyphen rules
- [ ] rules excluding some rules at start of sentence

__
dk
