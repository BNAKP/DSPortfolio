# Causality

## Project Overview
Causality - Using spearman correlation, eigenvector centrality and community detection to determine the causal inference between variables in the UN SDGs

### Problem
During my masters i was invited to join a research group at the University of Aberdeen as a research assisitant. In my work i investigated the correlations and relationships between goals and variables in the UN sustainable development goals database. The key focus was to identify if any variables had a causal relationship or if changing one can have a negative or positive impact on another. Each goal in the database had 100s of variables contributing to its outcome and so it was first necessary to identify the most important variables in the goals and identify the relationship between them. Multiple algorithms were used such as spearman correlation, eigenvector centrality and community detection to determine the best method for calculating causal inference between the goals. The outcome of this analysis was instrumental in advising what a countries government should focus on to ensure the best possible route towards a sustainable future.

### Methodology

### Code

### Results
Sustainable Development Goals (SDGs) have the aim of improving
the planet and the lives of the people by 2030. SDGs cover a wide perspective of
global issues facing many countries, allowing for a detailed plan to be developed for
addressing these issues. We have focused on the interactions of the SDGs where a
strong positive correlation between a pair of indicators is a synergy, and a strong
negative correlation is a trade-off. Using network science to explore the interactions
we use methods of community detection, eigenvector centrality and delayed
correlation to explore the indicators further. Brazil and India both formed two distinct
clusters of indicators based on correlation rather than their UN classification.
Indicators with a large influence in synergies typically also had a strong influence in
trade-offs and were found to connect the denser cluster together. Indicators with the
greatest influence in trade-offs also had low influence in synergies and were trade-
offs with most of the network such as total greenhouse gas emissions. Weak causal
links were identified between funds for scholarships leading to more full-time
researchers as well as a greater renewable energy capacity giving rise to more funds
for infrastructure. Discovering the hidden structure of connections will allow for a
quicker delivery of the sustainability goals.
