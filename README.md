[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit)](https://github.com/pre-commit/pre-commit)
[![linting: pylint](https://img.shields.io/badge/linting-pylint-yellowgreen)](https://github.com/PyCQA/pylint)

# pre-commit demo

A git repository for demo of `pre-commit`.

## Setup environment

This repo is best used with a `Python Virtual Environment`. Create it using these commands:

```bash
python3 -m venv venv-demo
source venv-demo/bin/activate
```

Note: When finished working in a `Python Virtual Environment`, it can be deactivated by simply issuing the command:

```bash
deactivate
```

### Install pre-commit

```bash
python3 -m pip install -r requirements.txt
```

### Use pre-commit to install the Git hook

This repo uses pre-commit git hook. Install it inside the `Python Virtual Environment` with:

```bash
pre-commit install
```

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
