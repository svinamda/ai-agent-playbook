### Jupyter Notebooks

This directory contains Python and Jupyter notebooks (.ipynb) used for data extraction, exploratory data analysis (EDA), processing pipelines, and local experimentation. 

### ⚙️ Environment Setup

To ensure reproducible results, please use a virtual environment to manage dependencies. 

### 1. Create a Virtual Environment

Navigate to this directory and create a new environment: 

bash

python -m venv venv

Use code with caution.

### 2. Activate the Environment

* **macOS / Linux:** 

bash

source venv/bin/activate

Use code with caution.
* **Windows (PowerShell):** 

bash

.\venv\Scripts\Activate.ps1

Use code with caution.

### 3. Install Dependencies

Install all required libraries and data science frameworks: 

bash

pip install --upgrade pip
pip install -r requirements.txt

Use code with caution.

### 4. Launch Jupyter

bash

jupyter notebook

Use code with caution.

### 🚫 Git Hygiene & Merge Conflicts

Jupyter Notebooks save execution counts, metadata, and raw outputs inside the JSON structure of the .ipynb file. This frequently causes large, unreadable merge conflicts in Git. 

### Strip Outputs Before Committing

Always clear your notebook cell outputs before pushing changes to GitHub. You can do this manually in the Jupyter UI via **Kernel -> Restart & Clear Output**, or use nbstripout to automate it: 

bash

# Install the utility
pip install nbstripout

# Strip a specific notebook manually
nbstripout your_notebook.ipynb

# Alternatively, set it up to strip outputs automatically on every git commit
nbstripout --install

Use code with caution.

### Exclude Cache Files

Ensure your root .gitignore file includes the following paths to keep the repository clean: 

text

.ipynb_checkpoints/
*/.ipynb_checkpoints/
__pycache__/
*.pyc

Use code with caution.
