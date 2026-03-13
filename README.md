# X-Retention-DS

A small data science project that simulates user retention on X (Twitter) and visualizes how ad load can impact churn.

## Project Overview

This project uses synthetic user data to model retention behavior:

- Generates 5,000 fake users
- Simulates device type, ad frequency, and content repetition score
- Creates a retention label (`is_retained`) from a probability model
- Visualizes the relationship between ad frequency and retention with a logistic regression curve

The core work is in a Jupyter notebook: `twitter_project.ipynb`.

## Repository Structure

- `twitter_project.ipynb`: Main analysis notebook
- `README.md`: Project documentation
- `.gitignore`: Ignore rules for virtual environments and local artifacts

## Tech Stack

- Python 3.10+
- pandas
- numpy
- matplotlib
- seaborn
- Jupyter Notebook

## Setup

### 1. Create and activate a virtual environment

PowerShell (Windows):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 2. Install dependencies

```powershell
pip install pandas numpy matplotlib seaborn notebook
```

### 3. Launch Jupyter Notebook

```powershell
jupyter notebook
```

Then open `twitter_project.ipynb` and run the cells from top to bottom.

## Analysis Logic

The notebook builds a simple retention model:

```text
prob_staying = 0.8 - (0.01 * ad_frequency) - (0.05 * repetition_score)
```

The probability is clipped to `[0, 1]`, and `is_retained` is sampled from a binomial distribution.

## Output

The notebook produces a chart showing a "burnout" curve, where higher ad frequency is associated with lower probability of retention.

## Notes

- Data is synthetic and generated at runtime.
- This project is intended for exploratory analysis and learning, not production forecasting.