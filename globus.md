# Globus Connect Personal

## Setup Globus Connect Personal

Go to https://www.globus.org/globus-connect-personal

Click on your appropriate installation and follow the instructions there:
 <img width="854" height="839" alt="image" src="https://github.com/user-attachments/assets/cfdad50c-4104-45c9-a757-00d183653dda" />

For Linux, these are the steps for an installation and setup that only need a terminal and an internet browser.
```
wget https://downloads.globus.org/globus-connect-personal/linux/stable/globusconnectpersonal-latest.tgz
tar xzf globusconnectpersonal-latest.tgz
cd globusconnectpersonal-3.2.7/
./globusconnectpersonal -setup -no-gui
```
<img width="1009" height="474" alt="Screenshot from 2025-08-28 15-04-43" src="https://github.com/user-attachments/assets/cec981b1-eae3-42e0-ab22-5c94df9610e9" />
Go to that link and use the organizational login, which will ask for your NetID. 

<img width="953" height="697" alt="image" src="https://github.com/user-attachments/assets/96b28cfb-5502-4d25-883f-a2b11a7057b2" />

Follow the instructions and enter the provided code in the terminal. 

Run `./globusconnectpersonal -start` in the terminal to start your collection. This is needed for setup right now, and later you will need to do this whenever you transfer files. 
For now, leave it running in the terminal.

To set up the collection detail,s go to https://www.globus.org/globus-connect-personal and log in.  
Click on Collections in the left menu.  
<img width="94" height="254" alt="image" src="https://github.com/user-attachments/assets/b82daf6c-fdfa-49cc-975c-1263a9e1e919" />

Then go to "Administered by you"  
<img width="1540" height="148" alt="image" src="https://github.com/user-attachments/assets/cd48aa07-bce0-4f36-83bd-7a95d98aec28" />  

Click on the new collection that appears in green  
<img width="1535" height="71" alt="image" src="https://github.com/user-attachments/assets/7886cc80-dbea-470d-b215-f26cc18a6f28" />

Click on Edit Attributes to change the name
<img width="389" height="67" alt="image" src="https://github.com/user-attachments/assets/23770772-3bad-404b-b314-5660b7214d94" />

Now, in the collections administered by you, it will look like this  
<img width="321" height="75" alt="image" src="https://github.com/user-attachments/assets/82db7181-a9ca-479e-80a4-d6413801bbb5" />  

Go back to your terminal and do `Ctrl+ C` to stop the collection.

To have easy terminal access to globusconnectpersonal in your terminal, add the path to your `.bashrc` file. 
```
cd
nano .bashrc
```
At the end of the file, add these lines:
```
# Add globusconnectpersonal to path:
export PATH="$PATH:~/globusconnectpersonal-3.2.7/"
```
Restart your terminal to make the change effective.

## Transfer files between your local collection and the Duke DCC

In your terminal, start the collection by running `globusconnectpersonal -start`. This will allow transfer to and from your home directory.  
To use a different directory, use `globusconnectpersonal -start -restrict-paths /mypath/`.  

Go to https://www.globus.org/globus-connect-personal and log in with your organization.  

Go to the File Manager in the left menu  
<img width="1770" height="520" alt="image" src="https://github.com/user-attachments/assets/6663843b-3fb5-405d-9d16-000bc15e9f8b" />  

In the left collection, click on search.    
That will take you to your collections.   
Select your local collection.  
<img width="1744" height="563" alt="image" src="https://github.com/user-attachments/assets/07bb2997-059c-4bc3-9b92-652ea2fc49b2" />  

On the right side, click on search.  
Type Duke DCC to find the Transfer Node and select it.  
<img width="1770" height="311" alt="image" src="https://github.com/user-attachments/assets/90a98381-618c-412b-b267-d13a9e318548" />  

On the receiver side, navigate to the destination folder.   
On the sender side navigate to and select the files to transfer and then click Start on the sender side.  

When the transfer is finished, go back to the terminal and stop the connection.  
To do long transfers is recommended to run the `globusconnectpersonal -start` inside a Tmux session.  


