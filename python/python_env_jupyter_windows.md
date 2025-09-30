# Python Environment Setup & Jupyter Notebook Guide (Windows)

This is a reference guide for setting up a Python environment on Windows using `pyenv-win`, installing dependencies, and working with Jupyter Notebooks. Perfect for data cleaning and analysis tasks.

---

## 1. Install pyenv on Windows

**Using pyenv-win:**

```powershell
# Open PowerShell as Administrator
# Install pyenv-win
git clone https://github.com/pyenv-win/pyenv-win.git $HOME\.pyenv
```

Add the following to your system environment variables (`Path`):

```
%USERPROFILE%\.pyenv\pyenv-win\bin
%USERPROFILE%\.pyenv\pyenv-win\shims
```

Restart PowerShell and check installation:

```powershell
pyenv --version
```

---

## 2. Install a specific Python version

```powershell
pyenv install 3.12.2  # Example: install Python 3.12.2
pyenv global 3.12.2   # Set it as the global Python version
python --version      # Confirm
```

---

## 3. Create a virtual environment

```powershell
# Using pyenv-virtualenv
pyenv virtualenv 3.12.2 myenv
pyenv activate myenv

# To deactivate
pyenv deactivate
```

---

## 4. Setting up a project folder

```powershell
mkdir my_project
cd my_project
pyenv local myenv   # Tie the virtualenv to this folder
```

---

## 5. Install dependencies

Create a `requirements.txt` file for your project:

```
numpy
pandas
matplotlib
seaborn
jupyterlab
ipykernel
```

Install dependencies:

```powershell
pip install -r requirements.txt
```

Or install packages one by one:

```powershell
pip install pandas numpy matplotlib seaborn
```

---

## 6. Setting up Jupyter Notebook

```powershell
# Install Jupyter if not already installed
pip install jupyterlab ipykernel

# Create a kernel for this environment
python -m ipykernel install --user --name=myenv --display-name "Python (myenv)"

# Start Jupyter Lab / Notebook
jupyter lab
# or
jupyter notebook
```

Your environment `myenv` will now be available as a kernel inside Jupyter.

---

## 7. Handy Python Tips for Data Cleaning

```python
import pandas as pd
import numpy as np

# Load CSV
df = pd.read_csv('data.csv')

# Inspect data
df.head()
df.info()
df.describe()

# Drop missing values
df.dropna(inplace=True)

# Fill missing values
df['column'] = df['column'].fillna(0)

# Remove duplicates
df.drop_duplicates(inplace=True)

# Convert column types
df['column'] = df['column'].astype(float)

# Basic filtering
df_filtered = df[df['column'] > 10]

# Save cleaned CSV
df.to_csv('cleaned_data.csv', index=False)
```

---

## 8. Tips for a Good Workflow

- Use `.gitignore` to avoid committing virtual environments:

```
myenv/
__pycache__/
*.pyc
*.ipynb_checkpoints/
```

- Always use `pyenv local` per project to avoid version conflicts.
- Keep `requirements.txt` updated after installing new packages:

```powershell
pip freeze > requirements.txt
```

- Consider using `black` or `isort` for formatting notebooks and Python scripts.

