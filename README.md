# MARKET-BASKET-ANALYSIS-WITH-APRIORI-ALGORITHM
![market basket image](https://github.com/user-attachments/assets/31ca88aa-df52-4b87-ac43-3ba4d68426ad)

# Introduction

Building upon insights gained from our previous customer segmentation analysis, which identified distinct customer segments based on spending patterns and demographics, this project delves into market basket analysis using the Apriori algorithm. The objective is to analyze purchasing patterns among our previously identified premium customer segments, such as high spenders and high-income, low-spend individuals, to discover associations between store items. By understanding these item associations, the company aims to implement strategic merchandising decisions and personalized loyalty programs that further enhance customer engagement and drive sales growth.

Association Rule Learning (ARL) enables us to identify frequently co-purchased items, providing insights that can be leveraged for in-store layout optimization, targeted promotions, and personalized product recommendations for each customer segment.

# Business Problem

In continuation of my prior work on customer segmentation, the company has expressed interest in capitalizing on identified premium customer segments by increasing their purchase volume and enhancing retention through strategic product placement and loyalty incentives. The goal is to understand the relationships between items frequently bought together, thereby enabling the company to:

- Optimize store layout to encourage additional purchases from premium segments.
  
- Tailor loyalty programs to incentivize the purchase of associated items.
  
- Enhance customer satisfaction by offering bundled promotions and discounts on frequently paired items.
  
By achieving these goals, the company can improve its overall sales while strengthening loyalty among high-spending customers.

# Problem Encountered: Data Cleaning and Formatting Issues
During the project, I encountered inconsistencies in the dataset, particularly in column naming conventions, with some column names in uppercase, others in lowercase, and some containing spaces. These inconsistencies led to data processing errors when feeding the data into the Apriori model.

# Resolution: 

To address this issue, I standardized all column names by converting them to lowercase and replacing any spaces with underscores. Additionally, I formatted the itemdescription column to remove extra spaces and ensure consistent naming across all item entries. The following code snippets were used to achieve these corrections:

# Standardizing column names
    df.columns = df.columns.str.lower().str.replace(' ', '_')

# Cleaning the itemdescription column
    df['itemdescription'] = df['itemdescription'].astype('str').apply(lambda x: re.sub(r'\s+', ' ', x).strip())

# Key Learnings from the Project

Understanding Key Metrics in Association Rule Mining:
- Support: The frequency of occurrence of an itemset within transactions, which helps in identifying common item combinations.
- Confidence: The likelihood that an item is bought when another item is also bought, aiding in establishing a stronger predictive relationship between items.
- Lift: A metric that evaluates the strength of the rule by comparing confidence with random chance; a lift greater than 1 indicates a positive association.

 ![image 2](https://github.com/user-attachments/assets/cfaf00a0-a766-408f-aa8d-351ab8b0a5bf)

# Data Preparation for Apriori:

Converting the dataset into a transaction matrix format is crucial for enabling the Apriori algorithm to detect frequent itemsets effectively. 

# Evaluating and Interpreting Rules:

Sorting rules by lift was essential to prioritize the most impactful associations. This process enabled the identification of the strongest item associations, which can be directly applied to enhance customer experiences through improved merchandising and marketing strategies.

# Model Implementation

- Generating Frequent Itemsets:
Using the Apriori algorithm, frequent itemsets were generated with a minimum support threshold of 6%. This threshold ensures that only itemsets appearing in at least 6% of transactions are considered, focusing the analysis on commonly co-purchased items.
- Generating Association Rules:
After identifying frequent itemsets, the association_rules function was applied with a minimum confidence threshold of 5%, filtering the rules to those with a higher probability of occurrence.
- Sorting Rules by Lift:
The rules were then sorted by lift in descending order to prioritize relationships with the strongest associations. This approach ensures that the company can leverage the most impactful item pairings to improve in-store product placement and targeted promotions.

# Key Findings and Recommendations
  - Yogurt and Whole Milk:

- Insight: Yogurt frequently appears in association with "whole milk" and "other vegetables."
- Action: Promote yogurt with whole milk and fresh produce sections to enhance cross-selling opportunities, especially for health-conscious customer segments.

  - Rolls/Buns and Sausage:

- Insight: The association between rolls/buns and sausage suggests common breakfast or snack items.
- Action: Bundle these items in promotions targeting customers in the "high spender" and "moderate spender" segments, particularly during mornings or weekends.

  - Optimizing Store Layout for High-Income, Low-Spend Customers:

- Insight: High-income, low-spend customers are more likely to add additional items if positioned strategically near frequently purchased items, such as "whole milk" and "yogurt."
- Action: Position complementary products close to staple items like whole milk to encourage incremental purchases, thereby increasing basket value for low-spend customers.

# Conclusion
By implementing association rule learning on historical transaction data, this project identifies key product associations that align with the previously identified customer segments. This analysis allows the company to:

- Design personalized marketing campaigns targeting high-spend and high-income segments.
- Develop loyalty programs centered around frequently purchased item pairs to encourage repeat purchases.
- Optimize store layout to maximize the visibility of associated items, driving higher sales.
- 
These actionable insights, in continuation of the customer segmentation analysis, provide a foundation for strategic retail decisions that enhance customer engagement and boost overall profitability.

For further details, please refer to the Market Basket Analysis Notebook in the project repository.
![thank you](https://github.com/user-attachments/assets/a299793f-63fa-4ebe-a540-98fc7c5bcd22)




