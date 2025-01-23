# Setup guide for VSCode recommended extensions and VSCode Remote-SSH

## Install VSCode

Go to [https://code.visualstudio.com/](https://code.visualstudio.com/) and choose the appropriate installer for your platform.

## Install VSCode Remote-SSH extensions

Before trying to connect to the server with VSCode, make sure that you can do it in a terminal.  

Go to the Extensions tab in the left panel icons (or Ctrl + Shift + X) and search for and install Remote-SSH. 

![image](https://github.com/user-attachments/assets/8fbf78b1-4a63-4394-a4c3-6da40ec16565)

![image](https://github.com/user-attachments/assets/5a27453a-0b36-4c1e-a281-b2400700046f)

This will automatically install these other extensions: Remote Explorer and Remote-SHH: Editing Configuration Files.  

In the left panel, you can connect to a new remote server using the Remote Explorer icon. If you followed the steps in [ssh_keys.md](https://github.com/magwenelab/CodeStarterKit/blob/main/ssh_keys.md) 
you will see the alias of your server as an option, select it and the connection should be automatic.  
![image](https://github.com/user-attachments/assets/218ff023-316e-4252-829a-e44af1c5fc3c)

![image](https://github.com/user-attachments/assets/d5cf0863-0f43-4677-9a58-4a8f837b6c46)

If you didn't set up an alias you can use the full ssh command and follow the prompts to connect and add your password.  
![image](https://github.com/user-attachments/assets/f68fc0c7-f23c-4d2f-af87-5cbd5c4519b6)

You can see that you have an activer remote connection in the lower left corner. 
![image](https://github.com/user-attachments/assets/b0eba5e3-8754-4bad-99c5-290da6c98f92)


If you are using Windows, you need to have an SSH Client, if you use Git Bash, it comes with an SSH client. After installing the Remotes-SSH extensions, 
go to Settings and search for "Remotes SSH Path" and add the path to your SSH Client, for example `C:\Program Files\Git\usr\bin\ssh.exe`.  

## Install other VSCode extensions

If you need the extensions on both the local machine and the remote server, you will need to install them twice. 
You need to have the remote connection active to install them remotely.    
You can search for them in the Extensions Explorer in the left panel.
![image](https://github.com/user-attachments/assets/a3d2e118-602b-44b3-b6e2-8e83db2c8481)

I recommend the following basic extensions that need no or little configuration:  

* Rainbow CSV
* Edit CSV (Not necessary if you will use Data Wrangler, which is better. See Python extensions below)  
* Preview  
* SVG Previewer

If something doesn't work as expected try opening the extension settings and toggle the parameters.  
In the bottom left corner, you can find the gear icon and click Settings. In Settings open the list of Extensions to the left 
or use the search bar.

![image](https://github.com/user-attachments/assets/7bc1c20f-de7c-4eda-816c-dd2ec7435ba4)


## Setup Python extensions

To use the Python and Jupyter Notebook extensions you need to have some Python packages installed (ipykernel and pip). 
I recommend making a Conda environment with all the Python packages you usually need, including the ones mentioned. 
For example, you can use this `yaml` file to create an environment. First make the file `python_env.yaml` 
with the content shown below and the run `conda env create --file python_env.yaml`:
```
name: python_env
channels:
  - conda-forge
  - bioconda
  - defaults
dependencies:
  - ipykernel
  - pandas
  - scipy
  - numpy
  - matplotlib
  - pip
```

With that environment installed go ahead and install the following extensions:
* Python  
* Jupyter  
* Data Wrangler  
Some other extensions will be also installed automatically.

Now create a notebook file `python_test.ipynb`. When you open it, it should automatically open a notebook view.
In the upper right corner, there will be an icon to select a Kernel. Click on it and select the `python_env` you created 
Make a basic code to check that all functionalities are working. Create a dataframe and click on the Data Wrangler icon 
that says View data. Follow the prompts to allow permissions. 
Data Wrangler will provide an interface to work with tables, which can be dataframes inside a notebook, or table files. 
When you open a table file from the Explorer, click on the Data Wrangler icon in the upper right corner. It will ask you for a
Python interpreter, you should use the same Python environment as before. 

## Setup R extension

In the terminal of VSCode open R.  
Install languageserver with `install.packages("languageserver")`.  
Install httpgd with `install.packages("httpgd")`.   
In Settings search for R > Plot: Use Httpgd and enable it.  
If you are not using an R installation that is available in the PATH by default (e.g inside a Conda environment), go to 
Settings and add te path to your R installation to the R > Rterm:<OS> setting.

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


