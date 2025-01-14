# Add SSH Keys to a server
With this you can connect to the server with ssh using a nickname and use VSCode Remote-SSH.

## Create and add the SSH key to a server

In a terminal run `ls ~/.ssh` to see if you already have ssh keys generated. Probably you have the key files `id_ed25519` and `id_ed25519.pub`, 
or maybe you don't have any keys or even the directory.

Run the following to create the new keys: 
~~~
ssh-keygen -t ed25519 -C "your_email@example.com" # Change the address to your e-mail (leave the quotes there)
# When it prompts for a key name you can just click Enter to use the default names, but if you already have
# the key files with the names above they might get overwritten.
# To use a new name for these specific key files (for example: id_ed25519_duke) type /home/username/.ssh/id_ed25519_duke
~~~

Run `ls ~/.ssh`  again to check that the files `id_ed25519_duke` and `id_ed25519_duke.pub` were created in `~/.ssh/`.  

Now run the following to copy your public key to the server:
~~~
ssh-copy-id -i ~/.ssh/id_ed25519_duke.pub user@ip.address.of.server # Change the name of the key and the address of the server.
# When prompted, give the password for the server
# If it is the first time connecting from that computer to the server, when prompted, type yes
~~~

Now you can connect to the server with only `ssh user@ip.address.of.server` without the need of passwords or two-factor authentication.

## Register your SSH key at Duke
Go to this page [https://idms-web-selfservice.oit.duke.edu/advanced](https://idms-web-selfservice.oit.duke.edu/advanced) 
- Enter your credentials.  
- In "Manage Your Public SSH Keys",  click  "See more about SSH keys".  
- Paste the content of your `.pub` key file into the gray box that appears.  
- Click "Add Key".  

## Set up a nickname for a server
Make a text file named `config` in the path `~/.ssh/` with the following content, changing the appropriate stuff 
and remove all the comments:
~~~
Host *
    AddKeysToAgent yes
    IdentityFile ~/.ssh/id_ed25519_duke #Put the name of your ssh-key files here (without the .pub extension)
    ForwardAgent yes

# This chunk is necessary to do a ProxyJump for Duke servers
Host dukeoit 
    HostName login.oit.duke.edu
    User yourNetID # Change to your netID

# This chunk will establish the nickname for the server.
Host nickName # Here put a nickname to the server
    HostName dcc-login.oit.duke.edu # Here put the correct domain/ip address of your server
    User usernameExample # Here put the username that you have in said server
    ProxyJump dukeoit

# Repeat the last chunk for as many servers as you want to include, changing the proper details.
~~~

Now you can log in to the server with `ssh nickName`
