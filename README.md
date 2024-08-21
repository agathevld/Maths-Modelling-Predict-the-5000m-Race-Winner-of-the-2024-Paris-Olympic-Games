<img src="https://centaur-wp.s3.eu-central-1.amazonaws.com/designweek/prod/content/uploads/2019/10/22133925/Featured-image1.jpg" alt="Olympic logo" width="250" />

# Project in Maths Modelling: Predict the 5000m Race Winner of the 2024 Paris Olympic Games
**Authors**: Lea Sauer & Agathe Vianey-Liaud

## Basic Overview

Sports predictions significantly influence areas like betting, sponsorship, and athlete training, with much of the research traditionally focused on team sports. This project shifts the focus to an individual sport by attempting to predict the results of the men's 5000m race at the 2024 Paris Olympics using two distinct approaches:

1. **Sentiment-Based Ranking**: Utilizing Tweets about the athletes posted before the race.
2. **AI Models**: Employing race-related features to predict athletes' scores (time and position).

## Table of Contents

- [Installation and Setup](#installation-and-setup)
- [Project Structure](#project-structure)
- [Usage Instructions](#usage-instructions)
- [Datasets](#datasets)
- [Model and Analysis](#model-and-analysis)
- [Results](#results)
- [Contribution Guidelines](#contribution-guidelines)
- [License](#license)
- [Contact Information](#contact-information)
- [Acknowledgements](#acknowledgements)

## Installation and Setup

### Installation

1. Clone the repository:
   ```ruby
   git clone https://github.com/project-leasauer
   ```

2. Create and activate a virtual environment:
   ```ruby
   python3 -m venv venv
   source venv/bin/activate
   ```

3. Install the required dependencies:
   ```ruby
   pip install -r requirements.txt
   ```

### Prerequisites

- **Python 3.x** and the following libraries:
  - `keras`, `json`, `csv`, `requests`, `BeautifulSoup`, `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`
  
## Project Structure

The repository is organized as follows:

```ruby
/data/             # Contains the datasets used in the project.
/scripts/          # Scripts for web scraping, data processing, and model training.
/notebooks/        # Jupyter notebooks for analysis and experimentation.
README.md          # The file you’re currently reading.
requirements.txt   # List of dependencies needed to run the project.
```

## Usage Instructions

### Running the Project

1. **Web Scraping Tweets**:
   ```ruby
   python scripts/scrape_tweets.py
   ```

2. **Training the AI Model**:
   ```ruby
   python scripts/train_model.py
   ```

3. **Analyzing the Results**:
   Load the Jupyter notebooks in `/notebooks/` to explore the data and model outcomes.

## Datasets

### Tweet Data

- **Source**: Collected via web scraping using the `Twikit` Python package, which circumvents the need for API keys.
- **Content**: Includes 625 tweets mentioning the athletes, with fields such as tweet content, username, posting date, and the athlete's actual race time and rank.

### Performance Data

- **Source**: The dataset comprises features from the top 100 athletes worldwide in the 5000m sprint, including past performances and simulated features (e.g., crowd cheering effect, environmental adaptation).

### Data Processing and Analysis

- **Sentiment Analysis**: Conducted using `Hugging Face`'s `nlptown/bert-base-multilingual-uncased-sentiment` model.
- **AI Models**: Features from the performance dataset were analyzed using Linear Regression, Neural Networks, and Random Forest, with the latter yielding the best performance.

## Model and Analysis

<h3><img src="https://img.freepik.com/vektoren-kostenlos/neues-twitter-logo-x-icon-design-2023_1017-45418.jpg?w=740" alt="X Logo" width="24" height="24"> Part 1: Sentiment analysis of the Tweets</h3>

- **Data Collection**: Tweets were collected before the race using the athletes' names as keywords.
- **Data Processing**: Sentiment analysis was conducted using the `nlptown/bert-base-multilingual-uncased-sentiment` model, classifying tweets into five sentiment categories.

<h3><span style="font-size: 24px;">&#128200;</span> Part 2: Feature analysis - past performances + simulated features</h3>

- **Data Collection**: Historical data of top athletes' performances was combined with simulated race features.
- **Data Simulation**: Monte Carlo techniques were employed to simulate variables like crowd cheering effect.
- **Data Analysis and Visualization**: Multiple AI models were trained and evaluated using metrics such as MAE, MSE, and RMSE.

## Results

### Key Findings

- **Sentiment Analysis**: Showed moderate correlations between tweet sentiment and race results. However, sentiment alone was not a reliable predictor.
- **AI Models**: The Random Forest model outperformed others, demonstrating better predictive accuracy.

### Visualizations

- Sentiment distribution and correlation matrices are available in the `/notebooks/` folder.
- Model performance metrics and residual plots are also included.

## Contribution Guidelines

To contribute to this project, follow these steps:

```ruby
git checkout -b {your-name/feature}
git add .
git commit -m "New Feature"
git push --set-upstream origin '{your-name/feature}'
git checkout main
git pull  # After PR gets merged into main branch
```

## License

This project is licensed under the MIT License. See the LICENSE file for more details.

## Contact Information

For inquiries or collaboration, please reach out to:

- **Lea Sauer**: lea.sauer@ucdconnect.ie
- **Agathe Vianey-Liaud**: agathe.vianey-liaud@ucdconnect.ie

## Acknowledgements

We would like to thank University College Dublin and specifically our professor Dr Sarp Akcay for his support and guidance throughout this project.
