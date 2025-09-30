# Quick Pyenv Bash Commands Cheat Sheet (Windows / Linux / macOS)

This is a concise guide of commands to manage Python versions and virtual environments with `pyenv`, activate environments, and install dependencies.

---

## 1. Check Python version

```bash
# Global system Python version
python --version

# Python version managed by pyenv
pyenv version
```

---

## 2. List Python versions installed with pyenv

```bash
pyenv versions  # Shows all Python versions installed via pyenv
```

---

## 3. List all available Python versions to install

```bash
pyenv install --list
```

---

## 4. Install a specific Python version with pyenv

```bash
pyenv install 3.12.2  # Example version
```

---

## 5. Set a Python version

```bash
# Set global version
pyenv global 3.12.2

# Set local version for current directory/project
pyenv local 3.12.2
```

---

## 6. Delete a Python version installed with pyenv

```bash
pyenv uninstall 3.12.2  # Removes the specified version
```

---

## 7. Create a virtual environment with pyenv

```bash
pyenv virtualenv 3.12.2 myenv  # Creates 'myenv' using Python 3.12.2
```

---

## 8. Activate and deactivate the virtual environment

```bash
# Activate
pyenv activate myenv

# Deactivate
pyenv deactivate
```

---

## 9. Install dependencies in the virtual environment

```bash
# Install a single package
pip install pandas

# Install from a requirements file
pip install -r requirements.txt
```

---

## 10. Check installed packages

```bash
pip list
```

This cheat sheet gives you the exact commands to manage Python versions and virtual environments using pyenv, including how to see all installed versions and how to delete a version.

