# A-Novel-Framework-for-Quantifying-Player-Influence-in-Football-Using-Player-Tracking-Data
---


## Introduction
In football, understanding player influence is crucial for evaluating individual performance and team strategy. Traditional metrics often overlook the nuanced interactions between players and the ball carrier. This project introduces a novel player influence model designed to quantify a player's impact on the game using detailed tracking data. By incorporating positional, speed, and orientation information relative to the ball carrier, this model aims to provide a more robust framework for assessing defensive effectiveness, ultimately enhancing strategies for team management and player development.

## Methods
The player influence formula considers factors such as a player’s distance, speed, and orientation relative to the ball carrier. The influence metric is calculated using a Gaussian decay function, which decreases with distance, scales with player speed, and adjusts based on the player's directional movement:

\[
\text{Influence}_i = \exp\left(-\frac{d_i^2}{2\sigma^2}\right) \times \frac{v_i}{v_{\text{max}}} \times \cos(\theta_i)
\]

Where:
- **\(d_i\)**: Distance between player \(i\) and the ball carrier.
- **\(\sigma\)**: A tunable parameter controlling the rate of influence decay with distance.
- **\(v_i\)**: Speed of player \(i\).
- **\(v_{\text{max}}\)**: Maximum possible speed, adjusted to 9.3 - 9.5 yards/sec to reflect the top speeds of elite NFL players.
- **\(\theta_i\)**: The difference between the player's direction and the ball carrier's direction.

This model was applied to the [NFL Big Data Bowl 2024 dataset](https://www.kaggle.com/competitions/nfl-big-data-bowl-2024), covering weeks 1-8 of the season. We then assessed player influence against the number of tackles for validation, analyzing the relationship across all players and by position to confirm the metric's consistency.

## Results
Our analysis reveals a strong correlation (R² = 0.63) between cumulative player influence and the number of tackles across all positions, demonstrating that the metric effectively captures defensive impact. Positional analysis shows that this correlation is consistently high (R² > 0.55 for most positions), lending additional validity to the metric. 

Moreover, the metric exhibits strong stability over time, as indicated by a persistent correlation when comparing player influence from weeks 1-4 to weeks 5-8 (R² = 0.59). This consistency underscores the reliability and repeatability of the player influence measure as an assessment of defensive performance.

## Conclusion
The player influence metric offers a comprehensive and stable framework for evaluating defensive effectiveness. Its strong correlation with tackles, both overall and by position, makes it a valuable tool for coaches and analysts. By integrating key aspects of player positioning, speed, and orientation, this metric provides a more detailed understanding of defensive dynamics, aiding strategic decisions in team management and player development.

## Figures
1. **Scatter Plot**: Cumulative player influence vs. number of tackles, segmented by player position.
2. **Scatter Plot**: Player influence comparison between weeks 1-4 and weeks 5-8, illustrating the metric's stability.

---

Feel free to include any additional details, references, or data sources in your README as needed. This structure provides a clear overview of the project, the methods used, and the key findings in a format suitable for a GitHub repository.
