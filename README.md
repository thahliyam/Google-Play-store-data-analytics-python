# Google-Play-store-data-analytics-python

Project Overview

This comprehensive analysis examines Google Play Store data to extract meaningful insights about app performance, user sentiment, and market trends. The project combines data cleaning, exploratory analysis, sentiment processing, and interactive visualizations to provide actionable intelligence for app developers and market analysts.

Data Loading & Initial Setup

The analysis begins by importing essential Python libraries including pandas for data manipulation, numpy for numerical operations, seaborn and matplotlib for visualization, and nltk for sentiment analysis. Two primary datasets are loaded: "Play Store Data.csv" containing comprehensive app information with 13 features including app name, category, rating, reviews, size, installs, type, price, content rating, genres, and version details; and "User Reviews.csv" containing user feedback data with 5 features including translated reviews and sentiment metrics. The initial exploration reveals the Play Store data comprises 10,841 entries while the User Reviews dataset contains 64,295 records, providing a substantial foundation for comprehensive analysis.

Data Exploration & Cleaning Process

Comprehensive data exploration is conducted to understand data structure and quality issues. The datasets undergo rigorous cleaning including handling missing values - with 1,474 missing ratings being dropped entirely while categorical nulls in 'Type' and 'Content Rating' are filled with mode values. Data type conversions are performed to ensure numerical columns like 'Reviews', 'Size', 'Installs', and 'Price' are properly formatted for analysis. Duplicate entries are identified and removed, with 474 duplicates eliminated from apps data and 7,735 from reviews data. The cleaning process ensures data integrity for subsequent analysis while preserving the dataset's analytical value.

Skewness Analysis & Transformation

Skewness analysis reveals the 'Rating' column exhibits moderate right-skewness with a value of 0.64, falling within the acceptable range of 0.5-1.0. Attempts to normalize this using Yeo-Johnson power transformation prove unsuccessful as the transformed data shows increased skewness of 1.72, indicating the transformation exacerbates rather than improves the distribution. Consequently, the decision is made to retain the original rating data. For sentiment metrics, both 'Sentiment_Polarity' and 'Sentiment_Subjectivity' demonstrate acceptable skewness values of -0.12 and -0.30 respectively, well within the normal range of -0.5 to 0.5, requiring no further transformation.

Sentiment Analysis Implementation

Sentiment analysis is performed on user reviews using NLTK's Vader Sentiment Analyzer, which calculates compound sentiment scores for each translated review. The analysis incorporates existing sentiment polarity and subjectivity metrics while adding computed sentiment scores. The resulting sentiment data shows average polarity of 0.18 and subjectivity of 0.49, indicating slightly positive and moderately subjective reviews overall. This comprehensive sentiment analysis provides valuable insights into user perceptions and emotional responses across different applications, enabling deeper understanding of user satisfaction drivers.

Interactive Dashboard & Time-Restricted Visualizations

Time-Restricted Visualization 

An intelligent dashboard system dynamically controls chart availability based on specific time windows. The system uses pytz for precise timezone management and validates current IST (Indian Standard Time) before rendering any time-sensitive visualizations.

Smart Chart Scheduling System

Grouped Bar Chart (3PM-5PM IST Only)

Availability Window: Afternoon hours when stakeholders typically review daily performance metrics

Visualization Content: Direct comparison between average ratings and total review counts across top app categories

Technical Innovation: Dual y-axes implementation with separate scales and color coding (green for ratings, purple for reviews) to ensure both metrics are clearly visible despite scale differences

Data Filters: Ratings ≥4.0, size ≥10MB, January updates only—ensuring analysis of high-quality, recent apps

Output: Interactive HTML file with dark theme optimized for professional presentations

Global Choropleth Map (6PM-8PM IST Only)

Strategic Timing: Evening hours designed for global team collaboration and international market analysis

Advanced Filtering: Exclusion of categories starting with A, C, G, or S to focus on less obvious high-performing segments

Geographical Insights: Visualization of install distribution across key markets including United States, India, United Kingdom, Germany, and other major territories

Interactive Features: Hover functionality displaying category and install counts for detailed country-level analysis

Dual-Axis Revenue Chart (1PM-2PM IST Only)

Operational Window: Early afternoon timing aligned with financial review sessions

Comparative Analysis: Side-by-side examination of installs and revenue for free versus paid apps within top categories

Comprehensive Filtering: Multiple criteria including minimum 10,000 installs, $10,000 revenue threshold, Android version >4.0, size >15MB, 'Everyone' content rating, and app name character limit of 30

Business Intelligence: Clear visualization of monetization effectiveness across different app categories and pricing models


Automated Plot Management

The system incorporates robust plot saving functionality that automatically creates and manages HTML files for dashboard integration. Each visualization generates self-contained HTML files with embedded Plotly libraries, ensuring portability and easy deployment. The saving process includes comprehensive error handling, directory management, and file verification to guarantee reliable output generation.


Timezone-Aware Execution

The dashboard implements precise timezone-aware execution using Asia/Kolkata timezone detection. Each time-restricted visualization includes real-time validation checks that prevent rendering outside designated windows while providing clear user feedback about availability schedules.

Key Analytical Insights

The analysis reveals significant patterns in app store performance metrics, user engagement levels, and monetization effectiveness. The sentiment analysis provides deep understanding of user satisfaction drivers, while the categorical analysis identifies high-performing app segments. The time-restricted approach ensures that stakeholders receive the most relevant insights at optimal times for decision-making.

Deployment Ready Components

All visualizations are generated as standalone HTML files suitable for immediate dashboard integration. The code includes comprehensive error handling, logging, and validation checks to ensure reliable operation in production environments. The modular design allows for easy extension and customization based on specific business requirements.

