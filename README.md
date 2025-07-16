Wicketkeeper Career Analysis Tool
1. Introduction: What is this project?
This project is a sophisticated data analysis tool, written in Python, designed to objectively compare the career trajectories of cricket wicketkeeper-batsmen.

Instead of relying on subjective opinion, this tool uses real (simulated) career statistics and a machine learning technique called Principal Component Analysis (PCA) to create a data-driven "Performance Score".
It then generates smoothed-out graphs to visualize and compare the careers of multiple players, providing a clearer view of long-term trends and peak performance periods.

This tool moves beyond simple debates and provides a quantitative foundation for analyzing player careers.

2. Key Features
Objective Performance Scoring: It uses PCA to find the optimal, data-driven weights for key stats (runs, batting average, strike rate, dismissals), removing personal bias from the analysis.
Multi-Player Comparison: Allows users to select any number of players from the dataset for a side-by-side graphical comparison.
Granular Metric Selection: Users can choose to compare players based on the overall Performance Score or on individual statistics like runs, average, or dismissals.
Trend Smoothing: The graphs use a 3-year rolling average to smooth out sharp year-to-year fluctuations, making it easier to identify a player's true career arc (rise, peak, and decline).
Interactive & User-Friendly: The script is run from the command line and provides clear, interactive prompts for easy use.

3. How It Works: The Methodology
The credibility of this tool comes from its transparent and statistically sound methodology. Here is a step-by-step breakdown of the process:

Data Loading & Pre-processing: The script begins by loading player data from the keeper_data.csv file using the pandas library. A crucial first step is converting the calendar years in the data (e.g., 2004, 2005) 
into sequential "career years" (1, 2, 3...) for each player. This ensures all careers start at the same point for accurate comparison.

Optimizing Weights with PCA: To create a fair "Performance Score," we need to decide the importance (or "weight") of each statistic. Instead of guessing, we use Principal Component Analysis (PCA):
The raw stats (runs, avg, sr, dismissals) for every player-season are scaled to put them on a level playing field. PCA analyzes this scaled data to find the single combination of stats that best explains the
overall performance variance. The coefficients of this combination become our objective, data-driven weights. The script prints these weights every time it runs.

Calculating the Performance Score: Using these PCA-optimized weights, a single Performance Score is calculated for every year of every player's career.

Generating the Comparison Graph:

The tool prompts the user to select a metric and the players they wish to compare. Using Matplotlib, it plots the chosen metric against the "career year" for each selected player.
To make trends clearer, it calculates and plots a 3-year moving average, which smooths the lines and highlights the underlying career trajectory.

4. How to Use This Tool
To run this analysis on your own machine, follow these steps:

Prerequisites:
Make sure you have Python and the following libraries installed:

pandas
numpy
scikit-learn
matplotlib

Instructions:

Clone this repository or download the files.
Make sure the keeper_data.csv file is in the same directory as the Python script.
Run the script from your terminal:
python (your_script_name).py
The script will first print the PCA-optimized weights it has calculated.

Follow the interactive prompts:
First, choose the metric you want to analyze (e.g., "1" for Performance Score).
Next, enter the numbers corresponding to the players you want to compare, separated by commas (e.g., 1, 2, 8).
A graph visualizing the comparison will be generated and displayed.

5. How This Project Can Help
This tool is designed to be valuable for several audiences:
For Fans and Analysts: It provides a data-driven way to settle debates and analyze player careers with more depth and objectivity than ever before.
For Scouts and Coaches: It can be used as a powerful benchmarking tool. By comparing the smoothed career arc of an emerging talent to that of established legends, it's possible to get a clearer picture of their
development pace and potential.
