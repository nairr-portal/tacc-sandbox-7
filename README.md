# TACC FlexServ Benchmark Notebook

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nairr-portal/tacc-sandbox-7/blob/main/tapis_flexserv_benchmark_task_07.ipynb)

**[View the notebook](./tapis_flexserv_benchmark_task_07.ipynb)**

This notebook demonstrates how to analyze and visualize the distribution of functional groups in molecular datasets using the UT Austin TACC Vista cluster, TACC's Tapis platform, and a FlexServ instance. It:

1. **Authenticates and initializes FlexServ** — connects to the TACC/Tapis platform, submits and monitors a FlexServ job, and loads a specified LLM.
2. **Prepares data** — embeds and writes the `dkpes_train.csv` and `dkpes_test.csv` datasets directly into the notebook for self-containment.
3. **Analyzes molecular activity** — identifies the 10 most and 10 least active molecules by `Signal-inhibition`, extracts their functional group counts, and visualizes the distribution to surface structural differences that may explain differing activity levels.
4. **Compares results** — displays the generated plot alongside a "gold standard" reference image.

The notebook is self-contained: dataset CSVs are embedded (encrypted, to avoid LLM training contamination) and dependencies are installed inline, so it can be run via the Colab badge above without cloning this repo.

## Running locally

Always use a local `venv/` in this directory when running Jupyter here — do not use a system or other environment's Python.

```
python3 -m venv venv
source venv/bin/activate
pip install jupyter notebook jupyterlab
jupyter lab   # or: jupyter notebook
```

The notebook's own runtime dependencies (`tapipy`, `pandas`, `matplotlib`, etc.) are installed by its own first code cell — no separate requirements file needed.
