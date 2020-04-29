

# MyVale

My collection of style-guide rules to use with Vale while writing. I have two goals for this project. First, to make it easy to have my style guide with me and up-to-date on my laptop, at work, or at home. Second, my style guide is standing on the shoulders of giants, but I want to migrate my borrowed style rules into one collection. To begin with, I'm using a set of styles, but it results in contradictions and redundancies. 

## Installation

- clone this repo into your `~/.config/vale/` directory
- hardlink the config file from this working directory to its required location.  
`ln ~/.config/vale/.vale.ini ~/.vale.ini`
- note the stylespath in that file, revise as needed
- To use these style rules within the Sublime Text editor, install my fork of [SublimeLinter-contrib-vale](https://github.com/dylan-k/SublimeLinter-contrib-vale).

## Configuration

- update submodule styles. `cd` to each and do `git pull origin master`

- alias in `~/.bash_aliases` to edit Vale settings with Sublime Text:  
`alias valestyles="cd ~/.config/vale/ && subl ."`

## Changes

Rather than to change/edit a .yml file, disable it in your vale.ini file. If you're making a change, copy it to `styles/Custom` with the change. Otherwise, you run the risk of replacing a deleted rule during an update. My plan is to eventually have only the Custom style.

Be careful not to replace any styles you've already removed.

## Sources

- https://github.com/testthedocs/vale-styles
- https://github.com/errata-ai/styles

Tasks:


- [ ] move these tasks to GitHub issues
- [ ] remove redundant rules that occur across styles
- [ ] remove contradictory rules, keeping what's preferred. 
- [ ] combine into one custom style
- [ ] make a rule for spelling exceptions
- [ ] test readability rules
- [x] add readability rules
- [x] check for headings in title case
- [x] add a good example doc for testing
- [ ] hyphen rules
- [ ] rules for words that should not start a sentence

__
dk
