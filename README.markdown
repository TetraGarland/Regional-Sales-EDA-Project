# Regional Sales EDA Project

## Overview

This project performs an Exploratory Data Analysis (EDA) on regional sales data from 2014-2018 to uncover trends, evaluate profitability, and support strategic decision-making for sales teams. The analysis identifies growth opportunities, regional performance variations, seasonal trends, top-performing products, channel profitability, budget utilization, and key customers.

**Problem Statement:** Sales teams often lack a clear, data-driven understanding of regional performance, making it difficult to identify growth opportunities and optimize resources.

**Objectives:**
- Analyze inconsistent revenue and profit performance across U.S. regions.
- Provide visibility into seasonal swings, top SKUs, and channel profitability.
- Leverage 5 years of historical data to pinpoint growth levers and optimize strategy.

The project uses Python for data processing and visualization, with results summarized in a PowerPoint presentation.

## Repository Contents

- **Regional_Sales_EDA.ipynb**: Jupyter notebook containing the full code for data loading, cleaning, merging, analysis, and visualizations.
- **Regional Sales EDA.pptx**: PowerPoint presentation summarizing the problem, approach, key metrics, insights, and recommendations with charts.
- **Regional Sales Dataset.xlsx**: The source dataset (Excel file with multiple sheets: Sales Orders, Customers, Regions, State Regions, Products, 2017 Budgets). *Note: If not included, download from your data source.*
- **README.md**: This documentation file.

## Setup and Installation

### Prerequisites
- Python 3.6+ (tested on Python 3.x)
- Jupyter Notebook or JupyterLab for running the .ipynb file.

### Dependencies
The project relies on the following Python libraries:
- numpy
- pandas
- matplotlib
- seaborn

Install them using pip:
```
pip install numpy pandas matplotlib seaborn
```

Alternatively, use a `requirements.txt` file (create one with the above libraries if needed):
```
pip install -r requirements.txt
```

### Running the Project
1. Clone the repository:
   ```
   git clone https://github.com/your-username/regional-sales-eda.git
   cd regional-sales-eda
   ```
2. Ensure the dataset (`Regional Sales Dataset.xlsx`) is in the root directory.
3. Launch Jupyter Notebook:
   ```
   jupyter notebook
   ```
4. Open and run `Regional_Sales_EDA.ipynb` cell by cell to reproduce the analysis.
5. View the PowerPoint (`Regional Sales EDA.pptx`) for a high-level summary.

*Note:* The notebook assumes the Excel file is named 'Regional Sales Dataset.xlsx'. Adjust the file path if necessary.

## Data Overview
- **Source:** Regional Sales Dataset (2014-2018)
- **Key Metrics:**
  - 64,104 orders
  - 175 unique customers
  - 994 regions, 48 states
  - 30 unique products
  - 2017 budgets
- **Columns (after merging/cleaning):** Order Number, Order Date, Customer Name, Channel, Product Name, Order Quantity, Unit Price, Line Total, Total Unit Cost, State Code, State Name, State Region, Latitude, Longitude, Product Budget, etc.
- **Derived Metrics:** Profit, Year, Month, Quarter, Budget Utilization %.

The dataset was cleaned by merging sheets on indices (e.g., Customer Name Index), reducing to 15 key columns, and removing duplicates.

## Analysis Approach
1. **Data Loading:** Read Excel sheets into pandas DataFrames.
2. **Data Integration:** Merge on indices (e.g., Customer, Region, Product).
3. **Data Cleaning:** Drop unnecessary columns, handle duplicates, add derived columns (e.g., profit = line_total - (order_quantity * total_unit_cost)).
4. **Analysis:** Compute KPIs by region, channel, product, and time using groupby operations.
5. **Visualization:** Bar and line charts for regional performance, seasonal trends, top SKUs, etc., using seaborn and matplotlib.

## Key Insights
- **Overall KPIs:**
  - Total Revenue: ~$1,000,000,000
  - Total Profit: ~$750,000,000 (75% margin)
  - Average Order Value: $15,596.78
  - Total Orders: 64,104 (steady YoY growth)
  - Unique Customers: 175
  - Unique Products: 30

- **Regional Performance:**
  - South: $400M revenue (40%), $300M profit (75% margin) – highest volume but cost inefficiencies.
  - West: $300M revenue (30%), $225M profit (75% margin) – better cost control.
  - Midwest/Northeast: Lag in volume ($200M and $100M revenue).
  - Insight: Focus on cost optimization in South; marketing boost in Northeast.

- **Seasonal Trends:**
  - Peaks in December (e.g., $100M in Dec 2017) due to holidays; Q4 30% higher than other quarters.
  - Dips in Jan-Feb (e.g., $50M in Jan 2014).
  - YoY growth: 20% from 2014 to 2018.
  - Insight: Prepare inventory in Q3; promotions in Q1.

- **Top SKUs by Revenue:**
  - Product 26: $117.3M (12%), high margin (75-80%).
  - Top 3 (Products 26, 25, 13): 30% of total revenue.
  - Insight: Prioritize top SKUs; phase out underperformers (bottom 10 contribute 20%).

- **Channel Profitability:**
  - Wholesale: $500M revenue (50%), $375M profit (75% margin).
  - Distributor: $300M revenue (30%), $225M profit (75% margin).
  - Export: $200M revenue (20%), highest margin (76%).
  - Insight: Scale Export for efficiency; optimize Wholesale for volume.

- **Budget vs Actual:**
  - Average utilization: 1,950%.
  - Product 26: 2,063% over budget ($117.3M vs $5.7M).
  - Insight: Reallocate budgets to top products.

- **Top Customers:**
  - Aibox Company: $12.6M (1.3%).
  - Top 10: 10% of total revenue (e.g., State Ltd, Pixoboo Corp).
  - Insight: Nurture top accounts; diversify to reduce risk.

## Recommendations
- Optimize costs in the South region; increase marketing in the Northeast for growth.
- Build inventory in Q3 for Q4 peaks; run promotions in Q1 to smooth revenue.
- Prioritize high-performing SKUs (e.g., Products 26, 25, 13); evaluate and phase out low performers.
- Scale the Export channel for higher margins; optimize costs in Wholesale.
- Adjust budgets upward for top products (e.g., Product 26) to support scaling.
- Diversify customer base to reduce dependence on the top 10 accounts.

## Limitations
- Data spans 2014-2018; budgets are only for 2017, leading to high utilization percentages (multi-year aggregation).
- No external data (e.g., market trends) integrated.
- Visualizations are static; consider interactive tools like Tableau for enhancements.

## Contributing
Feel free to fork the repository and submit pull requests for improvements, such as additional analyses or updated visualizations.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details (add one if needed).

## Contact
For questions, reach out via GitHub issues or [your-email@example.com].