# CV5570 - Computer Vision for Construction Engineering

## Assignment 1

### Student Details

* **Name:** Vasantharan K
* **Roll No:** ID26S012
* **Program:** M.S
* **Department:** School of Interdisciplinary Studies
* **Course:** CV5570 - Computer Vision for Construction Engineering
* **Semester:** Jul - Nov 2026

---

## Project Structure

```text
CV5570_Assignment_1/
│
├── env/                    # Python virtual environment
├── images/                 # Input images used for the assignment
├── notebook_results/       # Results generated from the notebook
├── r2d2/                   # R2D2-related files and resources
├── report/                 # Assignment report
│
├── Assignment_1.ipynb      # Main assignment notebook
├── README.md               # Project documentation
├── requirements.txt        # Python dependencies
└── .gitignore              # Git ignore configuration
```

---

# Setup and Execution

## Step 1 - Clone / Open the Project

Open a terminal and navigate to the project directory:

```bash
cd CV5570_Assignment_1
```

---

## Step 2 - Create a Virtual Environment

Create a Python virtual environment named `env`:

```bash
python -m venv env
```

If the virtual environment already exists, this step can be skipped.

---

## Step 3 - Activate the Virtual Environment

### Windows PowerShell

```powershell
.\env\Scripts\Activate
```

### Windows Command Prompt

```cmd
env\Scripts\activate
```

After activation, the terminal should show `(env)` at the beginning of the command prompt.

---

## Step 4 - Upgrade pip

It is recommended to upgrade `pip` before installing the dependencies:

```bash
python -m pip install --upgrade pip
```

---

## Step 5 - Install Required Packages

Install the packages listed in `requirements.txt`:

```bash
pip install -r requirements.txt
```

---

## Step 6 - Install PyTorch with CUDA Support

The assignment uses PyTorch for the R2D2-based feature extraction and matching pipeline.

Install the CUDA 12.8 compatible PyTorch packages using:

```bash
python -m pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu128
```

### Verify PyTorch Installation

Run:

```bash
python -c "import torch; print('PyTorch:', torch.__version__); print('CUDA available:', torch.cuda.is_available()); print('CUDA version:', torch.version.cuda)"
```

If CUDA is available, the output should contain:

```text
CUDA available: True
```

If CUDA is not available, the notebook can still be executed using the CPU, although R2D2 processing may take considerably longer.

---

# Step 7 - Install Jupyter Notebook

If Jupyter Notebook is not already installed through `requirements.txt`, install it using:

```bash
pip install notebook
```

Alternatively, JupyterLab can be installed with:

```bash
pip install jupyterlab
```

---

# Step 8 - Launch the Notebook

Make sure the terminal is inside the project directory:

```bash
cd CV5570_Assignment_1
```

Then start Jupyter Notebook:

```bash
jupyter notebook
```

A browser window should open automatically.

Open:

```text
Assignment_1.ipynb
```

---

# Step 9 - Select the Correct Python Kernel

Inside Jupyter Notebook, select the Python interpreter corresponding to the virtual environment:

```text
env
```

For example:

```text
Kernel → Change Kernel → Python (env)
```

This is important because all packages installed in the virtual environment must be accessible to the notebook.

---

# Step 10 - Run the Notebook

Run the notebook from the **first cell to the last cell in sequential order**.

In Jupyter Notebook, use:

```text
Kernel → Restart Kernel and Run All Cells
```

or run individual cells using:

```text
Shift + Enter
```

The notebook performs the required computer vision operations and generates the corresponding results.

---

# Input Data

The input images required for the assignment are stored in:

```text
images/
```

The notebook expects the project directory structure to remain unchanged.

Therefore, `Assignment_1.ipynb` should be executed from the root project directory:

```text
CV5570_Assignment_1/
```

Do not move the notebook to another directory unless the relative paths in the notebook are updated accordingly.

---

# Results

Results generated during notebook execution are stored in:

```text
notebook_results/
```

The directory contains the output visualizations and intermediate results produced by the assignment.

The final report is available in:

```text
report/
```

---

# GPU Support

The R2D2 pipeline benefits significantly from GPU acceleration.

To check whether PyTorch can access the GPU:

```bash
python -c "import torch; print(torch.cuda.is_available())"
```

For additional information:

```bash
python -c "import torch; print(torch.cuda.get_device_name(0) if torch.cuda.is_available() else 'CUDA GPU not available')"
```

If a CUDA-enabled GPU is detected, the R2D2 implementation can use GPU acceleration.

---

# Re-running the Assignment

To run the assignment from a clean environment:

```bash
cd CV5570_Assignment_1

python -m venv env

.\env\Scripts\Activate

python -m pip install --upgrade pip

pip install -r requirements.txt

python -m pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu128

pip install notebook

jupyter notebook
```

Then open:

```text
Assignment_1.ipynb
```

and run all cells sequentially.

---

# Important Notes

1. **Activate the virtual environment before running the notebook.**
2. Ensure that the notebook is using the **`env` Python kernel**.
3. Keep the `images/`, `r2d2/`, and `notebook_results/` directories in their original locations.
4. Run notebook cells **in sequential order** because later cells may depend on variables or results generated by earlier cells.
5. A CUDA-enabled GPU is recommended for faster execution of the R2D2 pipeline.
6. If CUDA is unavailable, the notebook can be executed on the CPU, but processing time may increase.
7. Do not rename or move the input files unless the corresponding paths in the notebook are updated.

---

# Assignment Notebook

Main notebook:

```text
Assignment_1.ipynb
```

This notebook contains the complete implementation, experiments, visualizations, and results for Assignment 1.

---