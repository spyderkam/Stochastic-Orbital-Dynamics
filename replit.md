# Workspace

## Overview

Pure Python 3.12 environment with scientific libraries.

## Stack

- **Python version**: 3.12.12
- **Package manager**: uv (via pyproject.toml)

## Installed Libraries

- **NumPy** 2.4.3 — numerical computing
- **SciPy** 1.17.1 — scientific algorithms
- **SymPy** 1.14.0 — symbolic mathematics
- **Matplotlib** 3.10.8 — plotting and visualization
- **Astropy** 7.2.0 — astronomy and astrophysics
- **Pandas** 3.0.1 — data analysis

## Structure

```text
workspace/
├── main.py          # Entry point
├── pyproject.toml   # Python project config and dependencies
└── uv.lock          # Locked dependency versions
```

## Running

The "Run Python" workflow executes `python main.py`.
