# Netflix Movies and TV Shows: Exploratory Data Analysis (EDA)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-150458?style=for-the-badge&logo=pandas)
![Data Analysis](https://img.shields.io/badge/Sector-Data%20Analysis-critical?style=for-the-badge)

## 📌 Project Overview
This project performs an extensive **Exploratory Data Analysis (EDA)** on the Netflix dataset containing comprehensive information about movies and TV shows available on the platform up to 2024. The core objective is to uncover underlying trends, analyze content distributions, track the growth of content over time, and extract actionable insights regarding content strategies across different geographical regions.

## 📊 Key Insights Captured
* **Content Distribution:** Identified the dynamic split between Movies and TV Shows hosted on Netflix, revealing that Movies constitute the vast majority of content available.
* **Release & Growth Trends:** Analyzed the exponential growth trajectory of titles uploaded between 2015 and 2024.
* **Duration Metrics:** Calculated statistical parameters of content length, showing an average movie duration of approximately ~98 minutes.
* **Maturity Metrics & Genres:** Classified content distribution based on target audience ratings (e.g., TV-MA, TV-14, R) and prominent movie/show genres.

---

## 🛠️ Built With (Technologies & Libraries)
* **Python:** Core programming language.
* **Pandas:** Data cleaning, ingestion, and manipulation.
* **NumPy:** Numerical computations.
* **Matplotlib:** Low-level descriptive plots.
* **Seaborn:** High-level statistical data visualization.

---

## 📂 Dataset Feature Breakdown
The source dataset (`NetFlix.csv`) consists of **7,787 rows and 12 columns** containing the following features:

| Column Name | Data Type | Description |
| :--- | :--- | :--- |
| `show_id` | Object | Unique identifier for each listing |
| `type` | Object | Category of content (`Movie` or `TV Show`) |
| `title` | Object | Title of the movie / show |
| `director` | Object | Director of the content |
| `cast` | Object | Main actors involved |
| `country` | Object | Country where the content was produced |
| `date_added` | Object | Date the title was added to Netflix |
| `release_year` | Integer | Year the title was originally released |
| `rating` | Object | Age rating classification (TV-MA, PG-13, etc.) |
| `duration` | Integer | Duration in minutes (Movies) or seasons (TV Shows) |
| `genres` | Object | Genre classifications |
| `description` | Object | Synopsis text |

---

## 🚀 Step-by-Step EDA Workflow

### 1. Data Ingestion & Inspection
* Initializing data loading via Pandas and checking dataset shape, structural balance, and attributes using `.info()`, `.shape`, and `.dtypes`.

### 2. Missing Value Management & Typcasting
* Missing entries in critical tracking categories (`release_year`, `duration`, `rating`) were securely imputed and standardized. 
* Handled structural nulls safely without disrupting analytical integrity.

### 3. Content Type Distribution Analysis
* Executed a value frequency count highlighting the structural differences between content strategies:
  * **Movies:** 5,377 titles
  * **TV Shows:** 2,410 titles
* Plotted custom statistical count distributions using `seaborn.barplot` using explicit custom styling palettes.

### 4. Advanced Metrics Export
* Automated the statistical export pipeline to compute summary benchmarks—saving insights directly into a generated `netflix_eda_summary.txt` report.

---

## 📈 Sample Visualization & Implementation Code
```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load dataset
df = pd.read_csv('NetFlix.csv')

# Plot content type distribution
plt.figure(figsize=(8, 5))
type_counts = df['type'].value_counts()
sns.barplot(x=type_counts.index, y=type_counts.values, palette='Set2')
plt.title('Content Distribution on Netflix (Movies vs TV Shows)')
plt.ylabel('Count')
plt.xlabel('Content Type')
plt.show()
📥 Getting Started & Installation
Prerequisites
Make sure you have Python installed on your system along with the following packages:

Bash
pip install numpy pandas matplotlib seaborn jupyter
Execution
Clone this repository to your local computer:

Bash
git clone [https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git](https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git)
Place the NetFlix.csv dataset inside the project root folder.

Launch Jupyter Notebook or JupyterLab:

Bash
jupyter notebook
Open and run all cells inside netflix_eda.ipynb.

📄 Output Report
Upon full execution of the notebook, an updated summary text log named netflix_eda_summary.txt is automatically compiled and saved in your working directory, tracking movie duration baselines, recent content spikes, and categorization summaries.
