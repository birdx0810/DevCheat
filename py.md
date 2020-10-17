# Python Cheat Sheet

## pipenv
```bash
sudo apt-get install pipenv
```

```
pipenv install <package>==<version>
pipenv install <package>==<version> --dev
pipenv uninstall

pipenv run <command>
```

## pytest
```bash
```

## syntax
```bash
pipenv run black -l 119 <package>
pipenv run flake8
pipenv run mypy -p <package> --ignore-missing-imports
pipenv run pylint <package>
```

## invoke
```bash
```

## security & ci
```
safety
bandit
drone ci
```

## jupyter
```bash
pip install jupyter-lab
pip install ipywidgets
jupyter nbextension enable --py widgetsnbextension
```
