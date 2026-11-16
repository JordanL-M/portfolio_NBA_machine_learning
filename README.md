# Project Name

## Purpose

Brief description of the project.

## Setup

### 1. Create the project from the template
 
On GitHub, open the template repo and click **Use this template → Create a new repository**. Then clone the new repo:
 
```powershell
git clone https://github.com/<username>/<project-name>.git
cd <project-name>
```
 
Update the `name` and `description` in `pyproject.toml`, and the title and purpose in this README.
 
### 2. Create and activate the virtual environment
 
```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```
 
> If PowerShell blocks the script, run this once:
> `Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned`
>
> If the terminal is Command Prompt, use `.venv\Scripts\activate` instead.
 
The prompt should now start with `(.venv)`.
 
### 3. Install dependencies
 
```powershell
python -m pip install --upgrade pip
pip install -e .
pip freeze > requirements.txt
```
 
### 4. Select the interpreter in VS Code
 
`Ctrl+Shift+P` → **Python: Select Interpreter** → choose `.\.venv\Scripts\python.exe` (Workspace).
 
### 5. Configure secrets
 
Copy `.env.example` to `.env` and fill in the database credentials and view names. `.env` is gitignored, so **never commit it.**
 
### 6. Load raw data
 
Run the ingestion script to pull data from MariaDB into `data/raw/` as CSV files. Exploration and reports read from these CSVs, not from the database.
 
### 7. Explore with marimo
 
```powershell
marimo edit notebooks/<notebook-name>.py
```
 
### 8. Write reports with Quarto
 
```powershell
quarto check jupyter # confirm Quarto can see the venv
quarto preview <path>/<report>.qmd # live preview; reloads on save
quarto render <path>/<report>.qmd --to docx
```

## Project Structure

- data/
- notebooks/
- src/
- output/
