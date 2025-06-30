<h1>
  <span class="headline">Setting Up a Virtual Environment with `venv`</span>
  <span class="subhead">Concepts</span>
</h1>

## What is a `Virtual Environment` and why are we doing this?

* What is a virtual environment?
    * A virtual environment is an isolated workspace where you can install Python libraries and dependencies without affecting other installations or projects.

    * Think of as its own sandbox, each project gets its own space to run specific versions of Python libraries.

* Why do we want to use them?
    * Helps with dependencies! Different libraries are getting updated at different times. Sometimes an updated version of a library will not be compatible with an older version of a library it used to use. By using a virtual environment, you can avoid these kinds of issues.
    * Reproducibility! By sharing the libraries and their versions for your projects, it can make your projects reproducible and easier to collaborate.
    * Organization! It is a nicer, cleaner way of organizing your projects

---

# How can you set up your machine so you can run a virtual environment?
The instructions below talk you through a number of steps:

- Configure your machine to be able to use virtual environments
     - Windows people make sure you have GitBash
     - Download Python (even if you have it already)
     - Create a dedicated folder in your root directory for all your environments
- Create a Virtual Environment
- Activate a Virtual Environment
- Install Dependencies from `requirements.txt`
- Deactivate a Virtual Environment
- Reactivate a Virtual Environment
- See what libraries are installed in the environment
- Export an environment as a `requirements.txt` file

---

## Configure your machine to be able to use virtual environments

### Windows people make sure you have GitBash

1. Install gitbash (32-bit or 64-bit depending on your version of windows): [video help](https://www.youtube.com/watch?v=rWboGsc6CqI) and access the install guide [here](https://git-scm.com/downloads/win).

### Download Python (even if you have it already)

In order to create our environment using ```venv``` we need to install python.

2. Open your terminal/ Git Bash fresh, make sure you aren't in an environment (you should not be in one if you have never made any before), and the next step is to install python so we can make a DS environment.  If you are on a mac you should see ```(base)``` at the beginning of your termianl prompt.
3. Go to this link: [3.11 for Windows](https://www.python.org/ftp/python/3.11.9/python-3.11.9-amd64.exe) or [3.11 for Mac](https://www.python.org/ftp/python/3.11.9/python-3.11.9-macos11.pkg) it will open a 3.11 download (do it directly through this link or it can take 15-40 minutes to download Python through terminal). Python 3.9 is too outdated for some of the required libraries, while versions 3.12 and above are too recent for others and that is why we use pyhon 3.11. Please use the exact link provided for Python 3.11.9.
4. **IMPORTANT!** - Be sure to check the 'add python to PATH' box as well as leaving the pre checked box for admin permissions.  This will come up for Windows users, it should not pop up for mac users.  This ensures python 3.11 will be used in the environment.
5. If asked when installing allow it to modify your system (select 'yes' when prompted).  
6. Once installed, open a new terminal/Git Bash session and type ```python -V```, you should see the output of the python version you just installed.

Now we have Python and can continue to create our Data Science environment!


### Create a dedicated folder in your root directory for all your environments

It's a good idea to have one folder containing all your environments so they are easy to find and use.

7. Return to your terminal and type:
```bash
cd 
```
Hit enter. (this is important to return your to home directory which looks like ```~``` )

8. Type:
```bash
mkdir virtual
```
and hit enter.

9. Type:
```bash
cd virtual
```
and hit enter.

Now we are inside the directory where we want to make the environment.  It is important that we know where it is so we can activate it from anywhere in our file structure.


## Create a Virtual Environment

10. Since we are in our dedicated directory for environments `virtual`, and have downloaded python 3.11, paste:

```bash
python3.11 -m venv <myenv>
```

in terminal (replace `<myenv>` with your preferred environment name) and hit enter.

---

## Activate a Virtual Environment

11. Then, for **Mac/Linux (bash/zsh)** paste:
```bash
source <myenv>/bin/activate
```
and for **Windows (cmd or PowerShell)** paste:
```powershell
source <myenv>/Scripts/activate
```
in terminal/ Git Bash (replacing `<myenv>` with your preferred environment name) and hit enter. Once activated, you should see `(<myenv>)` in your terminal prompt.

12. Then, for **Mac/Linux (bash/zsh)** paste:
```bash
pip install --upgrade pip
```
and for **Windows (cmd or PowerShell)** paste:
```powershell
python -m pip install --upgrade pip
```
in terminal/ Git Bash and hit enter.

---

## Install Dependencies from `requirements.txt`
Now we need to install a group of core Data Science packages, and these are collected in the `requirements.txt` file in this repo.  Download the repo to get the `requirements.txt` file only and _move it to your `~virtual/<myenv>` directory_.

13. We need to move into our environment, so type:
```bash
cd <myenv>
```
and hit enter.

14. Ensure your virtual environment is activated, then install dependencies with typing:

```bash
pip install -r requirements.txt
```

And hitting enter.  This will install all packages listed in the `requirements.txt` file.

15. We need to finish setting up `jupyterlab`, so type:
```bash
pip install jupyterlab
```
and then 
```bash
jupyter lab build
```
Hitting enter for each line.  

---

## Deactivate a Virtual Environment
To exit the virtual environment, simply run:

```bash
deactivate
```

This will return you to the system’s default Python environment.

---

## Reactivate a Virtual Environment
If you need to use the virtual environment again, navigate to your project directory and run the activation command for your OS (from Step 11).

---

Now you're all set with a Python virtual environment using `venv`! 🚀
- It is a good idea to test run `jupyter lab` since it is what we'll use to edit code, and you can do that by typing:
```bash
jupyter lab
```  
to make sure it launches.

No matter where you are in your terminal, for **Mac/Linux (bash/zsh)** running:
```bash
source ~/virtual/<myenv>/bin/activate
```
and for **Windows (cmd or PowerShell)** running:

```bash
source ~/virtual/<myenv>/Scripts/activate
```

will now activate your virtual environment.
This should work on different computers i.e. desktop PCs running Ubuntu on Windows. 

## See what libraries are installed in the environment

Run this command:

```bash
pip list
```

And you should see the output of the libraries and their versions

---

## Export an environment as a `requirements.txt` file

Typically you'll see a `requirements.txt` file. This will list the libraries and their versions used in an environment. 

You can create a text file containing all the libraries you are using in your current virtual environment with this command:

```bash
pip freeze > requirements.txt
```

This will create a `requirements.txt` text file in your current directory.

--- 

Since we're suggesting you create all your environments in your root directory, you can see which ones are there by running the following in your terminal/git bash

```bash
ls ~/virtual/
```

And you'll see all the virtual environments that you've created.


That's it!  Now you can create and use virtual environments on your machine.
