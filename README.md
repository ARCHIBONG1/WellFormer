## WellFormer Codes Repository

Welcome to the WellFormer codes repository! This repository contains codes used for geophysical well-log forecasting across different geological fields including Athabasca, North Sea, and Volve.

### Code Structure

The `codes` directory is organized into three subfolders, each representing a different geological field:
- **Athabasca**
- **North Sea**
- **Volve**

Each folder contains IPython Notebook scripts tailored to the respective geological field. The notebooks are well-organized to facilitate easy navigation and understanding.

### System and Installation Requirements

These notebooks were trained using Nvidia RTX A5000 GPUs. To replicate the results easily, ensure that conda is installed on your system. Create a Python environment with all necessary packages using the following command:

```bash
conda env create -f forecasting1.yml
```

### GPU Setting & Code Reproducibility

The notebooks are optimized for GPU usage. Prior to executing other cells in the notebook, please ensure the following code is adjusted according to your system's GPU configuration:

```python
os.environ['CUDA_VISIBLE_DEVICES'] = "2"
```

This sets a specific GPU to be used by the notebook. Modify this setting based on the available GPUs on your system to avoid errors. If no GPU is available, the notebook will revert to using the CPU, which may significantly increase training times.

### File Paths

You must update the default file paths within the notebooks to match those on your system. Not doing so may lead to a "File path not found" error.

### Trained Models

The trained model weights are too large to be uploaded directly to the repository. They can be downloaded from the following Google Drive link:

[Download Trained Models](https://drive.google.com/drive/folders/1kpVI_KUKvDwT78EVHm90rSj80dCQoFcY?usp=sharing)

The trained weight can be loaded using the following lines contained within the repsective notebooks:
```python
#load our saved model again
!unzip -o '.../Models/Athabasca_Welllog_[DPHI].zip'
best_model_path='lightning_logs/lightning_logs/version_2/checkpoints/epoch=137-step=1701954.ckpt'
best_tft = TemporalFusionTransformer.load_from_checkpoint(best_model_path)
```

### Dataset

The datasets used in this project are open-source and can be downloaded from the following links:
- **Athabasca Oil Sands**: [MannvilleGroup Strat Hackathon by Justin Gosses](https://github.com/JustinGOSSES/MannvilleGroup_Strat_Hackathon)
- **North Sea**: [Force 2020 Well Log and Lithofacies Dataset for Machine Learning Competition by Bormann et al.](https://github.com/bolgebrygg/Force-2020-Machine-Learning-competition/tree/master/lithology_competition)
- **Volve**: [Available Here](https://drive.google.com/drive/folders/1prYwCJdgpcNUmT0Mz3LAuCwrC0l3Z1TJ?usp=drive_link)

### Efficient Notebook Rendering

To view Jupyter Notebook files without downloading, paste the URL of this repository into:

[https://nbviewer.jupyter.org/](https://nbviewer.jupyter.org/)

### Key References

- Lim, B., Arık, S.Ö., Loeff, N., Pfister, T., 2021. Temporal fusion transformers for interpretable multi-horizon time series forecasting. *International Journal of Forecasting*, 37, pp.1748–1764.

### Remark

Please explore and customize the provided code as per your needs. If you encounter any issues or have questions, do not hesitate to reach out for assistance.
