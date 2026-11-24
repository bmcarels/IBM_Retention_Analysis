# IBM_Retention_Analysis

### Project Summary:

This project seeks to determine which groups of employees are most likely to leave in IBM’s fictional HR dataset. The groups analyzed in this project are department, job role, overtime, job satisfaction, years since promotion, tenure band, income band, training sessions last year, job level and job involvement.

### Key Findings:

The categories with the highest attrition rates are: 
1) Sales Representatives (39.8% attrition vs. 16% overall)
2) Employees with low job involvement (33.7% attrition vs. 16% overall)
3) Employees who work overtime (30.5% attrition for 'Yes' vs. 10.4% for 'No')
4) Employees who have been at the company for less than two years (29.8% attrition vs. 16% overall).
Additionally, I calculated a rough estimate of 2.5 million dollars lost from the 237 employees who left IBM based on [The Center for American Progress's (CAP)](https://www.americanprogress.org/article/there-are-significant-business-costs-to-replacing-employees/) attrition cost estimates categorized by salary.

### Datasource:

I used IBM's HR Analytics Employee Attrition dataset for this analysis. The dataset is fictional and created by IBM. The dataset contains about 1,470 employees, 35 columns, and fields like department, job role, overtime, job satisfaction, training sessions, years since last promotion, and whether the person left. The dataset can be found using [this link](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset/data).

### Tools Used:

This project uses the coding languages Python and SQL (PostgreSQL). The Python library pandas and sqlalchemy are also used. The generative AI tool, Claude (Anthropic), was also used for various coding development tasks throughout the project. All AI outputs were tested and verified. All markdown cells, research, analysis, and recommendations are my own work.

### Recommendations: 

Given the results of the analysis, IBM should:
1) Develop retention initatives for sales representatives
2) Promote events that encourage job involvement and seek out employees who have low job involvement
3) Revisit overtime policies
4) Incentivize employees who have been at the company less than two years

### Limitations:
This data is fictional, “attrition” doesn’t separate people who quit from people who were let go, the dataset covers no time period, and DailyRate, HourlyRate and MonthlyRate aren’t explained in the source.

### How to Run the Notebook:
1) **Get the data.** Download the dataset from Kaggle (link above), extract the CSV (WA_Fn-UseC_-HR-Employee-Attrition.csv) and place it in the same folder as the notebook.
2) **Install the required packages.** In a terminal, run:

    *pip install jupyterlab pandas sqlalchemy psycopg2-binary ipython-sql python-dotenv*

3) **Connect a database.** The SQL analysis runs on a PostgreSQL database. In the notebook folder, create a file named .env containing your own connection string:

    *DATABASE_URL=postgresql://username:password@host:port/database_name*

  The .env file is listed in .gitignore, so connection details are never uploaded to GitHub.

4) **Run the notebook.** Open it in JupyterLab and select Run → Run All Cells. The notebook cleans the data in pandas, saves the cleaned table to the database, and then runs the SQL analysis cells.
