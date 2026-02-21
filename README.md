# learn-python

Python learning repo for data analysis and machine learning, with support for exploratory work and experiments. Dependencies are managed with [uv](https://docs.astral.sh/uv/).

## Setup

**Prerequisites:** [uv](https://docs.astral.sh/uv/getting-started/installation/) and Python 3.9 (pinned via `.python-version`).

1. From the repo root, create the environment and install dependencies:

   ```bash
   uv sync
   ```

   This creates a virtual environment and lockfile. To add packages later: `uv add <package>`.

2. **(One-time)** Install the git hook that strips notebook outputs before each commit:

   ```bash
   uv sync --group dev
   uv run pre-commit install
   ```

   Every `git commit` will run [nbstripout](https://github.com/kynan/nbstripout) on staged notebooks so outputs are not stored in the repo.

## Notes

- **Data:** Keep datasets near the notebooks that use them; reference them with relative paths.
- **Large files:** Add large datasets to `.gitignore` or use [Git LFS](https://git-lfs.com/) if you want them versioned.
- **Notebook outputs:** Stripped automatically by the pre-commit hook; no need to clear them manually.
