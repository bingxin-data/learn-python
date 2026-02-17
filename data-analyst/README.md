# data-analyst

Notebooks and materials for the data analyst track.

## Layout

| Path | Purpose |
|------|---------|
| **data/** | Input datasets (CSV, Feather, ICS, etc.). Reference in notebooks as `data/<filename>`. |
| **output/** | Generated figures and exports (gitignored). Use for `plt.savefig()`, exported tables, etc. |
| **\*.ipynb** | One notebook per topic or project at this level. |

## Current notebooks

| Notebook | Data |
|----------|------|
| `hypothesis_testing.ipynb` | `data/late_shipments.feather` |

Run notebooks with the working directory set to this folder (e.g. open `data-analyst` in Jupyter).

## Recommendations for future growth

- **New topics** – Add one notebook per topic (e.g. `sql_basics.ipynb`, `viz_dashboards.ipynb`). Use descriptive snake_case names.
- **New data** – Put any new files in `data/` and use paths like `data/your_file.csv` in notebooks.
- **Generated files** – Save plots and exports under `output/` so they stay out of version control and don’t clutter the folder.
- **Many notebooks** – If this folder gets crowded, consider subfolders by theme (e.g. `hypothesis_testing/`, `viz/`, `sql/`) with one notebook and a small `data/` or shared `../data/` per theme. Only do this when the flat list becomes hard to scan.
- **Shared code** – If you start reusing helpers across notebooks, add a small `utils.py` or `common.py` in this folder and `import` from notebooks, or move shared code to a package later.
