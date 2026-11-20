# credit-risk-analysis
### Author: Hanna Hajdu

## Business Challenges and Project Objectives
<p>
From the lender’s perspective, loan is like an investment. As someone who has been experimenting with different trading strategies, I understand that an investment comes with risk by nature and losses are inevitable. The question is not how can we avoid loss at all costs, but how can we allocate our resources wisely to <b>minimize risk</b> and its impact, while protecting our capital and <b>maximizing our profit</b> in the long run. </p>
<p>
How can an adverse event be predicted? What characteristics are associated with higher risk? Can relevant risk groups be distinguished from one another? I made it the focus of this study to <b>understand the driving factors</b> behind credit risk and use this knowledge to <b>estimate the likelihood</b> of a client defaulting, with an aim to make data <b>interpretable from a business perspective</b> and applicable in decision-making.</p>

### Project Structure
<table>
    <thead>
        <tr>
            <th scope="col">Task</th>
            <th scope="col">Objective</th>
            <th scope="col">Status</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row"><a href="https://github.com/hannabalazs0330-hash/credit-risk-analysis/blob/data-analysis/risk%20analysis/notebooks/eda.ipynb">Exploratory Data Analysis</a></th>
            <td>Understand and enhance the quality of the data, and identify relevant patterns, including risk drivers.</td>
            <td>:heavy_check_mark:</td>
        </tr>
        <tr>
            <th scope="row">Risk Segmentation</th>
            <td>Distribute clients into risk-based categories.</td>
            <td>:construction:</td>
        </tr>
        <tr>
            <th scope="row">Predictive Modelling</th>
            <td>Find interaction patterns and predict the outcome of a loan.</td>
            <td>:construction:</td>
        </tr>
        <tr>
            <th scope="row">Power BI Report</th>
            <td>Visualize the most important findings comprehensively to guide business decision.</td>
            <td>:construction:</td>
        </tr>
    </tbody>
</table>

### Dataset
<p>As credit behaviour data is highly sensitive and unavailable for public use, the analysis uses a synthetic dataset with an analysis framework that can be easily transferred to other datasets as well.</p>
<ul>
<li><b>Dataset:</b> Credit Risk Dataset published by Lao Tse on Kaggle.</li>
<li><b>Source:</b> Kaggle — laotse/credit-risk-dataset <a href="https://www.kaggle.com/datasets/laotse/credit-risk-dataset/data">URL</a> </li>
<li><b>License:</b> CC0: Public Domain </li>
</ul>
<p>The dataset of 32,581 records contains 12 variables including borrower characteristics, loan characteristics, credit history information and loan default status (0 = non-default, 1 = default).</p>

## Exploratory Data Analysis
### Data Overview and Quality Checks
<p>The investigation concluded consistency among categorical variables but identified <b>logically invalid details, missing data, duplicate records</b> and <b>target class imbalanc</b> in the dataset. 
<p>Missing information in employment length data seemed to appear in patterns with other numerical variables such as income, loan amount, loan-to-income ratio and default rate. In order to preserve potentially valuable information for the model, <b>missing values were not removed</b> and will only be handled while preparing the data for model training.</p>
<p>After removing duplicates and invalid data, <b>32,409 records</b> remained.</p>

### Data Analysis
#### Descriptive Statistical Analysis and Outlier Assessment
<p>Descriptive analytics indicated <b>asymmetry in the distribution</b> of most numerical columns and the <b>presence of outliers</b> in the data. The IQR method found that extreme values took up 17.21% of the data, impacted columns were capped in a different version of the dataset and used in visualizations to prevent them from making charts unreadable.</p>
<p>Values appeared to be <b>disproportionately distributed</b> in most categorical variables as well. All further analyses were conducted with the distributions in mind.</p>

#### Investigating Patterns
<p>All variables were tested against each other with non-parametric statistical analysis methods, as a guide to see which relationships are worth further examining. Relevant relationships were visualized to help understand how the variables correlate.</p>

### EDA Most Mentionable Findings
#### Loan Grades
<p><b>Loan grades</b> are meant to be a summative measure, guiding the mitigation of risk associated with loan by strategic interest rate assignment. In accordance with this, loan grades were found to <b>strongly correlate with interest rates, default history</b> and <b>default rates</b>. This finding suggests that loan grade does <b>capture risk-related information and holds predictive value</b>. </p>
<p>The variables that loan grade correlates with do not completely overlap with the ones default rate has relationship with, implying that there may be a chance to refine grade boundaries based on observations.</p>
<img src="risk analysis/images/loan_grades.png">

#### Default Rate
<p>The analysis has successfully <b>narrowed down the scope of factors</b> that potentially play a role in driving risk. The factors that associate with loan status are <b>loan grade, loan-to-income ratio, annual income, home ownership status</b> and <b>interest rate</b>. 
Financial profile related information seemed to have an impact on loan status, as loan-to-income ratios and income details both appeared to correlate with default rates. This finding suggests that other financial factors may also be worth investigating in accordance with defaulting.</p>
<img src="risk analysis/images/def_rate.png">

#### Next Steps Based on Findings
<p>With loan grades identified as risk-based groups, the objective of the planned risk segmentation became even more clear. The analysis will focus on distributing clients into risk categories and the new segments' performance will be checked against loan grades to see if the data at hand is sufficient for optimizing the original grades.</p>
<p>For the predictive purpose of the project, the EDA recognized errors in the dataset that need to be handled before training the model, such as missing values, outliers and small number categories.</p>
