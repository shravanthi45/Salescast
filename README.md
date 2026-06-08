🚀 SalesCast — AI-Powered Sales Prediction Dashboard

📌 Project Overview
An AI-powered end-to-end sales prediction and analytics project that accepts sales CSV data, trains a Random Forest machine learning model entirely in the browser, predicts revenue for every record, and visualizes business insights through an interactive React dashboard with forecasting, goal tracking, and AI chat.
This project demonstrates a complete machine learning workflow from raw sales data to actionable business intelligence — all running in the browser without any backend server.

🎯 Problem Statement
Businesses deal with large volumes of sales records across multiple categories, regions, and time periods, making manual revenue analysis slow and error-prone.
The challenge is to automatically process sales data, predict revenue for each record, measure model accuracy, forecast future sales trends, and generate meaningful business insights for data-driven decision making.

🎯 Objectives
✅ Accept and parse raw sales CSV files in the browser
✅ Train a Random Forest regression model on uploaded data
✅ Predict sales revenue for every row with confidence levels
✅ Visualize revenue by category, region, and month
✅ Forecast the next 6 months of sales using exponential smoothing
✅ Track business revenue goals vs predicted performance
✅ Enable plain-English querying of sales data through AI Chat
✅ Allow filtering, sorting, and exporting of all predictions

🛠️ Tech Stack
💻 Programming

JavaScript (ES6+)
React

🤖 Machine Learning

Random Forest Regressor (built from scratch in JavaScript)
Decision Tree with MSE-based splitting
Bootstrap sampling and Out-of-Bag validation
17 engineered input features

📊 Visualization

Recharts (Bar, Area, Line, Pie, Composed charts)
SVG (custom circular goal gauge)

📦 Data Handling

PapaParse (CSV parsing)

⚙️ Development Tools

VS Code
Webpack
Node.js


📊 Dataset Features
The CSV dataset contains:

Category
Sub-Category
Region
Segment
City / State
Quantity
Discount
Profit
Sales (used for model training)
Order Date
Ship Mode


🔄 Project Architecture
User Uploads CSV File
        ↓
PapaParse — CSV Parsing
        ↓
Feature Engineering (17 features)
        ↓
Random Forest Training (60 trees, OOB validation)
        ↓
Per-Row Sales Prediction + Confidence Level
        ↓
Data Aggregation
   ├── By Category
   ├── By Region
   ├── By Month
   ├── By Sub-Category
   └── By Year
        ↓
React Dashboard
   ├── Analytics Dashboard
   ├── RF Model Metrics
   ├── Sales Forecast
   ├── Goal Tracker
   ├── Records Table
   └── AI Chat
        ↓
Business Insights

🤖 Machine Learning Implementation
A Random Forest regression model was developed entirely from scratch in JavaScript without using any external ML library.
Model workflow:
✅ CSV data parsed and cleaned using PapaParse
✅ Raw columns converted into 17 numeric features
✅ Categorical fields encoded as numbers
✅ Interaction and log-transform features engineered
✅ 60 Decision Trees built using bootstrap sampling
✅ Each tree trained on a random subset of rows and features
✅ Out-of-Bag rows used for honest validation
✅ Final prediction = average of all 60 tree outputs
✅ Confidence measured using Coefficient of Variation

Evaluation metrics used:

OOB R² (Out-of-Bag accuracy)
Train R²
MAPE (Mean Absolute Percentage Error)
RMSE (Root Mean Square Error)


⚙️ Feature Engineering
17 input features were engineered from the raw CSV columns:
✅ Quantity, Discount, Profit (direct)
✅ Category, Sub-Category, Region, Segment, Ship Mode (encoded)
✅ Order Month (extracted from Order Date)
✅ Discount × Quantity (interaction term)
✅ Profit ÷ Quantity (profit per unit)
✅ High Discount Flag (1 if discount > 30%)
✅ Log(Quantity) (reduces skew)
✅ Log(Profit) signed (handles negatives)
✅ Category × Sub-Category (combined signal)
✅ Segment × Region (combined signal)
✅ Discount² (non-linear discount effect)

📈 Forecasting Implementation
Future sales projection was built using:
✅ Exponential Smoothing (alpha = 0.35) on monthly averages
✅ Trend calculation from first half vs second half of historical data
✅ Trend capped at ±15% per month to prevent extreme projections
✅ Confidence bands at ±1 standard deviation
✅ Bands widen further into the future to reflect uncertainty

📊 Dashboard Tabs
Interactive dashboard includes:
📍 Total Predictions Count
📍 Total Estimated Revenue
📍 Average Sale Value
📍 High Confidence Percentage
📍 Revenue by Category (Bar Chart)
📍 Revenue by Region (Horizontal Bar Chart)
📍 Monthly Sales Trend (Area Chart)
📍 Year-over-Year Revenue (Bar Chart)
📍 Confidence Split (Donut Chart)
📍 Top Sub-Categories (Table)
📍 Avg Sale by Category (Bar Chart)
📍 RF Model Accuracy Metrics
📍 6-Month Sales Forecast with Confidence Bands
📍 Goal Tracker with Circular Gauge
📍 Full Predictions Table (sortable, filterable, exportable)
📍 AI Chat for plain-English data queries

💼 Business Use Cases
This solution helps organizations:
📍 Predict revenue before it is realized
📍 Identify top-performing product categories
📍 Compare regional sales performance
📍 Detect low-confidence predictions for manual review
📍 Forecast future revenue trends
📍 Track progress against revenue targets
📍 Export predictions for further analysis
📍 Support data-driven sales strategy decisions

🚀 Future Enhancements
✨ Backend integration with Node.js or Django
✨ Real-time sales data ingestion via API
✨ Advanced AI Chat using LLM integration
✨ Automated low-confidence alert notifications
✨ Multi-file CSV upload and comparison
✨ User authentication and saved dashboards
✨ Mobile-responsive layout improvements
✨ Deep learning regression models (LSTM, XGBoost)

This Project Demonstrates
✅ React frontend development
✅ Machine learning implementation from scratch in JavaScript
✅ Random Forest and Decision Tree algorithm
✅ Feature engineering techniques
✅ Data visualization using Recharts
✅ Sales forecasting using exponential smoothing
✅ Business intelligence dashboard development
✅ CSV data handling and export
✅ End-to-end ML workflow without a backend server
