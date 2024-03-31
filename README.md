# TwoSidedPlatform

## About this project

This project aims to optimize supply and demand balance for a two-sided platform that facilitates dog walking arrangements (e.g., Wag, Rover). Specifically, using a simple simulation in a hypothetical market, the project aims to illustrate how the platform owner can set a target number of dog walkers given anticipated demand, existing walkers, potential new walkers, and walker acquisition cost. Generally, the more providers in the market, the more transactions taking place, resulting in a higher revenue for the platform owner. However,
acquiring more providers requires higher acquisition costs, hence, the target number must consider the tradeoff between revenue and cost. The accompanying Jupyter Notebook solves a static optimization problem where I compare the platform owner's revenue against total
acquisition cost of achieving the target number of providers. The project also contains a preliminary analysis of how adding more providers could lead to an increase in unmatched providers, which is important to consider given that unmatched walkers may churn in the future.

## Contents

**Simulation.ipynb**: Contains analysis of determining how many more providers are needed in April 2024 to maximize the platform owner's profit. 

**Data**: Contains three input CSV files corresponding to (1) information on existing dog walkers who will be on the platform in April 2024 (existing_walkers.csv), (2) information on 20,000 simulated needs that occurr in the market for April 2024 (simulated_needs.csv), and (3) information on 20,000 simulated new walkers that could join the platform in April 2024 via marketing (simulated_new_walkers.csv).

(1) existing_walkers.csv: 
-provider_id: a unique identifier of a row
-latitude, longitude: walker's home location
-review_count: the number of review the walker has as of March 2024
-list_price: the price the walker charges per walk

(2) simulated_needs.csv:
-simulated_need_id: a unique identifier for a row
-start_date: the first date the walk is needed
-end_date: the first date the walk is no longer needed (i.e., end_date - 1 is the last date of the walk needed)
-latitude, longitude: pet owner's home location

(3) simulated_new_walkers:
-simulated_provider_id: a unique identifier for a row
-latitude, longitude: walker's home location
-review_count: the number of review the walker has. Always set to 0 by definition.
-list_price: the price the walker charges per walk

**requirements.txt**: Shows necessary package versions to run the Jupyter Notebook.

## Results

The revenue steadily increases as more providers are added to the market. Assuming that the per-provider cost of acquisition is $12, the profit gets maximized under around 30 providers.




