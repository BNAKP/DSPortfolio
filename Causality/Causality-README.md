# Causality

## Project Overview
Causality - Using spearman correlation, eigenvector centrality and community detection to determine the causal inference between variables in the UN SDGs

### Problem - Why this project was done
The project investigates the complex interactions between the United Nations Sustainable Development Goals (SDGs), a set of 17 global objectives aimed at improving life and the planet by 2030. While each SDG has its own targets and indicators, they are interlinked—progress in one can influence others positively (synergies) or negatively (trade-offs). The challenge lies in understanding these interdependencies to help policymakers prioritise actions that accelerate overall progress. The project aims to uncover these relationships using network science, with a focus on Brazil and India, to identify key indicators that drive or hinder progress.

### Methodology - How this problem was tackled
The project investigates the complex interactions between the United Nations Sustainable Development Goals (SDGs), a set of 17 global objectives aimed at improving life and the planet by 2030. While each SDG has its own targets and indicators, they are interlinked—progress in one can influence others positively (synergies) or negatively (trade-offs). The challenge lies in understanding these interdependencies to help policymakers prioritise actions that accelerate overall progress. The project aims to uncover these relationships using network science, with a focus on Brazil and India, to identify key indicators that drive or hinder progress.

### Code - Tools, Data Cleaning and Causality Algorithms
The project was implemented in Python using the following tools and libraries:
- Pandas for data handling; Numpy and Scipy for numerical operations and correlation.
- Matplotlib for plotting; NetworkX for network visualisation and centrality calculations.
- CDLIB for community detection using the Leiden algorithm.
- Pickle for saving and loading intermediate results.

Key code modules included:
- Data Notebook: Cleaned and transformed raw data, applied sign corrections, grouped indicators by SDG.
- Eigenvector Centrality: Calculated and visualised centrality scores.
- Community Detection: Identified and visualised clusters of indicators.
- Delayed Correlation: Measured weak causality by comparing time-shifted correlations.
Additional modules explored betweenness centrality and temporal changes in centrality but were excluded due to data limitations.


### Results - What was found
It is vital to understanding the full network of interactions among SDG indicators to assess a country’s progress. By using network visualisation and eigenvector centrality, the study identified key indicators that reflect overall trends, showing that top indicators span multiple SDGs and cannot be confined to a single goal. Community detection revealed that UN classifications do not always align with statistical groupings, suggesting hidden structures in the data. The delayed correlation method provided a basic but useful insight into directional influence, showing that top indicators often act as “informational sinks” influenced by many others. This makes them valuable for tracking national progress, even if they are not the best levers for initiating change. Understanding both synergies and trade-offs is essential, as neglecting poorly performing indicators could have widespread negative effects

