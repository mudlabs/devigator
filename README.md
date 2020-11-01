# Devigator
Devigator is a bash executable that makes it easy to inspect and jump around your local development directory.

## How to use it
1. Download the `devigator` plain text file into `/usr/local/bin`
    - `curl -fsSL https://raw.githubusercontent.com/mudlabs/devigator/master/devigator -o /usr/local/bin/devigator`
2. Change the `development` variable on line `55` to the path of your projects directory.
3. Optionally create an alias in `~/.bash_profile` that sources devigator for you.
    - If your running macOS Catalina and your default shell is `zsh` you can move all you aliases over to `~/.zshrc`. Or keep them in `.bash_profile` and just add this to the very top of your `.zshrc` file;<br/><br/>
    
    ```zsh
    if [ -f ~/.bash_profile ]; then
        . ~/.bash_profile;
    fi
    ```

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

I went with `alias dev=". devigator"` and will be using that alias for the rest of the document.


## Available Commands
These may change or grow over time, But for now they are;

* `dev` - cd into your development directory
* `dev ls` - list contents of development directory
* `dev help` - displays the available commands
* `dev your-project` - cd into that project
* `dev your-project ls` - list contents of project directory

## Example Output
Assuming you have an available directory named `dogs`.

```
~ $ dev dogs

 DEVIGATOR
 Changed Directory 
-------------------------------------------
 Now working out of: dogs 
 Git enabled: true
 Working branch: bank_blueprints
-------------------------------------------
 Last Commit                           
-------------------------------------------
 Committer: Freddy Newandyke
 Commit Date: Fri Jul 30 08:32:45 1996 +1100
 Updated details on robbery location and crew.
 May have collected some background on Mr White,
 see crew.json for more.
-------------------------------------------
 Repository Status                           
-------------------------------------------
 M layout.html
 M loose_ends/crew.json
 ?? weapons.yml
-------------------------------------------

bandit $
```


