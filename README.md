# Medicare-Fraud-Analysis

As part of the 2020 Management Analytics datathon organized by University of Toronto, we analyze Medicare claim data to investigate medical insurance Fraud.

<h2> Problem Introduction: </h2>
Medical provider fraud is one of the biggest problems facing the US public healthcare system.
Medicare, one of the largest public insurance programs primarily for people aged 65 or older, accounts for a majority of public healthcare spending and has been the target of many fraud schemes. Extensive records are collected by Medicare on its utilization and costs; however, it is still vulnerable to fraud with fewer than 5% of Medicare claims being audited.<br />

Analysis of Medicare data has shown that many cases of fraud involved physicians and associated providers. They adopt ways in which an ambiguous diagnosis code is used to charge Medicare for unnecessary procedures and drugs. This results in increased costs, raising insurance premiums for all Americans.<br />

<h2> Problem Statement: </h2>
Analysis of Medicare data has shown that many cases of fraud involved physicians and associated providers. They adopt ways in which an ambiguous diagnosis code is used to charge Medicare for unnecessary procedures and drugs. This results in increased costs, raising insurance premiums for all Americans.

We would like to investigate fraud among Medicare providers and provide data-driven recommendations on how to combat Medicare fraud.

Make a recommendation on the criteria that should be used to select which medical providers are audited, given the limited audit resources available.

Some of the most common types of fraud by providers are:
● Billing for services that were not provided
● Duplicate submission of a claim for the same service
● Misrepresenting the service provided
● Charging for a more complex or expensive service than was actually provided
● Billing for a covered service when the service actually provided was not covered

<h2> Dataset: </h2>
The provided dataset contains a sample of anonymized data for beneficiaries, as well as their inpatient and outpatient insurance claims between Dec 2008 and Dec 2009. A separate table of health care provider flags show those who appear to have engaged in fraud.

We examined each variable, then based on description of common types of fraud stated above, we developed hypotheses that might explain relationship between several variables and likelihood of fraud and visualized these potential correlations:

![fraud4](https://user-images.githubusercontent.com/87089936/143789164-ce5044c0-d6a6-4516-97f6-c51ed3ac0062.png)

![fraud3](https://user-images.githubusercontent.com/87089936/143789163-72803a4d-ae72-4f25-8a31-ff76711b4f1f.png)
<h2>Modeling:</h2>

The data that we have is from Medicare Insurance. The answer between yes/no for “whether the claim provider is fraudulent?” is a binary classification task. Therefore, we attempt to perform classification models in Python to detect fraud transactions. We compared different available classifiers including Decision Tree and RandomForest.
<PIC OF MODEL RESULTS>

![fraud2](https://user-images.githubusercontent.com/87089936/143789230-6842c75e-3496-4812-8729-a0b9efc3f7ec.png)

 
![fraud6](https://user-images.githubusercontent.com/87089936/143789231-8498a92d-cd82-4ec4-9fc3-0be8f53f9538.PNG)

The impurity-based feature importance ranks the numerical features to be the most important features. As a result, the non-predictive random_num variable is ranked the second most important. Contrary to our hypothesis, the starting age of patients was ranked the most important feature to determine whether the claim is from a fraud or non-fraud provider. As expected, patient’s average annual deductible amount and claim’s amount reimbursed are important in identifying fraud/ non-fraud.

 <h2>Conclusion and Future Work:</h2>
- We attempted to look at the most common diagnosis codes among claims of Fraud vs Non-fraud providers, and map it with ICD9/10 codes dictionary from the CMS to see potential outlier services on claims of Fraud providers. However, top 20 most frequent diagnosis codes are very similar among two groups (claims of Fraud vs. non Fraud providers):

![fraud5](https://user-images.githubusercontent.com/87089936/143789165-51243e50-0cd3-429a-908f-1f9dc3773d8b.png)

- For future work, we would like to use more Medicare claim data (i.e. Part D on Drug Coverage) to dive deeper into types of fraud including upcoding, provision of unnecessary procedures, and providing services with nurses and staff that should be provided by doctors. 
- If we have more information on the physician’s specialty, type of procedures performed and drug prescribed, we can try to predict the expected medical specialty of a physician based on type and count of procedures performed, then compare it with his/her actual specialty. For example, if the model predicts a physician as a dermatologist but his/her actual specialty is optometrist, he or she might be performing procedures indicating fraud
- Looking at historical data on providers who were identified as “Fraud” and understand their behaviors can be another way. Besides, we would like to implement other classifier algorithms.
