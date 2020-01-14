# MyVale

My collection of style-guide rules to use with Vale while writing. I have two goals for this project. First, to make it easy to have my style guide with me and up-to-date on my laptop, at work, or at home. Second, my style guide is standing on the shoulders of giants, but I want to migrate my borrowed style rules into one collection. To begin with, I'm using a set of styles, but it results in contradictions and redundancies. 

## Installation

- clone this repo into your `~/.config/vale/` directory
- update styles to their latest with `git pull --recurse-submodules`
- hardlink the config file from this working directory to its required location.  
`ln ~/.config/vale/.vale.ini ~/.vale.ini`
- note the stylespath in that file, revise as needed
- To use these style rules within the Sublime Text editor, install my fork of [SublimeValeLinter](https://github.com/dylan-k/SublimeValeLinter).

## Extra Settings

alias in `~/.bash_aliases` to edit Vale settings with Sublime Text:  
`alias valestyles="cd ~/.config/vale/ && subl ."`

## Want More Styles?

- https://github.com/testthedocs/vale-styles
- https://github.com/errata-ai/styles

TODO:

- [ ] remove redundant rules that occur across styles
- [ ] remove contradictory rules, keeping what's preferred. 
- [x] add readability rules
- [ ] combine into one custom style
- [x] check for headings in title case
- [x] add a good example doc for testing

__
dk
