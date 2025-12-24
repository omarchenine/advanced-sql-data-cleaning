# SQL Data Cleaning Portfolio Project

## 📊 Project Overview
This repository showcases SQL data cleaning and database management techniques using real-world datasets. The project demonstrates proficiency in handling messy data, identifying and removing duplicates, standardizing formats, and preparing data for analysis.

## 📁 Repository Contents

### 1. **Data Cleaning.sql**
A comprehensive data cleaning project using the Kaggle Layoffs 2022 dataset. This script demonstrates:
- Duplicate detection and removal using window functions
- Data standardization techniques
- Handling NULL values
- Data type conversions
- Strategic use of staging tables

### 2. **Beginner - Parks_and_Rec_Create_db.sql**
A practice database creation script featuring:
- Database and table creation
- Primary key constraints
- Data insertion
- Sample employee and department data based on the Parks and Recreation TV show

### 3. **layoffs.csv**
Raw dataset containing global layoff information from 2022 ([source: Kaggle](https://www.kaggle.com/datasets/swaptr/layoffs-2022))

## 🎯 Key Skills Demonstrated

### Data Cleaning Techniques
- **Duplicate Removal**: Using `ROW_NUMBER()` with `PARTITION BY` to identify and eliminate duplicate records
- **Data Standardization**: 
  - Trimming whitespace and special characters
  - Consolidating similar category values (e.g., 'Crypto Currency' → 'Crypto')
  - Standardizing country names
- **Date Formatting**: Converting string dates to proper DATE data types using `STR_TO_DATE()`
- **NULL Handling**: Populating NULL values using self-joins and UPDATE statements
- **Staging Tables**: Creating intermediate tables to preserve raw data integrity

### SQL Features Used
- Common Table Expressions (CTEs)
- Window Functions (`ROW_NUMBER()`, `PARTITION BY`)
- Self-joins
- ALTER TABLE operations
- Data type modifications
- Complex WHERE clause filtering

## 🔍 Data Cleaning Process

The layoffs data cleaning follows a systematic 4-step approach:

### 1. Remove Duplicates
```sql
-- Identify duplicates using ROW_NUMBER()
-- Create staging table with row numbers
-- Delete records where row_num > 1
```

### 2. Standardize Data
- Clean industry categories
- Fix country name inconsistencies
- Trim trailing characters
- Consolidate similar values

### 3. Handle NULL Values
- Populate NULL industries using matching company data
- Keep NULL values in numeric fields for analysis purposes

### 4. Remove Unnecessary Data
- Delete rows where both `total_laid_off` and `percentage_laid_off` are NULL
- Drop temporary columns used for processing

## 💡 Best Practices Applied

✅ **Data Integrity**: Always work with staging tables, never modify raw data directly  
✅ **Documentation**: Extensive inline comments explaining each step  
✅ **Verification**: Frequent SELECT queries to verify changes before committing  
✅ **Idempotency**: Use `IF EXISTS` clauses for repeatable script execution  
✅ **Modularity**: Clear separation of concerns (duplicate removal, standardization, etc.)

## 🛠️ Technologies Used
- **SQL (MySQL)**: Primary language for data manipulation
- **Database**: MySQL/MariaDB
- **Dataset**: Kaggle Layoffs 2022 dataset

## 📈 Use Cases
This project is ideal for:
- Data Analyst portfolio demonstrations
- Learning SQL data cleaning techniques
- Understanding real-world data quality issues
- Preparing messy datasets for analysis

## 🚀 How to Use

1. **Setup Database**:
   ```sql
   CREATE DATABASE world_layoffs;
   ```

2. **Import Raw Data**:
   - Import `layoffs.csv` into a table called `layoffs` in the `world_layoffs` database

3. **Run Cleaning Script**:
   - Execute `Data Cleaning.sql` to clean and prepare the data

4. **Optional**: Run the Parks and Recreation database script for practice:
   ```sql
   SOURCE Beginner - Parks_and_Rec_Create_db.sql
   ```

## 📝 Notes
- The original raw data is preserved in the initial `layoffs` table
- All cleaning operations are performed on staging tables (`layoffs_staging`, `layoffs_staging2`)
- The final cleaned dataset is ready for exploratory data analysis (EDA)

## 🎓 Learning Outcomes
Through this project, I've demonstrated:
- Advanced SQL query writing
- Data quality assessment and improvement
- Systematic approach to data cleaning
- Problem-solving with SQL functions
- Database design and management

---

**Author**: Chenine Omar Seifeddine  
**Contact**: [Connect with me on LinkedIn](https://www.linkedin.com/in/chenine-omar-seieddine-042606323)  
**Last Updated**: December 2025
