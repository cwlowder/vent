# VENT command line tool
## Description
This tool helps organize projects(aka ventures) by:
* Allowing easy navigation to different ventures
* Mainting a list of command alias for easy execution

## Installation
To install simply copy the contents of the `vent` file into `/usr/local/bin/`

Also add the following alias to the end of your `~/.profile` file. This alias
allows for quick navigation to different ventures
```bash
# Vent
alias vego='{ dest=$(cat -); echo "Moving to venture: $dest"; cd $(vent go $dest) 
>> /dev/null 2>&1 || echo "Unknown venture: \"$dest\"";}<<<'
```

## Usage
### Quick Navigation
`vego <venture name>`
Example: 
```
user@Computer:.../Pictures$ vego schoolwork
Moving to venture: schoolwork
user@Computer:.../schoolwork$ 
```
### Initialize Venture
`vent init <optional name>`
Example: 
```
user@Computer:.../schoolwork$ vent init
user@Computer:.../schoolwork$
```
### Search Ventures
`vent find <optional query>`
Example: 
```
user@Computer:.../schoolwork$ vent find e
Venture Name 
------------
    projects
 minesweeper
       tests
user@Computer:.../schoolwork$
```
### List Commands
`vent list`
Example: 
```
user@Computer:.../schoolwork$ vent list 
    Name Command 
-----------------
    test echo 'lol'
user@Computer:.../schoolwork$  
```
### Run Commands
`vent run <command>`
Example: 
```
user@Computer:.../schoolwork$ vent run test 
lol
user@Computer:.../schoolwork$  
```
### Delete Command
`vent delete <command>`
Example: 
```
user@Computer:.../schoolwork$ vent delete test 
Successfully deleted test
user@Computer:.../schoolwork$  
```

## Help
Simply run `vent -h` for instructions