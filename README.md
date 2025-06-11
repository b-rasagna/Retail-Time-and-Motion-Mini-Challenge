# Retail Time-and-Motion Mini-Challenge

This repository contains an end-to-end pipeline for analyzing retail video clips to extract time-and-motion statistics using a 3D CNN.

## Contents
- **`notebook.ipynb`** - Jupyter notebook running from data loading through visualization and model saving  
- **`requirements.txt`** - pinned core dependencies  
- **`model.pth`** - trained `r3d_18` checkpoint  
- **`time_motion_summary.csv`** - aggregated per-clip statistics (exported in the notebook)  
- **`report.pdf`** - two-page write-up with method, key figures, and recommendations  

## Setup & Run

1. **Clone** this repo  
2. **Install dependencies**:  
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the notebook**:

   * In Jupyter:

     ```bash
     jupyter lab
     ```

     then open `notebook.ipynb` and click “Run All.”
   * Or click the Colab badge at the top of `notebook.ipynb`.

The notebook will:

* Auto-install any missing packages
* Export `requirements.txt` for exact versions
* Train and validate the model (≈ 20 min on Colab GPU)
* Save `model.pth`
* Export `time_motion_summary.csv`
* Generate all plots inline

## File Descriptions

* **`notebook.ipynb`**: full pipeline with rich Markdown explanations
* **`requirements.txt`**: exact package versions used
* **`model.pth`**: final model weights
* **`time_motion_summary.csv`**: aggregated durations per clip and action
* **`report.pdf`**: concise two-page report
