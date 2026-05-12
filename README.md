# Valorant Patch Balance and Professional Pick Rate Analysis
Overview

This project analyzes how balance changes in Valorant patches relate to professional agent pick-rate movement in VCT tournaments. Using professional match data and manually engineered patch features, the project explores whether gameplay adjustments such as cooldown changes, utility strength changes, economy adjustments, and other balance categories are associated with shifts in the competitive meta.

The analysis focuses on interpretability rather than purely predictive performance by using regression-based modeling and exploratory tree-based methods to examine relationships between patch adjustments and professional agent selection.

## Research Question

How do different categories of Valorant balance changes relate to professional agent pick-rate movement in VCT tournaments?

## Project Goals
Track professional agent pick-rate movement over time
Align VCT tournaments with active Valorant patches
Engineer interpretable gameplay balance features from patch notes
Evaluate relationships between balance changes and professional pick-rate changes
Explore how existing meta popularity influences future pick rates
Dataset Information

The project combines two primary sources of information:

1. VCT Professional Match Data

Professional tournament pick-rate information was collected and aggregated at the agent-tournament level to better align with patch-level balance changes.

[VCT Dataset](https://www.kaggle.com/datasets/ryanluong1/valorant-champion-tour-2021-2023-data/data) 
   
*I recommend getting the information from here as I used the file paths in my workflow to gather data.* 

2. Patch Balance Features

Patch notes were manually categorized into gameplay adjustment types. Each balance feature was encoded directionally using:

- -1 = nerf
- 0 = no meaningful adjustment
- +1 = buff

## Feature Descriptions

This data was scraped from the VALORANT patch notes and filtered into one of these columns. These are character specific buffs and nerfs so overall bug fixes or gameplay changes were not accounted for.  

- cooldown_change - Ability Cooldown (Initiator signature all being set to 60 sec)

- charges_change - Ability usage count (Neon Dash Count 2 --> 1)

- duration_change - How long an ability lasts (Blinds)

- range_change - How far an ability reaches (Breach Ult Range)

- consistency_change - Ability changes that affect normal gunplay (Bullet Accuracy on Neon's dash going from extreme accuracy --> crouching accuracy)

- utility_strength_change - Ability changes (Cypher Camera now being heard)

- economic_value_change - Ability Price

## Methodology

Data Preparation

Tournament data was aligned with the active patch during each event

Pick rates were aggregated to the agent + tournament level

Previous tournament pick rates were calculated chronologically for each agent

delta_pick_rate was calculated to measure pick-rate movement between tournaments

**ONLY MAJOR TOURNAMENTS WERE CONSIDERED**

## Modeling Approaches
Linear Regression

Linear regression was used as the primary modeling method to evaluate relationships between patch adjustments and pick-rate movement.

Decision Tree Regression

A decision tree regressor was used as a secondary exploratory model to examine potential nonlinear relationships within the data.

This project should be interpreted as associative rather than strictly causal. Professional Valorant metas are influenced by many external factors beyond direct patch changes, including:

- Team strategy evolution

- Map pool preferences

- Coaching adaptation

- Regional metas

- Player comfort and familiarity

- Tournament timing relative to patches

As a result, patch adjustments alone cannot fully explain professional pick-rate movement.


## Findings 

The results of the analysis showed that some types of balance changes appeared to have a stronger relationship with professional pick-rate movement than others. Utility strength changes showed one of the clearest positive relationships in the regression model, which suggests that buffs or nerfs directly affecting an agent’s utility can have a noticeable impact on professional usage. This makes sense in competitive Valorant since utility often shapes site executes, map control, and overall team coordination.

Charge-related changes showed the strongest negative relationship in the model. This may suggest that adjustments affecting how often abilities can be used can heavily influence whether an agent stays viable in professional play. 

Economic value and range-related changes also showed negative relationships with pick-rate movement, which suggests that ability cost efficiency and utility reach may affect how consistently agents are selected across tournaments. On the other hand, cooldown and duration changes showed much smaller relationships in the model, which may indicate that these adjustments alone are not usually enough to significantly shift the professional meta.

The model also showed that previous pick rate still mattered. Agents that were already popular in the professional meta tended to remain relevant even after accounting for patch adjustments. This suggests that team familiarity, established strategies, and overall comfort with certain agents continue to play an important role in professional agent selection.

Overall, the findings suggest that patch balance changes do contribute to professional pick-rate movement, but they are only part of a much larger competitive environment that also includes map pools, team strategy, coaching adaptation, and evolving tournament metas.

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Author

**Riley Villanueva**

University of Texas at San Antonio
Statistics and Data Science Major
