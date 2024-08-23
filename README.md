
# Impact of Signal-to-Noise Ratio and Time Length on the Reliability of Gene Transcription Kinetics Data

## Overview

This study explores the impact of varying noise levels and time trace lengths on the reliability of synthetic fluorescence intensity data in gene transcription kinetics. By introducing a simple yet effective reliability indicator, this research aims to assist scientists in better controlling experimental variables, ensuring data quality, and advancing the understanding of gene expression regulatory mechanisms.

## Simulator

The simulator used in this study is based on the burstInfer tool. You can find more details and the source code of the simulator at [ManchesterBioinference/burstInfer](https://github.com/ManchesterBioinference/burstInfer).


## Experiments

### 1. Time Trace Length Experiment
This experiment investigates how different time trace lengths affect the reliability of gene transcription data. The goal is to identify a threshold for time trace length above which the data can be considered reliable. The experiment found that a time trace length of around 180 units is sufficient for the data to reach a stable state, ensuring reliable dwell time calculations.

### 2. Signal-to-Noise Ratio (SNR) Experiment
This experiment focuses on the effect of different SNR levels on data reliability. The study identified an SNR threshold of 30 dB, above which the data is considered reliable. The difference between Lag_0 and Lag_1 was used as a key metric to assess data reliability, and this threshold was consistent across various noise levels.

### 3. Intuitive Indicator Experiment
To address the challenge of not being able to directly observe SNR in real-world data, an intuitive indicator based on the autocorrelation function was developed. This indicator was validated against the results of the SNR and time trace length experiments, demonstrating that the difference between Lag_0 and Lag_1 is a reliable metric for quickly assessing data quality.

## Results Summary

- **Time Trace Length Experiment:** A time trace length of 180 units was identified as the threshold for reliable data, with dwell times stabilizing around this length.
- **SNR Experiment:** Data with an SNR greater than 30 dB were consistently reliable. The difference between Lag_0 and Lag_1 served as a reliable indicator of data quality.
- **Intuitive Indicator:** The proposed indicator, based on the difference between Lag_0 and Lag_1, effectively identified reliable data in line with the findings from the SNR and time trace length experiments.

## Installation

To run the experiments, follow these steps:

1. Ensure Python is installed on your system.
2. Clone the repository to your local machine.
3. Navigate to the cloned repository directory.
4. Install the required dependencies using the following command:

   ```bash
   pip install -r requirements.txt
   ```

This will install all necessary Python packages to run the Jupyter Notebooks included in this repository.

## Running the Experiments

### 1. Time Trace Length Experiment
Run the `time_trace_length_experiment.ipynb` notebook to explore the impact of varying time trace lengths on data reliability. The notebook will generate synthetic gene transcription data and compute the autocorrelation function to identify the optimal time trace length.

### 2. SNR Experiment
Run the `SNR_experiment.ipynb` notebook to investigate how different SNR levels affect the reliability of the synthetic data. This notebook generates data with varying noise levels and analyzes the autocorrelation function to determine the SNR threshold for reliable data.

### 3. Intuitive Indicator Experiment
Finally, run the `intuitive_indicator_experiment.ipynb` notebook to test the proposed reliability indicator. Ensure that the datasets generated from the SNR and time trace length experiments are available before running this notebook. The indicator will be validated against these datasets to confirm its effectiveness.

## Troubleshooting

- **Dependency Issues:** Ensure that all dependencies listed in `requirements.txt` are installed correctly. If you encounter issues, try reinstalling the packages.
- **Missing Data Files:** Ensure that the synthetic data files (`gene_w5.csv`, `long_gene_w5.csv`, etc.) generated during the experiments are correctly saved in the designated directories.
- **Unexpected Results:** If the results do not match expectations, check the parameters and settings in the Jupyter Notebooks, such as random seeds and noise levels.

## Synthetic Data Files

The synthetic data files generated during the experiments are saved as follows:
- **SNR Experiment:** Data saved as `gene_w5.csv` and `gene_w5_fluorescent_traces.csv`.
- **Time Trace Length Experiment:** Data saved as `long_gene_w5.csv` and `long_gene_w5_fluorescent_traces.csv`.

These files are critical for running subsequent analyses, particularly for validating the intuitive indicator.