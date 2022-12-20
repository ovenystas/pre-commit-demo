# pre-commit demo

[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit)](https://github.com/pre-commit/pre-commit)
[![linting: pylint](https://img.shields.io/badge/linting-pylint-yellowgreen)](https://github.com/PyCQA/pylint)

A git repository for demo of `pre-commit`.

## Setup environment

This repo is best used with a `Python Virtual Environment`. Create it using these commands:

On Linux:

```bash
python3 -m venv venv-demo
source venv-demo/bin/activate
```

On Windows (Ex: In Git Bash):

```bash
python -m venv venv-demo
venv-demo\Scripts\activate
```

Note: When finished working in a `Python Virtual Environment`, it can be deactivated by simply issuing the command:

```bash|bat
deactivate
```

### Install pre-commit

```bash
python3 -m pip install -r requirements.txt
```

```bat
python -m pip install -r requirements.txt
```

**Note:** On Windows it might be needed to choose another path for the pre-commit cache folder.
Then set environment variable PRE_COMMIT_HOME to the desired folder.

### Use pre-commit to install the Git hook

This repo uses pre-commit git hook. Install it inside the `Python Virtual Environment` with:

```bash
pre-commit install
```

## Install dependencies

### On Linux

```bash
sudo apt update
sudo apt install clang-format clang-tidy cppcheck
```

### On Windows

LLVM - https://github.com/llvm/llvm-project/releases

cppcheck - http://cppcheck.net/

## Run pre-commit for all files

Run all configured pre-commit hooks on all files in the repo.
The first time it will download and install the tools from PyPI (Python Package Index).
The tools to install and use are defined in the file `.pre-commit-config.yaml`.

```bash
pre-commit run --all-files
```

Run a specific hook on all files. In this example: `black`.

```bash
pre-commit run --all-files black
```

## Edit a file and make a commit

Edit file `hello_world.c`. For example move the "{" after main() to the next line.

Add and commit:

```bash
git add hello_world.c
git commit
```

This time `clang-format` should fail and re-format the file.
