<p align="center">
  <img width="200" height="200" alt="blinkit_logo" src="https://github.com/user-attachments/assets/fd0d2df2-41df-4a85-a114-05e421de5113" />
</p>

<h1 align="center">🛒 Blinkit Sales Analysis</h1>

<p align="center">
  <strong>A comprehensive data analysis project exploring sales patterns, customer satisfaction, and inventory distribution for India's leading quick-commerce platform.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.13-blue?style=flat&logo=python" alt="Python"/>
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-green?style=flat&logo=pandas" alt="Pandas"/>
  <img src="https://img.shields.io/badge/Matplotlib-Visualization-orange?style=flat" alt="Matplotlib"/>
  <img src="https://img.shields.io/badge/Seaborn-Statistical%20Plots-red?style=flat" alt="Seaborn"/>
</p>

---

## 📖 Overview

This project analyzes Blinkit's retail dataset containing **8,523 records** across **12 attributes** to uncover actionable insights about sales performance, product characteristics, and outlet dynamics. The analysis identifies key drivers of revenue and provides data-driven recommendations for business optimization.

---

## 🏗️ High-Level Architecture

<img width="2752" height="1536" alt="High_Level_Architecture" src="https://github.com/user-attachments/assets/3e557746-18f2-4211-87a1-07878f376cad" />

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                        BLINKIT SALES ANALYSIS PIPELINE                       │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                            1. DATA INGESTION                                 │
│  ┌─────────────────┐                                                        │
│  │  blinkit_data   │──▶  pandas.read_csv()  ──▶  Raw DataFrame (8523 rows) │
│  │     .csv        │                                                        │
│  └─────────────────┘                                                        │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         2. DATA PREPROCESSING                                │
│  ┌──────────────────┐    ┌──────────────────┐    ┌──────────────────┐      │
│  │  Handle Missing  │    │   Standardize    │    │  Data Type       │      │
│  │     Values       │───▶│   Categories     │───▶│  Validation      │      │
│  │  (dropna/fillna) │    │ (Fat Content)    │    │                  │      │
│  └──────────────────┘    └──────────────────┘    └──────────────────┘      │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                     3. EXPLORATORY DATA ANALYSIS (EDA)                       │
│                                                                              │
│  ┌────────────────┐  ┌────────────────┐  ┌────────────────┐                 │
│  │  Descriptive   │  │  Distribution  │  │  Correlation   │                 │
│  │  Statistics    │  │  Analysis      │  │  Analysis      │                 │
│  └────────────────┘  └────────────────┘  └────────────────┘                 │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                          4. KPI COMPUTATION                                  │
│                                                                              │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐        │
│  │   Total     │  │  Average    │  │  Number of  │  │  Average    │        │
│  │   Sales     │  │   Sales     │  │   Items     │  │   Rating    │        │
│  │   ($1.2M)   │  │   ($141)    │  │   (8,523)   │  │   (3.9)     │        │
│  └─────────────┘  └─────────────┘  └─────────────┘  └─────────────┘        │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                         5. VISUALIZATION LAYER                               │
│                                                                              │
│  ┌────────────────────────────────────────────────────────────────────┐     │
│  │                    Matplotlib / Seaborn                            │     │
│  ├───────────────┬───────────────┬───────────────┬───────────────────┤     │
│  │  Bar Charts   │  Pie Charts   │  Horizontal   │  Grouped          │     │
│  │  (Item Type)  │  (Outlet Size)│  Bars (Loc.)  │  Analysis         │     │
│  └───────────────┴───────────────┴───────────────┴───────────────────┘     │
│                                      │                                       │
│                                      ▼                                       │
│  ┌────────────────────────────────────────────────────────────────────┐     │
│  │                       Power BI Dashboard                           │     │
│  │         (Interactive Dashboards for Stakeholders)                  │     │
│  └────────────────────────────────────────────────────────────────────┘     │
└─────────────────────────────────────────────────────────────────────────────┘
                                      │
                                      ▼
┌─────────────────────────────────────────────────────────────────────────────┐
│                        6. INSIGHTS & RECOMMENDATIONS                         │
│                                                                              │
│  • Identify top-performing item types and outlet configurations             │
│  • Detect regional sales disparities across Tier 1/2/3 locations            │
│  • Analyze fat content impact on consumer purchasing behavior               │
│  • Generate targeted promotion strategies for underperforming segments      │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 📊 Dataset Description

| Column | Type | Description |
|--------|------|-------------|
| `Item Fat Content` | String | Fat category (Low Fat / Regular) |
| `Item Identifier` | String | Unique product ID |
| `Item Type` | String | Product category (16 types) |
| `Outlet Establishment Year` | Integer | Year outlet was established |
| `Outlet Identifier` | String | Unique outlet ID |
| `Outlet Location Type` | String | City tier (Tier 1, 2, 3) |
| `Outlet Size` | String | Store size (Small, Medium, High) |
| `Outlet Type` | String | Store type (Grocery/Supermarket) |
| `Item Visibility` | Float | Product display percentage |
| `Item Weight` | Float | Product weight |
| `Sales` | Float | Sales amount |
| `Rating` | Float | Customer rating |

