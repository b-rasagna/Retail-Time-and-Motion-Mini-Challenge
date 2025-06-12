# Retail Time-and-Motion Mini-Challenge

This repository contains an end-to-end pipeline for analyzing retail video clips to extract time-and-motion statistics using a 2D frame-level model (ShuffleNet V2 ×0.5) with an optional video-level RD3-18 alternative.

## Contents

* **`notebook_shufflenet.ipynb`** - Jupyter notebook implementing the frame-level ShuffleNet V2 ×0.5 pipeline
* **`notebook_r3d_18.ipynb`** - Jupyter notebook implementing the video-level R3D-18 pipeline
* **`requirements.txt`** - pinned core dependencies
* **`model_shufflenet.pth`** - trained ShuffleNet V2 ×0.5 checkpoint
* **`model_r3d_18.pth`** - trained R3D-18 checkpoint
* **`time_motion_summary_shufflenet.csv`** - aggregated per-clip stats from ShuffleNet pipeline
* **`time_motion_summary_r3d_18.csv`** - aggregated per-clip stats from R3D-18 pipeline
* **`report.pdf`** - two-page write-up with method, key figures, recommendations, and comparative note

## Setup & Run & Run

1. **Clone** this repo.
2. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```
3. **Run the notebook**:

   * In Jupyter:

     ```bash
     jupyter lab
     ```

     then open `notebook_shufflenet.ipynb` or `notebook_r3d_18.ipynb` and click **Run All**.
   * Or click the Colab badge at the top of notebook.

The notebook will:

* Auto-install any missing packages
* Export `requirements.txt` for exact versions
* Train and validate the ShuffleNet model (≈ 10–15 min on Colab GPU)
* Save `model.pth` and `time_motion_summary.csv`
* Generate all plots inline

## Comparative Note

**Video-Level Alternative:**
In a parallel experiment on a 200/50 demo split, the R3D-18 model achieved **73.5% → 77.0% → 81.5%** val accuracy over three epochs, with LR = 1e-4 (≈79.3% val acc) far outperforming LR = 1e-3 (30.5% val acc). However, inference speed was **\~20 FPS**, compared to **>300 FPS** with ShuffleNet V2.
