# Reddit Business Analyzer 📊

A sophisticated tool that combines Reddit data mining, AI-powered business analysis, and Monte Carlo simulations to generate and evaluate business opportunities.
![Project Interface](/marketmetrics.png)

## Overview 🌟

This project was created during the AGI House Global AI x Mathematics Hackathon to explore potential business opportunities by analyzing Reddit's most engaging content. It uses AI to generate business ideas from Reddit discussions and evaluates their viability through comprehensive Monte Carlo simulations.

## Features 🚀

### What this is
This was a hackathon project built in a few hours. Everything are jupyter notebook functions and classes you can repurpose into proper modules. The interface is an ipywidgets Streamlit element with self-refreshing sliders.

### Data Collection
- Automated scraping of top subreddits filtered by subscriber count 
- Extraction of most upvoted posts and comments
- Smart filtering based on engagement metrics
- Comprehensive data aggregation pipeline

### AI Business Analysis  
- LLM-powered business idea generation
- Market analysis and segmentation
- Problem-solution fit mapping  
- Automated business framework alignment

### Monte Carlo Simulation
Interactive simulation of key business metrics including:
- Customer retention rates
- Order processing costs
- Customer acquisition costs (CAC)
- Daily order volumes 
- Profit margins
- Customer Lifetime Value (CLV)
- Return on Investment (ROI)
- Payback periods

### Usage 📝
```
# Import the main classes
from reddit_scraper import SubredditScraper
from business_analyzer import BusinessAnalyzer

# Initialize scrapers
subreddit_scraper = SubredditScraper()
multi_reddit_scraper = MultiRedditScraper()

# Configure data collection parameters
SUBREDDIT_LIMIT = 20       # Number of subreddits to analyze
MIN_SUBSCRIBERS = 10000    # Minimum subscriber threshold 
POST_LIMIT = 3            # Number of top posts per subreddit
MIN_COMMENTS = 5          # Minimum comments per post
ORDER = 'bottom'          # 'top' or 'bottom' subreddits by subscriber count

# Collect subreddit data
posts_df = multi_reddit_scraper.scrape_multiple_subreddits(
    subreddits_df=subreddits_df,
    posts_per_subreddit=POST_LIMIT, 
    top_n=SUBREDDIT_LIMIT,
    order=ORDER
)

# Get top comments from posts
comments_df = get_top_comments(
    bottom_posts_df,
    num_comments=3,        # Top comments per post
    top_n_posts=10,        # Process only top N posts
    sort_by='score',       # Sort posts by score
    ascending=False,       # Sort in descending order
    min_score=100,         # Only posts with score >= 100
    min_comments=5         # Only posts with >= 5 comments
)

# Generate business ideas
ideas = generate_ideas(
    content_list=aggregated_posts,
    topic="web browsing automation",
    custom_prompt=None,    # Optional custom LLM prompt
    batch_size=5          # Batch size for processing
)

# Run financial analysis
analyzer = BusinessAnalyzer(business_list)

# Configure simulation parameters
analyzer.avg_order_slider.value = 55.0     # Average order size
analyzer.orders_slider.value = 60          # Daily orders
analyzer.retention_slider.value = 0.75     # Customer retention rate
analyzer.margin_slider.value = 0.15        # Profit margin
analyzer.marketing_slider.value = 1250.0   # Monthly marketing spend
analyzer.customer_acquisition_cost.value = 25.0  # CAC
analyzer.num_trials_slider.value = 1000    # Monte Carlo iterations

# Display interactive analysis dashboard
analyzer.display()
```

![Business Choices Running Default Filters](/marketmetricschoices.png)
### Interactive Analysis Dashboard 📊
The project includes an interactive dashboard built with Plotly and ipywidgets that allows users to:

- Select different business ideas
- Adjust simulation parameters
- Visualize profit distributions
- Analyze key financial metrics
- Compare different business scenarios

### Demo 🎥
Check out the live demo: [YouTube Video Demo](https://youtu.be/b7WXxQ34_h4?si=SPYGMArlNawA7LW-&t=4028)
#### Try It Yourself 🔥 

### Acknowledgments 🙏
AGI House Global AI x Mathematics Hackathon
