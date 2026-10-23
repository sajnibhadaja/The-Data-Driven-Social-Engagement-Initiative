# The Data-Driven Social Engagement Initiative

An end-to-end analytics and machine learning pipeline that extracts YouTube engagement data, calculates statistical virality coefficients, analyzes audience sentiment via NLP, performs A/B testing on content formats, generates prescriptive content recommendations, forecasts rising trends, and outputs executive PDF reports and interactive Power BI dashboards.

---

## 🚀 Features & Pipeline Architecture

1. **Content Performance Tracker (Data Extraction Engine)**
   - Extracts multi-topic YouTube videos and comment threads via YouTube Data API v3.
   - Cleans and normalizes metrics (Views, Likes, Shares, Saves, Retention Rate).
2. **Relational Data Persistence**
   - Ingests structured video performance records into MySQL database (`video_metrics`).
3. **Virality Prediction Engine**
   - Computes weighted Viral Coefficients:
     $$\text{Viral Coefficient} = \frac{(\text{Shares} \times 2.0) + (\text{Saves} \times 1.5) + \text{Likes}}{\text{Views}}$$
4. **Audience Sentiment Analyzer (NLP)**
   - Processes user comment feedback using TextBlob polarity analysis to gauge emotional resonance.
5. **A/B Testing Framework**
   - Conducts comparative analysis across topics, sentiment styles, and video formats (Short vs. Long).
   - Validates statistical significance using Welch's two-sample t-test ($p < 0.05$).
6. **Engagement Optimization Recommender**
   - Prescribes optimal content strategy combinations (best topic, peak posting time, format, and sentiment tone).
7. **Growth Visualization Dashboard**
   - Formats engagement and save-to-share metrics for the interactive Power BI dashboard (`Growth Visualization Dashboard.pbix`).
8. **Trend Forecasting Module**
   - Combines topic and engagement indicators to rank rising future content trends.
9. **Executive Deliverable Generator**
   - Compiles full executive analytics and visual figures into `Social_Engagement_Project_Report.pdf`.

---

## 🛠️ Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/your-username/the-data-driven-social-engagement-initiative.git
cd the-data-driven-social-engagement-initiative
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Configure Environment Variables
Copy `.env.example` to `.env` and insert your credentials:
```bash
cp .env.example .env
```

Edit `.env`:
```env
YOUTUBE_API_KEY=your_youtube_api_key_here
MYSQL_HOST=localhost
MYSQL_USER=root
MYSQL_PASSWORD=your_mysql_password_here
MYSQL_DATABASE=youtube_project
```

---

## ⚡ Execution

Run the complete pipeline:
```bash
python run_project.py
```
Or open and execute the Jupyter Notebook:
```bash
jupyter notebook "The Data-Driven Social Engagement Initiative.ipynb"
```

---

## 📁 Repository Structure

```
├── .env.example                                  # Template for environment credentials
├── .gitignore                                    # Excludes .env and sensitive data
├── requirements.txt                              # Python package dependencies
├── README.md                                     # Project documentation
├── run_project.py                                # End-to-end execution script
├── The Data-Driven Social Engagement Initiative.ipynb  # Interactive Jupyter notebook
├── Growth Visualization Dashboard.pbix           # Power BI dashboard
├── Social_Engagement_Project_Report.pdf          # Compiled executive PDF report
├── youtube_dataset1.csv                          # Raw YouTube API extract
├── clean_youtube_dataset.csv                     # Sanitized dataset
├── viral_coefficient_dataset.csv                 # Virality metrics dataset
├── final_dataset.csv                             # Topic and viral classification dataset
├── sentiment_dataset.csv                         # NLP sentiment-tagged dataset
├── a_b_testing_framework.csv                     # A/B test outputs
├── final_recommendation_output.csv               # Optimization recommendations
├── dashboard_dataset.csv                         # Transformed Power BI dataset
└── trend_forecast.csv                            # Future trend score projections
```
