# FoG-STAR: Freezing of Gait Severity, Tasks, Activities, and Ratings

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.16989602.svg)](https://doi.org/10.5281/zenodo.16989602)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)

## 📌 Overview

This dataset contains wearable inertial sensor recordings and clinical/demographic information collected from 22 people with Parkinson’s disease.
It is designed to support research on Freezing of Gait (FoG) detection, severity estimation, activity recognition, and digital biomarkers.

The dataset is organized in two CSV files:

- sensor_data.csv → synchronized inertial sensor signals with FoG labels and task annotations
- clinical_data.csv → subject-level demographic and clinical assessments

## 🎯 Key Features

- **22 participants** with Parkinson's Disease
- **4 sensor positions**: Left ankle, Right ankle, Back, Wrist
- **6-axis IMU data**: Accelerometer (g) + Gyroscope (°/s)
- **60 Hz sampling rate**
- **7 motor tasks** designed to elicit FoG
- **Expert annotations**: FoG presence and severity levels
- **Clinical assessments**: H&Y, MDS-UPDRS III, FoG-Q, MoCA, FES-I, PDQ-8

## 📂 Dataset Structure

```
FoG-STAR/
├── sensor_data.csv          # Synchronized sensor signals with annotations (119.6 MB)
├── clinical_data.csv        # Subject demographics and clinical scores
├── FoG-Star_Analytics.ipynb # Example analysis notebook
└── LICENSE                  # CC-BY 4.0 license
```

## 📊 Data Description

### Sensor Data (`sensor_data.csv`)

31 columns sampled at 60 Hz:

| Column | Name | Description |
|--------|------|-------------|
| 1 | `timestamp` | Timestamp in milliseconds |
| 2-25 | Sensor signals | Format: `[position]_[sensor]_[axis]` |
| 26 | `activity` | Activity code (1-7) |
| 27 | `fog` | Binary FoG label (0/1) |
| 28 | `fog_severity` | Severity during FoG (1-3) |
| 29 | `subjectID` | Subject identifier (1-22) |
| 30 | `sessionID` | Recording session ID |
| 31 | `taskID` | Task code (1-7) |

**Sensor naming convention**: `[position]_[sensor]_[axis]`
- Positions: `ankleL`, `ankleR`, `back`, `wrist`
- Sensors: `acc` (accelerometer), `gyro` (gyroscope)
- Axes: `x`, `y`, `z`

**Activity codes**:
1. Walking
2. Sitting
3. Standing
4. Sit-to-Stand transition
5. Stand-to-Sit transition
6. Right turn
7. Left turn

**FoG severity levels**:
1. Shuffling forward
2. Trembling in place
3. Complete akinesia

**Task codes**:
1. Timed Up-and-Go (TUG)
2. Standing for 1 minute
3. Walking back and forth
4. Walking through doorway
5. Walking while carrying water
6. Walking while counting backwards
7. 360° turn

### Clinical Data (`clinical_data.csv`)

10 variables for 22 subjects:

| Column | Variable | Description | Range |
|--------|----------|-------------|-------|
| 1 | `subjectID` | Subject identifier | 1-22 |
| 2 | `age` | Age in years | - |
| 3 | `gender` | Gender | M/F |
| 4 | `disease_duration` | Years since PD diagnosis | - |
| 5 | `h_y` | Hoehn & Yahr stage | 0-5 |
| 6 | `updrs_iii` | MDS-UPDRS Part III score | 0-76 |
| 7 | `fog_q` | Freezing of Gait Questionnaire | 0-24 |
| 8 | `moca` | Montreal Cognitive Assessment | 0-30 |
| 9 | `fes_i` | Falls Efficacy Scale–International | 16-64 |
| 10 | `pdq_8` | Parkinson's Disease Questionnaire–8 | 0-32 |



## 📈 Analysis Examples

The included `FoG-Star_Analytics.ipynb` notebook provides:
- Data exploration and visualization
- FoG event duration analysis
- Severity distribution analysis
- Clinical correlation studies
- Signal visualization with FoG annotations

## 🔬 Research Applications

This dataset supports various research directions, such as:

1. **FoG Detection**: Binary classification of FoG presence
2. **Severity Estimation**: Multi-class severity prediction
3. **Activity Recognition**: Classification of motor activities
4. **Predictive Modeling**: FoG prediction before onset
5. **Digital Biomarkers**: Correlation with clinical assessments
6. **Multi-modal Fusion**: Combining multiple sensor positions

## 📝 Citation

If you use this dataset in your research, please cite:

```bibtex
@dataset{borzi2025fogstar,
  author       = {Borzì, Luigi and Demrozi, Florenc and others},
  title        = {FoG-STAR: Freezing of Gait Severity, Tasks, Activities, and Ratings},
  year         = {2025},
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.16989602},
  url          = {https://doi.org/10.5281/zenodo.16989602}
}

@article{borzi2025freezing,
  title={Freezing of gait detection: The effect of sensor type, position, activities, datasets, and machine learning model},
  author={Borzì, Luigi and others},
  journal={Journal of Parkinson's Disease},
  volume={15},
  number={1},
  pages={163--181},
  year={2025}
}

@article{demrozi2023lowcost,
  title={A low-cost wireless body area network for human activity recognition in healthy life and medical applications},
  author={Demrozi, Florenc and others},
  journal={IEEE Transactions on Emerging Topics in Computing},
  volume={11},
  number={4},
  pages={839--850},
  year={2023}
}
```

## ⚖️ License

This dataset is licensed under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) license.

You are free to:
- **Share**: Copy and redistribute the material in any medium or format
- **Adapt**: Remix, transform, and build upon the material for any purpose

Under the following terms:
- **Attribution**: You must give appropriate credit and provide a link to the license

## 👥 Contributors

- Luigi Borzì¹
- Florenc Demrozi²
- Ruggero Bacchin³
- Cristian Turetta⁴
- Michele Tebaldi⁴
- Luis Sigcha⁵
- Samaneh Zolfagharian⁶
- Domiziana Rinaldi⁷
- Giuliana Fazzina⁸
- Giulio Balestro⁹
- Alessandro Picelli⁹
- Graziano Pravadelli⁴,¹⁰
- Gabriella Olmo¹¹
- Stefano Tamburin⁹
- Leonardo Lopiano¹²
- Carlo Alberto Artusi¹³

¹Politecnico di Torino, ²Independent, ³University of Padova, ⁴University of Verona, ⁵University of Limerick, ⁶Mälardalen University, ⁷Sapienza University of Rome, ⁸University of Turin, ⁹University of Verona, ¹⁰EDALab s.r.l., ¹¹Politecnico di Torino, ¹²University of Turin, ¹³University of Turin

## 📧 Contact

For questions about the dataset, please:
- Open an issue on this repository
- Contact the corresponding authors through the Zenodo record
- Visit the [Zenodo dataset page](https://zenodo.org/records/16989602)

## 🔗 Links

- [Zenodo Dataset](https://zenodo.org/records/16989602)
- [Related Publications](https://doi.org/10.3233/JPD-230319)
- [IEEE TETC Paper](https://doi.org/10.1109/TETC.2023.3268019)
