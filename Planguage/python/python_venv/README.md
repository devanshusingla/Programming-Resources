## Setting Virtual Environment in python

Create a project directory, change to it and follow follwing steps.

```
alias python=/path/to/python/executable  // example alias python=/usr/bin/python3.8
python -m venv .venv --without-pip
source venv/bin/activate
curl https://bootstrap.pypa.io/get-pip.py | python
deactivate
```

This will create a project with name as project-name and a virtual environment.

### How to use it.

Change into the project folder.

To start the virtual environment we have to type `. venv/bin/activate`. This will start the virtual environment and from now on any package installed using pip will remain isolated from global python installation.

To exit this mode type `deactivate` and it will stop virtual mode.

## Script for setting virtual environment.

### Installation

Add the following line in your ~/.bashrc.

```
PROMPT_COMMAND='if [[ "$venvrc" != "$PWD" && "$PWD" != "$HOME" && -e .venvrc ]]; then venvrc=\"$PWD\"; . .venvrc; fi'
```

Add script [set-venv](set-venv) in `~/.local/bin` and run

```
chmod +x ~/.local/bin/set-venv
```

### Usage

change into your project folder and run `set-venv path/to/python/executable` (or `set-venv` which will run using system python) and it will setup the virtual environment. The first setup will require internet.

To activate venv just type `activate` and to deactivate type `deactivate`.

Also to create project specific aliases or commands, add them to `.venvrc`.

###### Sources

[Setting Virtual Environment](https://github.com/ContinuumIO/anaconda-issues/issues/6917#issuecomment-340014721)
[Using Virtual Environment](https://docs.python-guide.org/dev/virtualenvs/#lower-level-virtualenv)
