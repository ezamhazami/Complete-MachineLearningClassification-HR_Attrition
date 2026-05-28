My End to End Machine Learning Lifecyle 
Note for myself,
Machine Learning Lifecyle
1) Requirement - check objectives of the dataset, what research do you want to do, whats the outcome
2) Data Ingestion / inspection - load data to local machine, inspect the data using :
   i) .head() - overview of the dataset ii) .describe() - statistical view - to see mean, max, std, min, count
   iii) .shape - to check how many row, columns iv) dtypes - to see feature types
   v) .isna.sum() - check null value vi) .duplicated().sum() - check duplicates
   vvi) .nunique() - check unique values - can identify useless columns
3) Exploratory Data Analysis - here are the main :
   i) .hist - histograme distributions - to check skewed , skewed to the right means majority at left
   ii) sns.boxplot - to see median, quartile and outlier
   iii) Scatterplot, regplot - to see relatiomship between 2 numerical variable, upword correl
   iv) Correlation Heatmap - see how strong the relationship , 0.5 above are strong relationship
4) Data Cleaning - clean full dataset bfr splitting
   i) fix datatypes ii) handle duplicates
   iii) Outlier detection IQR method , if <500 use Winsorising, Z-score method
5) Feature Engineering - ways to make feature more impactful
6) Model Training (always split before preprocessing to avoid data leakage) - there are 3 types of model training
   i) Standard train / test split + stratify=y (to keep class ratios equal)
   ii) train / validation / test
   iii) Cross validation (stratified KFold) - use for small dataset <1000 rows
7) Model Preprocessing (train - fit_transform, test - transform ONLY - to avoid data leakage)
   i) Imputation - we can input via SimpleImputer, fillna, KNNImputer(finds similar rows to estimate missing value (slower, often better))
       - (median for numerical, mode for categorical)
   ii) Encoding
       - Label Encoding = for binary / tree based model
       - Ordinal Encoding = use for rankings like low,mid,high
       - One Hot Encoding = no order, best for linear models
       - pd.get_dummies = easy fun to use
   iii) Feature Scalling
       - Standard Scaler(), best for linear model 
       - MinMaxScaler(), best for neural nets
       - RobustScaler(), Best for extreme outliers
   iv) Balance Dataset
       print(y_train.value_counts(normalize=True)), If minority class < 15% → you likely need balancing , if minority 20% - 50% -> try class_weight
       - Class weight
       - SMOTE - create a synthethic data , minority oversampling
       - SMOTETomek - Oversample minority and undersample majority 
   
   
   
   
   
   
