You will get an error if you try to plug categorical variables into most machine learning models in Python without preprocessing them first

# Approaches
- Drop the variables
- Ordinal encoding
- One-Hot Encoding

## Drop the Variables
Easiest approach if the columns don't have any useful information

## Ordinal Encoding
1. Assign each unique value to different categories
2. This approach assumes an ordering of the categories (Could be a pro and con)
3. Ordinal encoding works well with tree based models like Decision trees and Random Forests

## One-Hot Encoding
1. One-hot encoding creates new columns indicating the presence (or absence) of each possible value in the original data. 
2. Unlike Ordinal Encoding, One Hot Encoding doesn't assume an ordering/ranking of categories
3. Thus, you can expect this approach to work particularly well if there is no clear ordering in the categorical data
4. One-hot encoding generally does not perform well if the categorical variable takes on a large number of values

### Checking Cardinality of Categorical and Numerical Variables

```
low_cardinality_cols = [cname for cname in X_train_full.columns if X_train_full[cname].nunique() < 10 and 
                        X_train_full[cname].dtype == "object"]
                        
numerical_cols = [cname for cname in X_train_full.columns if X_train_full[cname].dtype in ['int64', 'float64']]                        
```
