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

#### TODO: Complete
Create Zsh alias called bash5 to exectue `/opt/homebrew/bin/bash`.
I have a weird thing about not wanting to switch my default shell to bash.
... I guess it's no big deal to switch it back after the course.
But why not just use Zsh?
__Solution__: From .zshrc, aliases should be set in ZSH_CUSTOM. I had to create the file `aliases.zsh`. source: [github](https://github.com/ohmyzsh/ohmyzsh/issues/4865)

### Bash Assignment
[bash_exercise.txt](../../../../data_bootcamp/w1/d1-day_1/bash_exercise.txt)
Q6
Assigning command outputs to varaibles [StackOverflow](https://stackoverflow.com/questions/4651437/how-do-i-set-a-variable-to-the-output-of-a-command-in-bash)

Arithmatic comparison [StackOverflow](https://stackoverflow.com/questions/18668556/how-can-i-compare-numbers-in-bash)

Q3 replacing the delimiter. Movie titles have commas, which get overwritten by the simple sed command.

Try:
1. move all quoted movie titles to a new file
    `grep -o '".*"' cast-2.csv > test.csv`
2. Replace quoted movie titles with a distinct string
    `sed 's/".*"/XXXXX/g' cast-2.csv > no_quotes.csv`
3. Change delimiter
    `sed 's/,/;/g' no_quotes.csv > no_quotes_new_delim.csv`
4. Replace distinct strings with quoted movie titles
    `sed "s/XXXXX/$(cat test.csv)/" no_quotes_new_delim.csv > cast_final.csv` # Not working [StackExchange](https://askubuntu.com/questions/811881/how-to-insert-the-contents-of-one-file-to-an-exact-place-in-another-file)