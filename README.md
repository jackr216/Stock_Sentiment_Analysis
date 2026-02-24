# Stock News Sentiment Analysis

Analyzing the relationship between financial news sentiment and stock price movements using AI-powered sentiment analysis.

## 📊 Project Overview

This project investigates whether news sentiment can predict stock price movements for **Microsoft (MSFT)**, **Tesla (TSLA)**, and **Visa (V)**. Using OpenAI's GPT-3.5 for sentiment analysis and financial news from major sources, the analysis examines correlations between news sentiment and stock returns.

**Key Question:** Does positive news sentiment predict stock price increases?

## 🎯 Key Findings

- **VISA** showed the strongest correlation (+0.52) between sentiment and next-day returns
- **TSLA** exhibited contrarian behavior (-0.33 correlation)
- **MSFT** showed weak correlation, suggesting limited short-term predictive power
- Overall weak-to-moderate correlations highlight limitations of 30-day sample size

## 🛠️ Technical Stack

- **Data Collection:** News API, Yahoo Finance API (`yfinance`)
- **AI/NLP:** OpenAI GPT-3.5 Turbo for sentiment analysis
- **Data Processing:** Pandas, NumPy
- **Visualization:** Matplotlib, Seaborn
- **Development:** Python 3.10+, Jupyter Notebooks

## 📁 Project Structure

```
Stock_Sentiment_Analysis/
├── data/
│   ├── raw/                      # Raw news and stock data
│   ├── processed/                # Sentiment-enriched data
│   └── outputs/                  # Visualizations and results
├── notebooks/
│   ├── 01_data_collection.ipynb       # News and stock price collection
│   ├── 02_sentiment_analysis.ipynb    # AI-powered sentiment analysis
│   ├── 03_correlation_analysis.ipynb  # Statistical correlation analysis
│   └── 04_summary.ipynb               # Findings and conclusions
├── requirements.txt
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- OpenAI API key
- News API key

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/jackr216/Stock_Sentiment_Analysis.git
cd Stock_Sentiment_Analysis
```

2. **Create virtual environment**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Set up API keys**

Create a `.env` file in the root directory:
```
OPENAI_API_KEY=your_openai_key_here
NEWS_API_KEY=your_newsapi_key_here
```

Get your API keys:
- OpenAI: https://platform.openai.com/api-keys
- News API: https://newsapi.org/register

### Running the Analysis

Execute notebooks in order:
1. `01_data_collection.ipynb` - Collect news and stock data
2. `02_sentiment_analysis.ipynb` - Analyze sentiment ($0.10-0.20 OpenAI cost)
3. `03_correlation_analysis.ipynb` - Calculate correlations
4. `04_summary.ipynb` - Review findings

## 📈 Methodology

### 1. Data Collection
- **Financial news:** 244 articles from Bloomberg, Reuters, CNBC, WSJ, Forbes
- **Stock prices:** Daily closing prices and returns from Yahoo Finance
- **Time period:** 30 days (Jan 26 - Feb 23, 2026)
- **Filters:** Business/financial keywords to focus on market-moving news

### 2. Sentiment Analysis
- OpenAI GPT-3.5 analyzes each article
- Returns sentiment classification (positive/negative/neutral)
- Numerical score from -1 (very negative) to +1 (very positive)
- Aggregated to daily sentiment scores per stock

### 3. Correlation Analysis
- Merged sentiment scores with stock price returns
- Calculated same-day and next-day correlations
- Analyzed days with news vs. days without news

## 📊 Results Summary

### Data Coverage
| Stock | Trading Days | Days with News | Avg Articles/Day |
|-------|-------------|----------------|------------------|
| MSFT  | 20          | 12 (60%)       | 7.2              |
| TSLA  | 20          | 16 (80%)       | 5.4              |
| VISA  | 20          | 18 (90%)       | 2.0              |

### Correlation Results
| Stock | Same-Day | Next-Day | Sample Size |
|-------|----------|----------|-------------|
| MSFT  | +0.14    | -0.12    | 12 days     |
| TSLA  | -0.01    | -0.33    | 16 days     |
| VISA  | +0.19    | **+0.52**| 18 days     |

## ⚠️ Limitations

1. **Small sample size:** 30-day window insufficient for statistical significance
2. **Timing mismatch:** Daily closing prices miss intraday reactions to news
3. **Equal weighting:** All articles treated equally (minor vs. major news)
4. **After-hours events:** Earnings typically released post-market, impacting next-day opening

## 🔮 Future Improvements

- [ ] Extend to 3-6 months of data
- [ ] Use intraday or opening prices for better timing alignment
- [ ] Weight articles by importance and source credibility
- [ ] Include social media sentiment (Twitter, Reddit)
- [ ] Focus analysis on major events (earnings, acquisitions)
- [ ] Build predictive ML model (classification)

## 📚 Skills Demonstrated

- API integration (News API, Yahoo Finance, OpenAI)
- Natural Language Processing with LLMs
- Financial data analysis and time series handling
- Statistical correlation analysis
- Data visualization and interpretation
- Critical evaluation of results and limitations

## 📝 License

This project is open source and available under the MIT License.

## 👤 Author

**Jack Roberts**

- GitHub: [@jackr216](https://github.com/jackr216)
- LinkedIn: [Your LinkedIn]
- Email: [Your Email]

## 🙏 Acknowledgments

- News data: [News API](https://newsapi.org/)
- Stock data: [Yahoo Finance](https://finance.yahoo.com/)
- Sentiment analysis: [OpenAI](https://openai.com/)

---

*Built as a demonstration of AI/ML engineering skills for data science portfolio*