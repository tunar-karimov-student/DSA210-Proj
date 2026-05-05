# DSA210-Proj
DSA210 Project Repository

Project: The Long-Distance Dynamic (Spotify & Weather Analysis)
Users: TK (Istanbul, TR) & LG (Beijing, CN)

Timeline: 2025 - 2026

# Milestone 1: Foundations & Statistical Discovery
In the first phase, we established the data pipeline and tested our core hypothesis.
*   The Data Pivot: Originally designed to test audio "valence," we pivoted to streaming volume (minutes played) due to the deprecation of the Spotify Audio Features API. This demonstrated technical adaptability in the face of external API failures.
*   Methodology: We merged a full year of Spotify streaming history with local precipitation data from the Open-Meteo API.
*   Statistical Findings: Using a Welch’s T-Test, we found a divergence in behavioral patterns:
    *   TK (Istanbul): A significant increase in streaming on rainy days ($p = 0.0017$). We rejected the Null Hypothesis.
    * LG (Beijing): No significant change in streaming habits regardless of weather ($p = 0.8666$). We failed to reject the Null Hypothesis.

# Milestone 2: Machine Learning & Predictive Analysis
In the second phase, we moved from observation to prediction using Supervised Learning.
*   Goal: To determine if we could predict daily listening minutes based on weather and the "weekend effect."
*   Feature Engineering: We extracted the is_weekend binary feature to account for routine changes.
*   Model Performance:
    *   Linear Regression: Identified general trends (e.g., weekends add ~28 mins for TK), but had low predictive power ($R^2 \approx 0.04$).
    *   Random Forest Regressor: Attempted to capture non-linear patterns but resulted in a negative $R^2$.
*   Conclusion: The models confirmed our Milestone 1 findings. While weather is a statistically significant influence for TK, the high variance in human behavior makes exact minute-by-minute prediction impossible. Furthermore, the models' total failure on LG’s data validated that no underlying pattern exists to be learned.
