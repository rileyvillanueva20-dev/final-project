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

2. Patch Balance Features

Patch notes were manually categorized into gameplay adjustment types. Each balance feature was encoded directionally using:

-1 = nerf
0 = no meaningful adjustment
+1 = buff
Feature Descriptions

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

- Technologies Used
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
