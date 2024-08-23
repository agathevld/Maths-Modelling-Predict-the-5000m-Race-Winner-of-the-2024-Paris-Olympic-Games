<img src="https://centaur-wp.s3.eu-central-1.amazonaws.com/designweek/prod/content/uploads/2019/10/22133925/Featured-image1.jpg" alt="Olympic logo" width="250" />

# Project in Maths Modelling: Predict the 5000m Race Winner of the 2024 Paris Olympic Games
**Authors**: Lea Sauer & Agathe Vianey-Liaud

## Basic Overview

Sports predictions significantly influence areas like betting, sponsorship, and athlete training, with much of the research traditionally focused on team sports. This project shifts the focus to an individual sport by attempting to predict the results of the men's 5000m race at the 2024 Paris Olympics using two distinct approaches:

1. **Sentiment-Based Ranking**: Utilizing Tweets mentioning the athletes name posted before the race.
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
  - `keras`, `json`, `csv`, `requests`, `BeautifulSoup`, `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `tweepy`, `re`, `transformers`, `sentencepiece`, `os`, `time`, `twikit`, `subprocess`
  
## Project Structure

The repository is organized as follows:

```ruby
/data/             # Contains the datasets used in the project.
/Part1/          # Jupyter notebook for the sentiment analysis and corresponding visualizations.
/Part2/        # Jupyter notebooks for the feature anaylsis.
/Web scrapping/        # Scripts for web scraping
README.md          # The file you’re currently reading.
poster.pdf   # Project poster.
```

## Usage Instructions

### Running the Project

<h3><img src="https://img.freepik.com/vektoren-kostenlos/neues-twitter-logo-x-icon-design-2023_1017-45418.jpg?w=740" alt="X Logo" width="24" height="24"> Part 1: Sentiment analysis of the Tweets</h3>

**Web Scraping Tweets**:
   ```ruby
   python Web scrapping/Web Scrape Tweets.ipynb
   python Web scrapping/Web Scrape race results.ipynb
   ```

**Jupyter Notebook**:
Load the Jupyter notebook in `/Part1/Sentiment analysis.ipynb` to extract the sentiment of the Tweets.
<h3><span style="font-size: 24px;">&#128200;</span> Part 2: Feature analysis - past performances + simulated features</h3>

**Jupyter Notebook**:
Load the Jupyter notebook in `/Part2/code/UCD_Project-part2.ipynb` to do the webscraping, train the AI models and analyse the data and model outcomes.

## Datasets

### Tweets

- **Source**: Tweets collected from X via web scraping using the `Twikit` Python package, which circumvents the need for API keys. Filters set on **recent** and **top** performing Tweets.
- **Content**: Includes 625 tweets mentioning the athletes, with fields such as tweet content, username, posting date, and the athlete's actual race time and rank.

### Performance Data

- **Source**: Web scrapped from [World Athletics](https://worldathletics.org/).
- **Content**: The dataset comprises features from the top 100 athletes worldwide in the 5000m sprint, including past performances.

### Competition results

- **Source**: Web scrapped from [World Athletics](https://worldathletics.org/results/olympic-games/2024/the-xxxiii-olympic-games-7153115/men/5000-metres/final/result).
- **Content**: The dataset comprises the athlets name, time and rank from the men's Olympic 5k run.


## Model and Analysis

<h3><img src="https://img.freepik.com/vektoren-kostenlos/neues-twitter-logo-x-icon-design-2023_1017-45418.jpg?w=740" alt="X Logo" width="24" height="24"> Part 1: Sentiment analysis of the Tweets</h3>

- **Data Collection**: Tweets were collected before the race using the athletes' names as keywords.
- **Data Processing**: Sentiment analysis was conducted using the `nlptown/bert-base-multilingual-uncased-sentiment` model, classifying tweets into five sentiment categories,  `cardiffnlp/twitter-roberta-base-sentiment` and `xlm-roberta-base` model, classifying tweets into three sentiment categories.

<h3><span style="font-size: 24px;">&#128200;</span> Part 2: Feature analysis - past performances + simulated features</h3>

- **Data Collection**: Historical data of top athletes' performances was combined with simulated race features.
- **Data Simulation**: Monte Carlo techniques were employed to simulate variables like crowd cheering effect.
- **Data Analysis and Visualization**: Features from the performance dataset were analyzed using Linear Regression, Neural Networks, and Random Forest and evaluated using metrics such as MAE, MSE, and RMSE.

## Results

### Key Findings

- **Sentiment Analysis**: `nlptown/bert-base-multilingual-uncased-sentiment` model performed best on the Tweets. Showed moderate correlations between tweet sentiment and race results. However, sentiment alone was not a reliable predictor.
- **AI Models**: The Random Forest model outperformed others, demonstrating better predictive accuracy.

### Visualizations

- Sentiment distribution and correlation matrices are available in the `/Part1/Visualizations` folder.
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
