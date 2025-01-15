# Implied Role Mining

This project explores the process of **Implied Role Mining** using a dataset derived from the **Der Standard** newspaper platform. The primary objective is to identify and validate implied roles within the user data by analyzing behavior patterns, assigning roles based on predefined criteria and visualizing the relationships between roles and clusters.

Implied Role Mining involves defining user roles by leveraging platform functionalities and features, selecting key behavioral metrics and assigning roles based on conditions tailored to those features. Clustering techniques are then applied to validate the coherence of these roles by grouping users into clusters that reflect similar behavioral patterns.

The analysis employs hierarchical clustering using the Ward method. Visualization plays a critical role in this project, with the relationships between roles and clusters illustrated in both 2D and 3D PCA-reduced spaces.

## Project Structure

- `data/`: Contains the processed datasets
- `scripts/`: Contains the Jupyter notebooks for analysis

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

### Data preprocessing

In `data_creation_scripts` **ADD** following data:

**ADD** Folder `Additional_Data` with all additional data that was provided:
`df_Clicks_net.parquet`
`df_CommunityConnection_filtered_net.parquet`
`df_Content_DimContentDetails.parquet`
`df_ContentPages_filtered_net.parquet`
`df_Postings_filtered_net.parquet`
`df_User_Activeness.parquet`
`df_Votes_filtered_net.parquet`

**ADD** empty Folder `Agg_Data` for results (They are already presented in `data` folder).

**ADD** empty Folder `Filtered_Data` for intermediate results.

**ADD** graph dataset `df_edge_list_directed_users_combined_postings_replies_and_votes_to_postings_net_and_follow_connections.parquet` to the `scripts`.

Run notebooks in given order to create Filtered_Data :

- `data_creation_scripts\users_reply_follow.ipynb`
- `data_creation_scripts\user_votes_user.ipynb`
- `data_creation_scripts\user_community_data.ipynb`
- `data_creation_scripts\user_click_act.ipynb`
- `data_creation_scripts\user_acrtiv_centrality.ipynb`

Run to aggregate data
`data_creation_scripts\user_all_data_aggregation.ipynb`

### Graphs Images

After `Data preprocessing` run in order:

- `data_creation_scripts\extract_user_roles.ipynb`
- `data_creation_scripts\create_visual_graphs.ipynb`

You will generate two files:

- subgraph.gexf
- subgraph2.gexf

Which can be used for Gephi.

### Clustering and Roles Analysis

1. Navigate to the `scripts` directory
2. Open one of the notebooks in Jupyter
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
