# AI Development Plan Assistant

### Project Summary:
The AI Development Plan Assistant (AI Agent) was created with the intention to efficiently make reliable recommends to address factors linked to attrition in IBM's fictional HR dataset. The AI Agent is an automated tool that outputs two learning suggestions, one stretch project, and a short conversation starter for managers based on specific job related information from a provided dataset. Fourteen profiles (seven employees who left and seven who stayed) were randomly selected from the dataset and used for each iteration of the project. 

***Development***
The final version of this project contained many rules that followed complex logic. Since a typical AI model would likely struggle with this, I used AI to develop a python script that applied these rules to every employee profile. The python script produced concrete outputs that the AI agent could easily follow. The AI agent was ultimately only responsible for writing appropriate wording since the python script handled the complex logic. This allowed my final version to be the strongest and most reliable.

### Key Findings:
From version one to version three we achieved a 6.16% increase in relevance, 12.87% increase in accuracy, and a 27.23% increase in actionability for all AI outputs. After the first version, relevance scored a 4.71/5, accuracy a 4.43/5, and actionability a 3.93/5. All category scores reached a 5/5 by the third version. I independently reviewed all plans and scored them using a written rubric.

In addition to this, three profiles were tested and showed clear age-based differences in all 3 profiles. In one clear and one possible instance, the AI output displayed gender based differences on identical profiles. These results lead me to recommend excluding demographic data from the AI prompt and encouraging a person to review each plan.

### Datasource:
I used IBM's HR Analytics Employee Attrition dataset for this analysis. The dataset is fictional and created by IBM. The dataset contains about 1,470 employees, 35 columns, and fields like department, job role, overtime, job satisfaction, training sessions, years since last promotion, and whether the person left. The dataset can be found using this [link](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset/data).

### Tools Used:
This project uses the coding languages Python and SQL (PostgreSQL) and the Python libraries pandas, google-genai, pydantic, openpyxl, and python-dotenv. Jupyter Notebook and Excel were used for scoring purposes. The generative AI tool, Claude (Anthropic), was also used for various coding development tasks throughout the project. All AI-assisted code was tested and verified. The generative AI model, gemini-3.5-flash-lite, was prompted and used for all iterations in this project. This project does *not* use real employee information. All markdown cells, research, analysis, and recommendations are my own work.

### Recommendations:
Given the results of the analysis, IBM should:
1) Have a human review every plan before it is used.
2) Re-test for demographic biases whenever the AI model or prompt changes.
3) Create a small pilot study with manager to test whether the plan affects retention.
4) Consider developing a second, relational dataset with information on an employee's past training sessions so the AI model could use that guide to suggest the next training topic.

### Limitations:
1) A small sample of 14 randomly selected profiles was used with only three profiles used in the bias test
2) I scored all outputs and developed a rubric that is partly subjective
3) One AI model was used and tested on the free tier
4) Rule thresholds in version three were developed and chosen by myself (for example, more than 3 years since promotion is the third tier choice for learning suggestions)
5) The data is fictional and has no real-world impact

### How to Run the Notebook:
1) Get a Gemini API key. Sign in to [Google AI Studio](https://aistudio.google.com/welcome), click Get API key → Create API key and copy the key. A free-tier key works.
2) Install the required packages. In a terminal, run:

    *pip install jupyterlab pandas google-genai pydantic openpyxl python-dotenv*
   
4) Add your API key. In the notebook folder, create a file named .env containing:

    *GEMINI_API_KEY=your-key-here*

    The .env file is listed in .gitignore, so the key is never uploaded to GitHub.

5) Add the data. Place employee_clean.csv in the same folder as the notebook. It's created by the analysis notebook.
6) Run the notebook. Open it in JupyterLab and select Run → Run All Cells. Each version's plans are saved as CSV files (for example, development_plans_v3.csv).

Note: On the free tier, requests sometimes fail when Google's servers are busy. The notebook retries each request up to 5 times. If a model is unavailable, check Google AI Studio for current free models and change the model= name in the code.
