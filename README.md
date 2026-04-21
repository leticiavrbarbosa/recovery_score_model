Recovery Score Model (WHOOP-inspired)
Overview

This project explores a simple, interpretable model for estimating daily recovery using three inputs:

Sleep duration
Resting heart rate
Activity strain

The goal is to translate physiological signals into a single recovery score (0–100) and an actionable recommendation.

Approach

Recovery is modeled as a weighted combination of three signals:

Sleep (40%) — primary driver of recovery
Resting heart rate deviation (30%) — indicator of physiological stress
Strain (30%) — proxy for prior exertion

Each input is:

Normalized to a common scale
Weighted based on relative importance
Combined into a single recovery score

This results in a simple and interpretable model:

Recovery = Sleep + HR + Strain
Example Logic
More sleep → higher recovery
Elevated resting heart rate → lower recovery
Higher strain → reduced next-day readiness

The model also generates a recommendation:

70–100 → High readiness (train hard)
40–70 → Moderate (train light)
0–40 → Low recovery (prioritize rest)
Visualization

The notebook includes a time-series visualization of recovery scores across multiple days, making it easy to observe trends and fluctuations in readiness.

Tech Stack
Python
Pandas
Matplotlib
Jupyter Notebook

Example Output
Day	Sleep	HR	Strain	Recovery	Recommendation
Mon	7.5	58	12	~80	Train hard
Tue	6.0	62	15	~55	Train light
Wed	5.5	65	18	~35	Rest

Model Notes
This is a simplified, interpretable model—not a physiological or clinical system
Constants (8 hours sleep, 10 bpm HR deviation, strain 20) are heuristic thresholds
In a production system, parameters would likely be:
Personalized per user
Learned from historical data
Adapted over time


Why I Built This

I’m interested in systems that translate physiological and behavioral data into actionable insights for users. This project explores how simple models can bridge raw data and meaningful recommendations in the human performance space.

Future Improvements
Personalization based on individual baselines
Multi-day fatigue modeling (rolling strain)
Nonlinear scoring (e.g., diminishing returns for sleep)
Integration with real wearable data


How to Run
Clone the repository
Open recovery_model.ipynb
Run all cells