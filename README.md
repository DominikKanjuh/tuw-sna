# Implied Role Mining

This project explores the process of **Implied Role Mining** using a dataset derived from the **Der Standard** newspaper platform. The primary objective is to identify and validate implied roles within the user data by analyzing behavior patterns, assigning roles based on predefined criteria and visualizing the relationships between roles and clusters.

Implied Role Mining involves defining user roles by leveraging platform functionalities and features, selecting key behavioral metrics and assigning roles based on conditions tailored to those features. Clustering techniques are then applied to validate the coherence of these roles by grouping users into clusters that reflect similar behavioral patterns.

The analysis employs hierarchical clustering using the Ward method. Visualization plays a critical role in this project, with the relationships between roles and clusters illustrated in both 2D and 3D PCA-reduced spaces.

## Prerequisites

- Python >= 3.12
- Docker (optional)

## How to Run the Project

### Using `pip`

```bash
pip install -r requirements.txt -c constraints.txt
```

### Using `uv`

```bash
pip install .
```

### Using `docker`

Build the docker image

```bash
docker build -t implied-role-mining .
```

Run the container

```bash
docker run -it -p 8888:8888 implied-role-mining
```

After running the docker container open the Jupyter URL displayed in the console in your browser.

## Usage

1. Navigate to the `scripts` directory
2. Open `clustering_with_roles.ipynb` in Jupyter
3. Follow the notebook instructions for analysis

## About the Dataset

The dataset was derived from the **Der Standard** newspaper platform. It contains user data from the platform, including various features such as user interactions, content consumption, and platform usage metrics. The dataset has undergone preprocessing and has been scaled to a uniform range of [-1, 1] to ensure consistency across all features. The processed dataset are available in the `data` directory.

## About the Project

This project was developed as part of the **Social Network Analysis (194.050)** course at **TU Wien** during the Winter 2024 semester.

**Authors**:

- Irene Garcia Villoria
- Júlia Royes Royo
- Roman Furzykov
- Dominik Kanjuh
