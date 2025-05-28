# CodeStarterKit

A collection of instructions to configure your computer to make your programming life easier. Aimed at new members of the Magwene lab.

## Add SSH keys to your servers

Follow the instructions in [ssh_keys.md](https://github.com/magwenelab/CodeStarterKit/blob/main/ssh_keys.md) to 
create and add SSH keys to your remote servers and allow VSCode to connect to the server. Follow this instructions 
befor setting up VSCode Remote-SSH.

## Set up VSCode

Follow the instructions in [vscode_setup.md](https://github.com/magwenelab/CodeStarterKit/blob/main/vscode_setup.md) to 
add and configure extensions in VSCode, including R, GitHub, GitHub Copilot and Remote-SSH.

## Transfer files with Globus

PENDING

## Using Tmux

Tmux allows you to run commands in a terminal session that you can open (attach) and close (detach) at will. 
With this, you avoid the risk of your program failing if your remote connection to your server stops, 
and the need to wait with the terminal open before turning off your computer.  

https://github.com/tmux/tmux/wiki  
https://tmuxcheatsheet.com/

| Command | Description |
|---------|-------------|
| tmux ls | List sessions |
| tmux new -s mysession | Create a new session with a name |
| tmux attach -t mysession | Open an existing session |
| `Ctrl + b` `d` (Ctrl and b at the same time, release them and then d) | Detach (close) a session |
| tmux kill-ses -t mysession | Kill a session while being detached |




## Efficiency tips and tricks

### Enable the use of up and down arrows to search your history of related commands

In your user's home directory add a file named `.inputrc` with the following lines:
```
"\e[A": history-search-backward
"\e[B": history-search-forward
```
Now, when you start typing a command and use the arrows, you will see the commands you have used that start with the same string.

## Literature

* Barrett, D. Efficient Linux at the Command Line.
* Aho, Kernighan, Weinberger. The AWK Programming Language.
* Allesina, Wilmes. Computing Skills for Biologists.

Available at Duke's online library: https://library.duke.edu/

