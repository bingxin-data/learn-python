# learn-python

Python learning repo: data analysis and machine learning tracks, plus a playground for one-off experiments. Dependencies are managed with [uv](https://docs.astral.sh/uv/).

## Setup

**Prerequisites:** [uv](https://docs.astral.sh/uv/getting-started/installation/) and Python 3.9 (the repo pins 3.9 via `.python-version`; uv will use it if available).

1. From the repo root, create the environment and install dependencies:

   ```bash
   uv sync
   ```

   This creates a `.venv` and a `uv.lock` from `pyproject.toml`. To add packages later: `uv add <package>`.

2. **(One-time)** Install the git hook that strips notebook outputs before each commit:

   ```bash
   uv sync --group dev
   uv run pre-commit install
   ```

   After this, every `git commit` will run [nbstripout](https://github.com/kynan/nbstripout) on staged `.ipynb` files so outputs aren’t stored in the repo.

3. Run Jupyter:

   ```bash
   uv run jupyter notebook
   ```

   Or activate the venv and run as usual:

   ```bash
   source .venv/bin/activate   # Windows: .venv\Scripts\activate
   jupyter notebook
   ```

Open any `.ipynb` from the folder you’re working in.

## File management

- **Data:** Keep datasets next to the notebooks that use them. Use a `data/` subfolder when a track or project has several files (e.g. `playground/data/`). In notebooks, reference files with paths relative to the notebook (e.g. `data/foo.csv` or `../data/foo.csv`).
- **Large data:** The `playground/data/` LoanStats CSVs (~90–100 MB each) are large for git. Options: (1) add `playground/data/` to `.gitignore` and document where to download the data, or (2) use [Git LFS](https://git-lfs.com/) if you want them versioned.
- **Notebook outputs:** The repo enforces stripped outputs via a [pre-commit](https://pre-commit.com/) hook (see Setup step 2). Staged notebooks are run through `nbstripout` before each commit.
- **Naming:** Numbered prefixes for ordered curriculum (`1_knn.ipynb`); descriptive snake_case for standalone notebooks (`hypothesis_testing.ipynb`).
