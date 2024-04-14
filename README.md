## Project Phoenix: Leveraging Data Analytics for DPDzero Borrower Repayment Optimization

**Introduction**

Project Phoenix simulates a data analysis task undertaken at DPDzero, a data-driven organization that relies on analyst insights to guide decision-making. It provides an opportunity to showcase your ability to leverage data analysis techniques for real-world scenarios, using Jupyter notebooks as the primary tool.

**Data Exploration and Feature Engineering**

1. **Data Acquisition and Preparation:**
   - The first step involves importing essential libraries like pandas, NumPy, and Matplotlib.
   - The loan data, stored in `Data_Analyst_Assignment_Dataset.csv`, is loaded using pandas' `read_csv` function.
   - Data cleaning and pre-processing are crucial to ensure data quality. Missing values are addressed using appropriate techniques (imputation, removal) and inconsistencies are rectified.

2. **Feature Engineering:**
   - New features are derived from existing data to gain deeper insights:
     - **Risk Labels:** Borrowers are categorized into risk groups based on their bounce behavior in the past 6 months.
       - Unknown Risk: New customers.
       - Low Risk: No bounces in the last 6 months.
       - Medium Risk: Max two bounces (excluding the last month).
       - High Risk: All other customers.
     - **Tenure Labels:** Borrowers are segmented based on their loan tenure progress.
       - Early Tenure: Customers within the first 3 months.
       - Late Tenure: Customers nearing the end (within 3 months of closing).
       - Mid Tenure: All others.

**Borrower Segmentation**

1. **Ticket Size Segmentation:**
   - Borrowers are divided into three cohorts (`Low`, `Medium`, `High`) based on their disbursed loan amount. This segmentation ensures that the sum of pending amounts across all cohorts is roughly equal. Techniques like quantile cuts can be employed to achieve this.

**Channel Spend Recommendations**

**Cost Considerations:**

- Different communication channels for borrower outreach incur varying costs:
   - WhatsApp Bot (cheapest): 5 rupees per borrower.
   - Voice Bot: 10 rupees per borrower.
   - Human Calling (costliest): 50 rupees per borrower.

**Channel Suitability:**

- Each channel is deemed appropriate based on specific borrower characteristics:
   - WhatsApp Bot:
     - Customers with a history of good repayment behavior.
     - Customers making their first EMI payments.
     - Customers with low EMI amounts.
   - Voice Bot:
     - Customers conversant in Hindi or English (consideration can be given to metropolitan areas and interest rates as proxies for language proficiency).
     - Customers exhibiting low bounce behavior.
     - Customers with low or medium EMI amounts.
   - Human Calling:
     - This is reserved for scenarios where the previous options are not suitable.

**Recommendation Algorithm:**

- The objective is to maximize repayment rates while minimizing overall spend. Here's a potential approach:
   1. Prioritize the WhatsApp Bot for borrowers who fit its suitability criteria.
   2. If the WhatsApp Bot is not applicable, consider the Voice Bot for suitable borrowers.
   3. Human Calling is used as a last resort for remaining borrowers.

**Conclusion**

Project Phoenix demonstrates the application of data analysis techniques in a loan repayment scenario. By analyzing borrower data, generating new features, and segmenting borrowers, we can develop targeted communication strategies. Prioritizing cost-effective channels while considering borrower characteristics can lead to improved repayment rates and reduced operational costs.

**Further Exploration**

This analysis lays the groundwork for further exploration. We can delve deeper into:

- Analyzing the effectiveness of different communication channels on repayment rates.
- Incorporating additional borrower data (e.g., demographics) for more granular segmentation.
- Developing predictive models to forecast repayment behavior.

By continuously refining our data analysis methods, we can empower DPDzero to make informed decisions and optimize their loan repayment processes.
