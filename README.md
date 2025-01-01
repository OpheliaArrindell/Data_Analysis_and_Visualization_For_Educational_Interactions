### Project Overview

This notebook demonstrates the creation, population and analysis of a relational database using SQLite within a Python environment. The purpose of this notebook is to preprocess, analyze and visualize user interaction data, for specific components while ensuring reproducibility and compliance with database setup requirements.


### Database Details

- **Database Name**: `activity_database.db`
- **Database Type**: SQLite (file-based relational database)
- **SQLite Version**: sqlite3
- **Tables Included**:
  - `activity_log`: Contains user activity details.
  - `component_codes`: Maps component identifiers to descriptive names.
  - `user_log`: Stores user-related metadata.


#### Software Requirements
- **Python Version**: 3.7 - 3.12
- **Environment**: Anaconda or standalone Python
- **Jupyter Notebook**

#### Libraries Used
- `pandas`: For data manipulation and preprocessing.
- `numpy`: For numerical operations.
- `sqlite3`: To create and interact with the SQLite database.
- `matplotlib`: For creating static visualizations.
- `seaborn`: For enhanced data visualization.

#### Dataset Files
Ensure the following CSV files are available in the specified paths:
- `ACTIVITY_LOG.csv`
- `COMPONENT_CODES.csv`
- `USER_LOG.csv`

---

### Database Creation and Population

This notebook contains all the necessary steps to set up and populate the SQLite database:

1. **Loading Datasets**:
   The datasets are loaded from CSV files and saved into SQLite using the following code:
   ```python
   conn = sqlite3.connect("activity_database.db")
   activity_log.to_sql("activity_log", conn, if_exists="replace", index=False)
   component_codes.to_sql("component_codes", conn, if_exists="replace", index=False)
   user_log.to_sql("user_log", conn, if_exists="replace", index=False)
   conn.close()
   ```

2. **Database Connection**:
   SQLite establishes a connection locally, using:
   ```python
   conn = sqlite3.connect("activity_database.db")
   ```
   Note: No host or port setup is required for SQLite as it is file-based.

3. **Database Schema**:
   The database includes three main tables, which are populated directly from the input CSV files:
   - `activity_log`
   - `component_codes`
   - `user_log`

4. **Reproducibility**:
   The code is designed to recreate the database from scratch, making it fully reproducible if the input files are provided.


### Steps to Execute

1. **Load and Preprocess Data**:
   Run the cells to load the datasets from their respective CSV files and clean them by removing duplicates, standardizing component names, and handling missing values.

2. **Create and Populate Database**:
   Execute the database setup cell to create the SQLite database and populate it with the cleaned data.

3. **Data Analysis**:
   Run the provided analysis cells to:
   - Calculate summary statistics.
   - Generate visualizations (e.g., correlation heatmaps, scatter plots).

4. **Outputs**:
   All outputs are generated within the notebook, including visualizations and statistical summaries.

---

### Additional Notes

- **Code Reusability**:
  The code is modular and can be adapted for other datasets with minimal changes.
- **Error Handling**:
  Proper error messages are displayed for missing files or failed database operations.
- **Documentation**:
  Comments are included within the code for better understanding of each step.

---

### Example Outputs

#### 1. Database Version
Use the following command to verify the SQLite version:
```python
import sqlite3
print(sqlite3.sqlite_version)
```

#### 2. Correlation Heatmap
A correlation heatmap is generated to identify relationships between components.

#### 3. Summary Statistics
Statistics such as mean, median, and mode are calculated and displayed for each component.

---

### Author

This notebook was created as part of the summative for the AP module to demonstrate the use of relational databases and data analysis in Python. 
