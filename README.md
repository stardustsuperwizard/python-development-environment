# python-development-environment

## Summary 
This is a repository to create a basic development environment for coding in Python. 

[Poetry](https://python-poetry.org/docs) is used to manage Python dependencies for your application (boto3, requests, etc). You can specify groups of dependencies that are needed to run different tools in the repo. Typically, the groups are packages necessary to run a production application as well as simplify the development process (code formatters and linters).

At the top of the repo is the [`pyproject.toml`](https://pip.pypa.io/en/stable/reference/build-system/pyproject-toml/) file.

## Commands
```
poetry install
```
will create a virtual environment `.venv` and install the dependencies according to the `poetry.lock` file. By default, this installs all depency groups that are specified in the `pyproject.tmol` file. Once installed, a `python` executable, as well as tools such as `black` and `isort`, can be found in `.venv/bin`.  This will create a new `poetry.lock` file if one does not already exist.

**_Warning_**

Never manually update a `poetry.lock` file! If there is a problem with this file, delete it and rerun the command, `poetry install` and a new file will be generated.


```
poetry run python script.py
```
The virtual environment can be applied to any of the executed scripts by simply adding the prefix `poetry run`. 


```
poetry updaate
```
will do the following 
1. review the version of the restrictions in the `pyproject.toml` file.
2. resolve the latest compatible verions and update the `poetry.lock` file.
3. apply any changes to the virtual environment.


