# CodeStarterKit
Collection of instructions to configure your computer to make programming projects.

## Add SSH keys to your servers

Follow the instructions in [ssh_keys.md](https://github.com/magwenelab/CodeStarterKit/blob/main/ssh_keys.md) to 
create and add SSH keys to your remote servers and allow VSCode to connect to the server. Follow this instructions 
befor setting up VSCode Remote-SSH.

## Set up VSCode

Follow the instructions in [vscode_setup.md](https://github.com/magwenelab/CodeStarterKit/blob/main/vscode_setup.md) to 
add and configure extensions in VSCode, including R, GitHub, GitHub Copilot and Remote-SSH.


## Efficiency tips and tricks

### Enable the use of up and down arrows to search your history of related commands

In your user's home directory add a file named `.inputrc` with the following lines:
```
"\e[A": history-search-backward
"\e[B": history-search-forward
```
Now, when you start typing a command and use the arrows, you will see the commands you have used that start with the same string.
