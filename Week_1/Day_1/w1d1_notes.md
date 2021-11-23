# W1D1-01 Notes
## This Week: Focus on Tech Fundamentals
## Today: Fundamentals of Data Science

### Virtual Environments

From the __[Virtual Environments walkthrough](https://data.compass.lighthouselabs.ca/activities/32)__ tutorial __[How to add your Conda environment to your jupyter notebook in just 4 steps](https://medium.com/@nrk25693/how-to-add-your-conda-environment-to-your-jupyter-notebook-in-just-4-steps-abeab8b8d084)__
​
On step 3, the command `python -m ipykernel install --user --name=test_env` raised error `ModuleNotFoundError: No module named 'ipython_genutils'`
​
The error was resolved via `conda install ipython_genutils`

***
From Prep Work: __[Install Anaconda walkthrough](https://data.compass.lighthouselabs.ca/activities/215)__
`conda activate base_env` comes right before `conda install ...` which places jupyter lab and the other installed packages in base_env, rather than the root, making these packages unavailable from the other environments wihtout a separate install.
​
I want to talk to a mentor about this. I installed Jupyter Lab in the root.

### Bash reading
From __[Introduction to Bash](https://stackabuse.com/introduction-to-bash/)__
The tutorial shows that Homebrew installs the latest version of BASH into `/usr/local/bin/bash`.
On my machine, Homebrew installed BASH 5.1.12 into `/opt/homebrew/bin/bash`.
Following the rest of the tutorial worked fine.
​
The command `which -a bash` shows where each version of BASH is installed on a machine. Source: __[Upgrading Bash on macOS](https://itnext.io/upgrading-bash-on-macos-7138bd1066ba)__

#### TODO:
Create Zsh alias called bash5 to exectue `/opt/homebrew/bin/bash`.
I have a weird thing about not wanting to switch my default shell to bash.
... I guess it's no big deal to switch it back after the course.
But why not just use Zsh?
[ ]:
