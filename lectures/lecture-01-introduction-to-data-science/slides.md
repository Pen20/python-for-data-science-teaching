# Lecture 1: Introduction to Data Science and Development Environment

**Course:** Python for Data Science 2026/2027  
**Instructor:** Motognon Wastalas d'Assise Dogbalou  
**Institution:** Open University of Kenya

## Part 1: Setting Up Your Development Environment

In this course, we will use **Git**, **GitHub**, and **Miniconda** to set up our Python development environment.

You do **not** need to install Python separately before installing Miniconda. Miniconda allows us to create and manage an isolated environment containing the Python version and packages required for this course.

### 1. Install Git

Git is a version control system that we will use to manage our code and course projects.

#### Windows

Open **PowerShell** and check whether Git is already installed:

```bash
git --version
```

If Git is installed, you should see a version number similar to:

```text
git version 2.x.x
```

If Git is not installed, install it using:

```bash
winget install --id Git.Git -e --source winget
```

After installation, close and reopen PowerShell, then verify:

```bash
git --version
```

#### macOS

Open **Terminal** and check whether Git is already installed:

```bash
git --version
```

If Git is not installed, macOS may prompt you to install the **Command Line Tools**. Follow the installation instructions.

After installation, verify again:

```bash
git --version
```

---

### 2. Create a GitHub Account

GitHub will be used to store, manage, and share your course projects and assignments.

If you do not already have a GitHub account, create one at:

[GitHub](https://github.com/)

After creating your account, make sure that you can successfully sign in.

---

### 3. Install Miniconda

We will use **Miniconda** to manage Python and the packages required for this course.

Follow the official installation instructions:

[Miniconda Installation Guide](https://www.anaconda.com/docs/getting-started/concepts/anaconda-or-miniconda)

Choose the appropriate installer for your operating system:

- Windows
- macOS

After installing Miniconda, close and reopen your terminal.

Verify that Conda is available:

```bash
conda --version
```

You should see a Conda version number.

> **Note:** If `conda` is not recognized immediately after installation, close and reopen your terminal. On Windows, you can also use **Anaconda Prompt** or **Miniconda Prompt**.

---

### 4. Create the Course Environment

Instead of installing all Python packages globally on your computer, we will create a dedicated environment for this course.

We will name the environment:

```text
python-ds
```

Create the environment with **Python 3.12**:

```bash
conda create -n python-ds python=3.12
```

Conda will display the packages that will be installed.

When prompted:

```text
Proceed ([y]/n)?
```

type:

```text
y
```

and press **Enter**.

---

### 5. Activate the Course Environment

Activate the environment:

```bash
conda activate python-ds
```

When the environment is active, you should see:

```text
(python-ds)
```

at the beginning of your terminal prompt.

For example, on Windows:

```text
(python-ds) C:\Users\Student>
```

> **Important:** Always activate the `python-ds` environment before working on the practical activities for this course.

---

### 6. Verify Python

Python was installed inside the `python-ds` environment when we created it.

Verify the Python version:

```bash
python --version
```

You should see something similar to:

```text
Python 3.12.x
```

The same command can be used inside the activated Conda environment on both **Windows** and **macOS**.

---

### 7. Verify Your Development Environment

Make sure the `python-ds` environment is active, then run:

```bash
git --version
conda --version
python --version
```

All three commands should return version information without errors.

You can also check your available Conda environments:

```bash
conda env list
```

The `python-ds` environment should appear in the list.

The active environment is usually indicated by `*`.

For example:

```text
# conda environments:
#
base                     C:\Users\Student\miniconda3
python-ds             *  C:\Users\Student\miniconda3\envs\python-ds
```

---

### What you should have at the end of Part 1

By the end of Part 1, you should have:

- Git installed and working
- A GitHub account
- Miniconda installed
- A Conda environment named `python-ds`
- Python 3.12 installed inside the `python-ds` environment
- The ability to activate and verify your course environment

Your basic development environment is now ready.

## Part 2: Installing JupyterLab and the Data Science packages

In Part 1, we created a Conda environment named `python-ds` with Python 3.12.

In this part, we will install the main tools and Python packages that we will use throughout the course.

---

### 1. Activate the course environment

Before installing packages or working on the course, make sure that the `python-ds` environment is activated.

```bash
conda activate python-ds
```

You should see `(python-ds)` at the beginning of your terminal prompt.

For example:

```text
(python-ds) C:\Users\Student>
```

> **Important:** Always activate the `python-ds` environment before working on the course.

---

### 2. Install JupyterLab

JupyterLab provides an interactive environment for writing and running Python code in notebooks.

Install JupyterLab inside the `python-ds` environment:

```bash
conda install jupyterlab
```

When prompted:

```text
Proceed ([y]/n)?
```

type:

```text
y
```

and press **Enter**.

Verify the installation:

```bash
jupyter lab --version
```

---

### 3. Install the core Data Science packages

We will use several Python libraries throughout the course.

Install the main packages:

```bash
conda install numpy pandas matplotlib
```

These packages have different purposes:

| Package      | Main purpose                   |
| ------------ | ------------------------------ |
| `NumPy`      | Numerical computing and arrays |
| `pandas`     | Data manipulation and analysis |
| `Matplotlib` | Data visualization             |

We will install additional packages later when they are needed.

---

### 4. Verify the installed packages

First, verify that the packages are installed in the current environment:

```bash
conda list
```

You should be able to find `numpy`, `pandas`, `matplotlib`, and `jupyterlab` in the list.

You can also verify them directly from Python:

```bash
python -c "import numpy; import pandas; import matplotlib; print('All packages imported successfully!')"
```

If everything is correctly installed, you should see:

```text
All packages imported successfully!
```

---

### 5. Launch JupyterLab

Make sure that the `python-ds` environment is still activated:

```bash
conda activate python-ds
```

Then launch JupyterLab:

```bash
jupyter lab
```

JupyterLab should automatically open in your default web browser.

> **Note:** The terminal running JupyterLab remains active while you are using JupyterLab. Do not close it during your session.

---

### 6. Create your first Jupyter notebook

In JupyterLab:

1. Click **Python 3** under the **Notebook** section.
2. A new notebook will open.
3. Rename the notebook to:

```text
first_notebook.ipynb
```

In the first cell, enter:

```python
print("Hello, Python for Data Science!")
```

Run the cell using **Shift + Enter**.

You should see:

```text
Hello, Python for Data Science!
```

---

### 7. Test the Data Science packages

Create a new cell and run:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

print("NumPy version:", np.__version__)
print("pandas version:", pd.__version__)

print("My Python for Data Science environment is ready!")
```

If the cell runs without errors, your environment is correctly configured.

---

### 8. Stop JupyterLab

When you have finished working, return to the terminal where JupyterLab is running.

Press:

```text
Ctrl + C
```

Confirm that you want to stop the Jupyter server if prompted.

---

### 9. Deactivate the Conda environment

When you have finished your work, you can deactivate the environment:

```bash
conda deactivate
```

The `(python-ds)` prefix should disappear from your terminal.

---

### What you should have at the end of Part 2

By the end of this section, you should be able to:

- Activate the `python-ds` Conda environment
- Install packages using Conda
- Verify installed packages
- Launch JupyterLab
- Create a Jupyter notebook
- Run Python code in a notebook
- Import NumPy, pandas, and Matplotlib
- Stop JupyterLab
- Deactivate the Conda environment

---

### Quick reference

Whenever you want to work on this course, the basic workflow is:

```bash
conda activate python-ds
jupyter lab
```

When you finish:

```bash
conda deactivate
```
