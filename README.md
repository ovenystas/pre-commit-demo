[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit)](https://github.com/pre-commit/pre-commit)
[![linting: pylint](https://img.shields.io/badge/linting-pylint-yellowgreen)](https://github.com/PyCQA/pylint)

# pre-commit demo

A git repository for demo of pre-commit.

## Setup environment

This repo is best used with a Python Virtual Environment. Create it using these commands:

```bash
python -m venv venv-demo
source venv-demo/bin/activate
```

### Install Python modules

```bash
python -m pip install -r requirements.txt
```

### Install Pre-commit Git hook

This repo uses pre-commit git hook. Install it inside the Python Virtual environment with:

```bash
pre-commit install
```

## Run pre-commit

Run all configured pre-commit hooks on all files in the repo.

```bash
pre-commit run --all-files
```
