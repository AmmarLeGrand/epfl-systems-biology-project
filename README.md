# EPFL Systems Biology Project

Collaborative EPFL Systems Biology course project using COBRApy and a SARS-CoV-2-infected macrophage metabolic model.

## Initial setup

1. Install Miniconda (or another Conda distribution), Git, and VS Code with Python and Jupyter extensions.
2. Clone the group's GitHub repository and open the project root in VS Code.
3. Run the following commands **from the project root**:

   ```bash
   conda env create -f environment.yml
   conda activate cobra-env
   python -c "import cobra; print('COBRApy', cobra.__version__)"
   ```

4. Choose the **cobra-env (Python 3.11)** kernel in VS Code.
5. Open `notebooks/model_exploration.ipynb` and run the cells.

To update an existing environment after changes to `environment.yml`:

```bash
conda env update -f environment.yml --prune
```

## Add the original course model and notebook

**The source files were not attached when this template was generated.** Copy your actual SBML file from your current `PAPER` folder into:

`data/iAB_AMO1410_SARS-CoV-2.xml`

A working **starter** notebook is provided at `notebooks/model_exploration.ipynb`. If you want to preserve your original notebook content, replace this starter notebook with your existing `model_exploration.ipynb` (or transfer its cells into this notebook). The starter checks that the XML file exists and loads it using a path that works whether the notebook runs from the repository root or the `notebooks/` directory.

Expected counts from the initial screenshot: 3,394 reactions, 2,572 metabolites, 0 genes. The counts are intended as a basic sanity check, not a guarantee that the model has no gene associations.

## Layout

```text
epfl-systems-biology-project/
├── data/                          # Add the original SBML model here
│   └── iAB_AMO1410_SARS-CoV-2.xml  # Copy from PAPER (not included)
├── notebooks/
│   └── model_exploration.ipynb     # Provided starter; replace if desired
├── src/                           # Reusable Python modules
├── environment.yml                # Shared Conda requirements
├── .gitignore
└── README.md
```

## GitHub team workflow

Create a **private**, empty GitHub repository named `epfl-systems-biology-project`. From this directory, after copying your original model in:

```bash
git init
git branch -M main
git add .
git commit -m "Initialize systems biology project"
git remote add origin https://github.com/YOUR_USERNAME/epfl-systems-biology-project.git
git push -u origin main
```

Invite your teammates via **Settings → Collaborators**. Everyone clones the repo and creates a feature branch for each task:

```bash
git switch main
git pull
git switch -c feature/my-analysis
# Work, test and save changes
git add .
git commit -m "Describe changes"
git push -u origin feature/my-analysis
```

Open a pull request to merge into `main`. To reduce conflicts, prefer distinct notebook files for different contributors. Avoid committing large notebook outputs, secrets, or machine-specific environment exports. Verify you have permission to share the SBML model before committing it.
