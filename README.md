# Stress Analysis in Social Media

## Project Overview
This project analyzes social media data from Reddit to identify stress indicators using the Dreaddit dataset. The dataset includes posts from five different Reddit communities, labeled for stress detection. The code performs data retrieval, preprocessing, visualization, and basic text analysis to explore stress-related patterns.

## Dataset
The dataset used is sourced from Kaggle: [Stress Analysis in Social Media](https://www.kaggle.com/ruchi798/stress-analysis-in-social-media). It contains 2838 rows and 116 columns, including features like post text, subreddit, label (stress or non-stress), confidence scores, and various lexical and social metrics.

## Dependencies
The following Python libraries are required:
- `numpy`
- `pandas`
- `matplotlib`
- `requests`
- `beautifulsoup4`
- `google-search-results` (SerpAPI)
- `networkx`
- `opencv-python`

Install them using:
```bash
pip install numpy pandas matplotlib requests beautifulsoup4 google-search-results networkx opencv-python
```

## Files
- **stress_analysis.py**: Main Python script for data retrieval, preprocessing, visualization, and analysis.
- **Stress_Analysis.ipynb**: Jupyter Notebook containing the same code as the Python script, with additional outputs and visualizations.
- **dreaddit-train.csv**: Training dataset (not included in this repository; download from Kaggle).
- **archive.zip**: Compressed file containing the dataset (assumed to be unzipped in the working directory).

## Usage
1. **Setup**:
   - Ensure all dependencies are installed.
   - Obtain a SerpAPI key and update the `api_key` in the code for Google search functionality.
   - Download the Dreaddit dataset from Kaggle and place `archive.zip` in the working directory.

2. **Running the Code**:
   - Execute `stress_analysis.py` or open `Stress_Analysis.ipynb` in a Jupyter environment.
   - The script performs the following:
     - Searches for the dataset URL on Kaggle using SerpAPI.
     - Downloads and parses the Kaggle page (note: web scraping may be incomplete due to Kaggle's dynamic content).
     - Unzips the dataset and loads `dreaddit-train.csv` into a pandas DataFrame.
     - Generates visualizations:
       - Bar plot of subreddit counts.
       - Bar plot of stress label distribution.
       - Scatter plot of social comments vs. upvote ratio.
     - Counts occurrences of stress-related words ("anxious," "stressed," "worried") and non-stress words ("relaxed," "calm," "happy").
     - Analyzes word frequency in the first two posts.
     - Creates a network graph of the top 20 words from the first two posts.
     - Prepares data arrays for features (`x`) and labels (`y`).

3. **Outputs**:
   - Console outputs include dataset details, word counts, and data shapes.
   - Visualizations are displayed as plots.
   - Network graph nodes are printed.

## Notes
- The web scraping section may not work as expected due to Kaggle's dynamic content. Consider downloading the dataset manually.
- The SerpAPI key in the code is hardcoded; replace it with your own key or remove it if not needed.
- The dataset must be unzipped before running the code (`!unzip /content/archive.zip`).
- The code assumes a Colab environment for some commands (e.g., `%matplotlib inline`). Modify for other environments if necessary.

## Limitations
- The web scraping functionality is incomplete due to Kaggle's JavaScript-rendered content.
- The analysis is basic and focuses on exploratory data analysis. Further machine learning models could be implemented for stress prediction.
- The network graph is rudimentary and only includes nodes without edges.

## Future Improvements
- Implement machine learning models for stress classification.
- Enhance web scraping with tools like Selenium for dynamic content.
- Add edge creation to the network graph based on word co-occurrence.
- Expand text analysis with advanced NLP techniques (e.g., sentiment analysis, topic modeling).

## Acknowledgments
- Dataset: Turcan, E., et al. (Dreaddit: A Reddit Dataset for Stress Analysis in Social Media)
- Kaggle for hosting the dataset
- SerpAPI for search functionality