---

## 📈 Key Performance Indicators (KPIs)

| KPI | Value | Description |
|-----|-------|-------------|
| **Total Sales** | ~$1.2M | Aggregate revenue across all outlets |
| **Average Sales** | ~$141 | Mean sales per transaction |
| **Number of Items** | 8,523 | Total unique product entries |
| **Average Rating** | ~3.9 | Mean customer satisfaction score |

---

## 🔍 Visual Insights

### Sales by Fat Content
<img width="377" height="293" alt="Picture1" src="https://github.com/user-attachments/assets/fd3798b2-1a4b-4433-9c34-28145f30384e" />

*Regular and Low Fat products show comparable sales performance.*

### Top 10 Item Types by Sales
<img width="408" height="287" alt="Picture2" src="https://github.com/user-attachments/assets/18aaffce-2042-4824-bfee-a61364950aff" />

*Fruits & Vegetables and Snack Foods lead sales, followed by Household items.*

### Sales Distribution by Outlet Size
![Picture3](https://github.com/user-attachments/assets/6cb5e3bc-2e44-4f1d-b5a7-457b9cdc109b)

*Medium (37.8%) and Small (37.2%) outlets contribute nearly equal shares of total sales.*

### Sales by Outlet Location
<img width="399" height="243" alt="Picture4" src="https://github.com/user-attachments/assets/d5908c3e-9bfe-4661-a5da-9f80aaad6cab" />

*Tier 2 locations generate the highest revenue, followed by Tier 3 and Tier 1.*

---

## 🚀 Getting Started

### Prerequisites
```bash
Python 3.10+
pip (Python package manager)
```

### Installation
```bash
# Clone the repository
git clone https://github.com/yourusername/blinkit-sales-analysis.git
cd blinkit-sales-analysis

# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install pandas numpy matplotlib seaborn jupyter
```

### Running the Analysis
```bash
# Launch Jupyter Notebook
jupyter notebook BLINKIT_ANALYSIS.ipynb
```

---

## 📁 Project Structure

```
blinkit-sales-analysis/
│
├── 📓 BLINKIT_ANALYSIS.ipynb    # Main analysis notebook
├── 📊 blinkit_data.csv          # Raw dataset (8,523 records)
├── 🖼️ blinkit_logo.png          # Project logo
├── 📄 README.md                 # Project documentation
├── 📄 Project_Info              # Project summary
│
└── 📸 Visualizations/
    ├── Picture1.png             # Code snippet - Data loading
    ├── Picture2.png             # Code snippet - Fat content analysis
    ├── Picture3.jpg             # Code snippet - Item type analysis
    ├── Picture4.png             # Chart - Sales by Fat Content
    ├── Picture5.png             # Chart - Top 10 Item Types
    ├── Picture6.png             # Chart - Outlet Size Distribution
    └── Picture7.png             # Chart - Outlet Location Sales
```

---

## 🔑 Key Findings

1. **Product Performance**: Fruits & Vegetables and Snack Foods are the top revenue generators, contributing over 25% of total sales combined.

2. **Outlet Size Impact**: Medium and Small outlets perform comparably, suggesting operational efficiency at smaller scales.

3. **Location Analysis**: Tier 2 cities outperform both Tier 1 and Tier 3 locations, indicating strong growth potential in semi-urban markets.

4. **Fat Content Preferences**: Consumer preferences are balanced between Low Fat and Regular products, with no significant sales disparity.

5. **Rating Consistency**: High average ratings (~3.9) across products indicate strong customer satisfaction.

---

## 💡 Recommendations

- **Targeted Promotions**: Focus marketing efforts on underperforming item categories like Seafood and Breakfast items
- **Outlet Optimization**: Prioritize expansion in Tier 2 cities given their superior sales performance
- **Inventory Management**: Maintain balanced stock of both Low Fat and Regular products
- **Small Outlet Strategy**: Consider small-format store expansion given comparable performance to medium outlets

---

## 🛠️ Technologies Used

| Tool | Purpose |
|------|---------|
| **Python 3.13** | Core programming language |
| **Pandas** | Data manipulation & analysis |
| **NumPy** | Numerical computations |
| **Matplotlib** | Static visualizations |
| **Seaborn** | Statistical data visualization |
| **Jupyter Notebook** | Interactive development |
| **Power BI** | Interactive dashboards |

---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📧 Contact

For questions or feedback, please open an issue in this repository.

---

<p align="center">
  <strong>⭐ Star this repository if you found it helpful!</strong>
</p>
