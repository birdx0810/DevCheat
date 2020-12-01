# Python Cheat Sheet

## pipenv
### Getting Started
```bash
# Install
pip install --user pipx
pip install --user pipenv
# Upgrade
pip install --user -U pipenv
```

If pipenv isn't available after installation, add user base binary to `PATH`
```bash
# For bashrc
echo "set PATH /home/bird/.local/bin:${PATH}" >> ~/.bashrc
# For fish
echo "set PATH /home/bird/.local/bin $PATH" >> ~/.config/fish/config.fish
```

#### Virtualenv mapping
```bash
# For bashrc (or zsh)
echo "export PIPENV_VENV_IN_PROJECT=1" >> ~/.bashrc 
# For fish
set -Ux PIPENV_VENV_IN_PROJECT 1
```

### Install
```bash
# Install a new package
pipenv install [pkg names]
# Install from `requirements.txt`
pipenv install -r path/to/requirements.txt
```

### Upgrade
```bash
# Update all
pipenv update
# Update all outdated
pipenv update --outdated
# Update specific package
pipenv update <pkg>
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
