# Background
We form part of a small group of data scientists who develop various models for companies and businesses. Our clients are looking to expand their knowledge in this field but currently outsource these activities instead of having a fully-fledged in-house team, or are in the process of developing their own in-house capabilities.

# The Ask
The newly formed data science team from one of our clients has asked us to do an independent model development and build using the same underlying dataset they have used. This will allow them to review and establish whether their in-house developed model and approach (steps) are sound. The client has not been prescriptive regarding certain criteria but has given us some guidelines to check against as we build out our model.
 
The main aim of the model is to classify whether a customer will take up the sales offer when cold called. Better discrimination between who will likely take up the offer and who will not can help our client optimize their internal efforts by cold calling the right customers to convert calls into sales.

The secondary aim is to overlay the revenue/cost impacts based on our classification outcomes. This will help evaluate the estimated financial impact of executing campaigns using this model for selection purposes, including yields and costs.

# The Dataset
The dataset contains 20 features (10 numerical and 10 categorical) and one response (binary) variable.
- 35,000 observations available for model development and testing purposes
- The dataset is pipe (|) delimited

## Variable Descriptions

### Numerical Features
| Variable | Description |
|----------|-------------|
| Feature_ae_0 | Customer - Age of the customer |
| Feature_dn_1 | Telematics - Latest call duration (in seconds), measured during last sales call |
| Feature_cn_2 | Telematics - Number of call attempts made to the customer |
| Feature_ps_3 | Telematics - Number of days since last campaign (999 = no previous campaign) |
| Feature_ps_4 | Telematics - Number of call attempts made for previous campaign |
| Feature_ee_5 | Macro variable - Employment variation rate (Quarterly) |
| Feature_cx_6 | Macro variable - Consumer price index (Monthly) |
| Feature_cx_7 | Macro variable - Consumer confidence index (Monthly) |
| Feature_em_8 | Macro variable - 3 month interbank rate (Quarterly) |
| Feature_nd_9 | Macro variable - Number of employees (Quarterly) |

### Categorical Features
| Variable | Description |
|----------|-------------|
| Feature_jd_10 | Customer - Type of employment |
| Feature_md_11 | Customer - Civil status |
| Feature_ed_12 | Customer - Highest level of education |
| Feature_dd_13 | Customer - Has credit facility in default |
| Feature_hd_14 | Customer - Has a home loan |
| Feature_ld_15 | Customer - Has a personal loan |
| Feature_cd_16 | Customer - Contact medium |
| Feature_md_17 | Telematics - Month when last contacted |
| Feature_dd_18 | Telematics - Day of week when last contacted |
| Feature_pd_19 | Performance - Outcome of previous campaign |

### Response Variable
| Variable | Description |
|----------|-------------|
| Response | Did customer take up offer (1 = Yes, 0 = No) |

# Key Considerations
1. Variable Selection
   - Assess relevance of all input variables
   - Examine data distribution and handle outliers
   - Evaluate discriminating power of variables
   - Control for high correlations

2. Data Preparation
   - Address class imbalance in response variable
   - Handle variable scaling
   - Encode categorical variables
   - Consider numerical data binning
   - Split data for training and testing

3. Model Development
   - Implement validation checks during training
   - Model selection criteria
   - Prevent over/underfitting
   - Variable importance assessment
   - Model comparison and optimization
   - Determine classification threshold
   - Interpret confusion matrix
   
Questions to answer:
- Check whether all the input variables are relevant to be considered for use in the model
- Can you explain what your data looks like and whether there are some outliers or corrections which have to be done
- How do you check whether there exist any discriminating power amongst the variables
- How do you control for high correlations amongst your variables


- Do you care whether the response variable classes are balanced or not
- Do you mind having variables all at different scales
- How do you encode categorical data and do you group any of these
- Do you bin your numerical data or not?


- Do you split your data for training and testing?
- Do you perform validation checks as you train your models
- How do you decide which model is the best one to use?
- How do you ensure the model does not over / underfit the data and that it can be used for prediction purposes?

- How do you know which input variables are the most and least important?
- Do you fit different models and how do you decide which one to optimize?
- How do you optimize your selected model? Why did you choose to optimize it that way?
- How do you settle on which cut off hurdle to use in terms of classifying new data into a 1 or 0?
- How do you interpret the confusion matrix obtained by the final model?
