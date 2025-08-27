# Alzheimer's Disease Risk Analysis 

# Project Overview 
Alzheimer’s disease is a progressive neurodegenerative condition that significantly impacts aging 
populations. Early identification of risk factors can improve care outcomes and resource planning. 
This Power BI project analyzes real-world data to identify predictors of Alzheimer's disease based on 
demographics, cognitive scores, lifestyle, and family history. 
By leveraging interactive visualizations, the dashboard enables dynamic risk profiling and supports 
data-informed early detection strategies. 
___________________________ 

# Dashboard Highlights 
The dashboard allows for filtering, drilling down, and trend exploration across key variables: 
�
�
 Education Level 
�
�
 Age Groups 
�
�
 Family History of Alzheimer’s 
�
�
 MMSE (Mini-Mental State Examination) Scores 
�
�
 Functional Assessment Scores 
�
�
 Lifestyle Behaviors 

 History of Head Injury 
> 
�
�
 Dynamic slicers and visual charts reveal high-risk groups and predictor patterns in an intuitive 
interface. 
__________________________ 
�
�
 Key Insights 
1. Education & Diagnosis 
Individuals with lower educational attainment are more likely to be diagnosed, regardless of gender. 
2. Age Factor 
People aged 70+ show a significantly higher risk of developing Alzheimer’s. 
3. Family History 
23% of patients with a diagnosis also reported a family history, suggesting a notable genetic 
predisposition. 
4. Lifestyle Risk 
86% of patients with unhealthy lifestyles were later diagnosed, indicating strong behavioral linkage. 
5. Cognitive Assessment (MMSE) 
MMSE scores correlate with diagnosis at -0.23, suggesting moderate predictive value. 
Patients with low MMSE scores showed significantly higher diagnosis rates. 
6. Functional Assessment 
Stronger indicator than MMSE, with a correlation of -0.36. 
Lower scores are directly associated with Alzheimer’s diagnosis. 
7. Combined Cognitive Deficit 
66% of patients with poor cognitive scores received a diagnosis, reinforcing the predictive reliability of 
combined cognitive assessments. 
8. Head Injury Impact 
Weak correlation of -0.024 with diagnosis — possibly a compounding but not standalone factor. 
___________________________ 
❓
 Exploratory Questions 
1. Does a bad lifestyle increase the chances of getting Alzheimer's?  If yes, what are the odds of being 
diagnosed before a certain age? 
Yes, lifestyle appears to have a **strong influence** on the likelihood of being diagnosed with 
Alzheimer’s. - Among individuals with a **bad lifestyle score** (scores 3 or 4), **86% were diagnosed with 
Alzheimer’s**, compared to just ~38% in the good lifestyle group (scores 1 or 2). - Notably, **41% of bad-lifestyle patients were diagnosed before the age of 70**, indicating that 
unhealthy behavior may **accelerate cognitive decline**, leading to **early-onset Alzheimer’s**. - While Alzheimer’s is more common after 70, lifestyle seems to **lower the threshold for onset**. 
> 
�
�
 *Conclusion*: Bad lifestyle increases both the **likelihood** and **early onset** risk of 
Alzheimer’s. It may act as a **trigger** in predisposed individuals, especially when combined with other 
risk factors like poor functional ability. 
2. Which is a better predictor of Alzheimer’s: MMSE or Functional Assessment?  Can we improve 
diagnostic accuracy by combining both? 
Both MMSE and Functional Assessment (FA) are useful screening tools, but FA shows **stronger 
alignment** with Alzheimer’s diagnosis in this dataset. - **Correlation with diagnosis**: - MMSE: `-0.23` - Functional Assessment: `-0.36` - Patients with: - **Low FA only** → 69% diagnosed   - **Low MMSE only** → 54% diagnosed   - **Both low** → 77% diagnosed 
> 
�
�
 *Conclusion*: Functional Assessment appears to be the **better standalone predictor**, but 
combining it with MMSE **increases diagnostic accuracy**. This supports the use of **multi-metric 
screening** in early-stage diagnosis efforts. 
___________________________ 
�
�
 Recommendations 
1. Patients with low functional assessment scores and poor lifestyle habits should be prioritized for 
screening and intervention. 
 
2. Combined use of MMSE + functional scores improves early diagnostic accuracy. 
 
3. Promote healthy lifestyle behaviors (sleep, activity, nutrition) to reduce modifiable risk. 
 
4. Although head injuries show a weak direct linkage, consider them in multi-factorial assessments 
 
___________________________ 
 
�
�
 Tools & Technologies Used 
 
Power BI – Dashboard design, data modeling, interactivity 
 
Microsoft Excel – Data cleaning and preparation 
 
DAX – Custom metrics, correlation logic, percentage calculations 
 
Domain Research – Alzheimer's risk factors, MMSE thresholds, functional assessment scoring 
 
___________________________ 
 
Key formulae and calculations (most relevant ones) 
 
**MMSE vs Diagnosis =  
VAR X_Mean = AVERAGE(alzheimers_data[MMSE]) 
VAR Y_Mean = AVERAGE(alzheimers_data[Diagnosis]) 
VAR n = COUNTROWS(alzheimers_data) 
VAR Numerator = 
    SUMX( 
        alzheimers_data, 
        (alzheimers_data[MMSE] - X_Mean) * (alzheimers_data[Diagnosis] - Y_Mean) 
    ) 
VAR Denominator = 
    SQRT( 
        SUMX(alzheimers_data, POWER(alzheimers_data[MMSE] - X_Mean, 2)) * 
        SUMX(alzheimers_data, POWER(alzheimers_data[Diagnosis] - Y_Mean, 2)) 
    ) 
RETURN 
    DIVIDE(Numerator, Denominator)** 
 
**BadLifestyle % = 
VAR TotalRows = COUNTROWS(alzheimers_data) 
VAR BadLifestyle34 = 
    CALCULATE( 
COUNTROWS(alzheimers_data), 
alzheimers_data[Bad lifestyle] IN {2, 3, 4} 
) 
RETURN 
DIVIDE(BadLifestyle34, TotalRows, 0)** 
___________________________ 
Detailed Visual analysis  
�
�
 Chart: Age vs diagnosis  
�
�
 Chart: Education vs diagnosis  
 
 
 
 
�
�
 Chart: MMSE, Functional Assessment & Lifestyle 
 
 
 
___________________________ 

 Analytical Techniques 
Correlation analysis (Pearson) between cognitive tests and diagnosis outcome 
Cross-tab filtering by demographic segments (age + education + family history) 
Categorical scoring for lifestyle index and risk flagging 
Logical intersections (e.g., low MMSE + poor lifestyle + family history) for compound risk detection 
____________________________ 
✅
 Summary 
This project demonstrates how clinical and behavioral datasets can be transformed into actionable risk 
intelligence for early detection of Alzheimer’s disease. The dashboard empowers researchers and care 
teams to explore risk drivers interactively, supporting data-driven decisions in preventive neurology, 
public health, and geriatric care planning. 
___________________________ 

�
 LinkedIn  
