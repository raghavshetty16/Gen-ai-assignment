# Generative AI Assignment 1

This repository contains the implementation for **Generative AI Assignment 1**. The assignment is developed and executed using a Jupyter Notebook in **VS Code**.

## Project Structure

```text
assignment-1/
│
├── Assignment 1.ipynb
├── bbc-news-data.csv
├── job_title_des.csv
├── part1_news_analysis_results.csv
├── part2_job_analysis_results.csv
├── Generative AI - Assignment 1.pdf
└── README.md
```

### Files

- **`Assignment 1.ipynb`** — Main notebook containing the assignment implementation.
- **`bbc-news-data.csv`** — Dataset used for the news analysis task.
- **`job_title_des.csv`** — Dataset containing job title/description information.
- **`part1_news_analysis_results.csv`** — Results generated for Part 1.
- **`part2_job_analysis_results.csv`** — Results generated for Part 2.
- **`Generative AI - Assignment 1.pdf`** — Assignment instructions/reference document.

## Requirements

- Python 3.10+ recommended
- Visual Studio Code
- VS Code **Python** extension
- VS Code **Jupyter** extension
- Internet connection if the notebook uses external LLM/API services
- Required Python packages used by the notebook

## Setup in VS Code

### 1. Clone or download the project

Open the project folder in VS Code.

```text
File → Open Folder → assignment-1
```

### 2. Create a virtual environment

Using Python's built-in virtual environment:

```powershell
python -m venv .venv
```

Activate it on Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

Alternatively, if the project uses `uv`:

```powershell
uv venv
```

Then synchronize/install the project dependencies if a `pyproject.toml` is provided:

```powershell
uv sync
```

### 3. Install Jupyter and the required packages

If Jupyter is not already installed:

```powershell
python -m pip install jupyter ipykernel
```

Install the packages required by the notebook. For example:

```powershell
python -m pip install pandas numpy matplotlib
```

If the notebook contains additional imports, install those packages as required.

### 4. Select the VS Code Kernel

Open:

```text
Assignment 1.ipynb
```

In the top-right corner of VS Code:

```text
Select Kernel
    ↓
Python Environments
    ↓
Select .venv / uv environment
```

Make sure the selected kernel is the same environment where the required packages were installed.

You can verify the interpreter from a notebook cell:

```python
import sys
print(sys.executable)
```

## Running the Assignment

Open `Assignment 1.ipynb` and execute the cells sequentially.

You can run a cell using:

```text
Shift + Enter
```

or run the complete notebook using:

```text
Run All
```

It is recommended to execute the notebook from top to bottom because later cells may depend on variables, models, or outputs created by earlier cells.

## Dataset Paths

The datasets are stored in the same directory as the notebook. Therefore, relative paths can be used:

```python
import pandas as pd

news_df = pd.read_csv("bbc-news-data.csv")
job_df = pd.read_csv("job_title_des.csv")
```

Avoid hard-coding absolute Windows paths such as:

```text
C:\Users\YourName\Downloads\...
```

This keeps the project portable across different systems.

## Output Files

The notebook generates/uses CSV result files for the assignment:

```text
part1_news_analysis_results.csv
part2_job_analysis_results.csv
```

These files contain the outputs/results associated with the corresponding assignment sections.

## Troubleshooting

### Kernel is not visible in VS Code

Make sure the environment contains `ipykernel`:

```powershell
python -m pip install ipykernel
```

Then restart VS Code and select the environment again.

For a `uv` environment:

```powershell
uv run python -m pip install ipykernel
```

You can also verify the environment:

```powershell
uv run python --version
```

### ModuleNotFoundError

If you see:

```text
ModuleNotFoundError: No module named 'package_name'
```

install the missing package into the **same environment selected by the notebook**:

```powershell
python -m pip install package_name
```

For a `uv` project:

```powershell
uv add package_name
```

### CSV file not found

If you see:

```text
FileNotFoundError
```

make sure the notebook and CSV files are located in the expected project directory.

Check the current working directory from a notebook cell:

```python
import os
print(os.getcwd())
```

## Recommended Execution Order

1. Open the project folder in VS Code.
2. Activate/select the correct Python environment.
3. Open `Assignment 1.ipynb`.
4. Select the environment as the notebook kernel.
5. Verify the Python interpreter.
6. Install any missing dependencies.
7. Run the notebook from the first cell.
8. Check the generated outputs.
9. Review the final CSV result files.

## Notes

- Keep all input datasets in the project directory unless the notebook specifies otherwise.
- Do not commit API keys or passwords to Git.
- If an `.env` file is used for API credentials, add `.env` to `.gitignore`.
- Run the notebook using the same Python environment in which the dependencies are installed.
