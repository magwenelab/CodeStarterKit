# Setup guide for VSCode recommended extensions and VSCode Remote-SSH

## Install VSCode

Go to [https://code.visualstudio.com/](https://code.visualstudio.com/) and choose the appropriate installer for your platform.

## Install VSCode Remote-SSH extensions

Before trying to connect to the server with VSCode, make sure that you can do it in a terminal.  

Go to the Extensions tab in the left panel icons (or Ctrl + Shift + X) and search for and install Remote-SSH. 
This will automatically install these other extensions: Remote Explorer and Remote-SHH: Editing Configuration Files.
In the left panel, you can connect to a new remote server using the Remote Explorer icon. If you followed the steps in [ssh_keys.md](https://github.com/magwenelab/CodeStarterKit/blob/main/ssh_keys.md) 
you will see the alias of your server as an option, select it and the connection should be automatic.  
If you didn't set up an alias you can use the full ssh command and follow the prompts to connect and add your password.  

If you are using Windows, you need to have an SSH Client, if you use Git Bash, it comes with an SSH client. After installing the Remotes-SSH extensions, 
go to Settings and search for "Remotes SSH Path" and add the path to your SSH Client, for example `C:\Program Files\Git\usr\bin\ssh.exe`.  


# In development &darr;
## Install other VSCode extensions

If you need the extensions on both the local machine and the remote server, you will need to install them twice. 
You need to have the remote connection active to install them remotely.    
You can search for them in the Extensions Explorer in the left panel.

I recommend the following basic extensions that need no or little configuration:  

* Rainbow CSV
* Edit CSV (Not necessary if you will use Data Wrangler, which is better. See Python extensions below)  
* Preview  
* SVG Previewer

If something doesn't work as expected try opening the extension settings and toggle the parameters.  
In the bottom left corner, you can find the gear icon and click Settings. In Settings open the list of Extensions to the left 
or use the search bar.


## Setup Python extensions

If you 
* Python (Python Debugger will be installed automatically)
* Jupyter (
* Data Wrangler


## Setup R extension

In the terminal of VSCode open R.  
Install languageserver with `install.packages("languageserver")`.  
Install httpgd with `install.packages("httpgd")`.   
In Settings search for R > Plot: Use Httpgd and enable it.  

Now you can open any R script, put your cursor in the first line, and click Ctrl + Enter, 
this will automatically open the R terminal and activate the R Workspace in the left panel.  

Try running `plot(cars)` to check if the plots are being shown well in the interactive R plot panel.  


## Setup GitHub account and Copilot

To use Git source control and GitHub Copilot you need to have a GitHub account, and in your account, you need to get access to Copilot.  
GitHub Education will give you free access to Copilot if you are part of an educational institution. To obtain GitHub Education go to 
[https://education.github.com/discount_requests/application](https://education.github.com/discount_requests/application), log in to your GitHub account , 
and submit an application. For this, you will need proof of enrollment in an institution. If you are staff you can apply as a Teacher and use your job offer letter to apply. 
If you are a Duke student you can use an Enrollment Verification letter found in your Duke Hub. 
After your application is approved you can follow the next steps.  

In the Extensions Explorer install GitHub Copilot and GitHub Copilot Chat. Follow the prompts to add your GitHub account credentials. 
In the lower right corner, the Copilot logo will appear, you can click on it to check the status of Copilot and open the Copilot Chat.  


