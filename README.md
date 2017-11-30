# Devigator
Devigator is a bash executable that makes it easy to inspect and jump around your local development directory.

## How to use it
1. Download the `devigator` plain text file into `/usr/local/bin`
2. Change the `development` variable on line `54` to the path of your directory.
3. Optionally create an alias in `~/.bash_profile` that sources devigator for you. 

## Why use it?
Because having to type out stuff like 
```
cd my/development/directory/subdirectory
git rev-parse --abbrev-ref HEAD
git diff --name-status
```
whenevery you move from project to project, or just want a quick overview is too much.



## Source it!
Devigator must be sourced. But it's amazing how much extra effort typing `. devigator` or `source devigator` feels like. So create an alias for it in `~/.bash_profile`.

I went with
```
alias dev=". devigator"
```

## Available Commands
These may change or grow over time, But for now they are;

* `. devigator` - cd into your development directory
* `. devigator ls` - display files/folder in root of development directory
* `. devigatior help` - displays the available commands
* `. devigator [project]` - cd into that project
* `. devigator [project] ls` - display files/folders in root of project directory

_Remember: The `. devigator` bit may be different if you created an alias for it._

## Example Output
Assuming you have an available directory named `bandit`.

```
~ $ . devigator bandit

 DEVIGATOR
 Changed Directory 
-----------------------------------------
 Now working out of: bandit 
-----------------------------------------
 Git enabled: true
-----------------------------------------
 Working branch: train_blueprints
-----------------------------------------
 Repository Status                           
-----------------------------------------
 M layout.html
 M loose_ends/crew.json
 ?? weapons.yml
-----------------------------------------

bandit $
```


