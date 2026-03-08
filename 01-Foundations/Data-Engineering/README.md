# Data Engineering for ML/DL 📊

**Duration:** Weeks 5-6 (12 days)  
**Goal:** Master data collection, cleaning, preprocessing, and pipeline building for ML projects

---

## Why Data Engineering Matters

> "Garbage in, garbage out."

- 80% of ML work is data preparation
- Quality data > fancy algorithms
- Production ML requires robust pipelines
- Understanding data is crucial for model performance

---

## 📚 Topics to Master

### Week 5: Data Collection & Cleaning

#### Day 1-2: Data Collection
**Topics:**
- Data sources (APIs, databases, web scraping, files)
- REST APIs and JSON handling
- Web scraping (BeautifulSoup, Scrapy)
- Database connections (SQL, SQLite)
- Reading various file formats (CSV, JSON, Excel, Parquet)

**Learn:**
```python
# APIs
import requests
response = requests.get('https://api.example.com/data')
data = response.json()

# Web Scraping
from bs4 import BeautifulSoup
import requests
html = requests.get('https://example.com')
soup = BeautifulSoup(html.content, 'html.parser')

# SQL
import sqlite3
conn = sqlite3.connect('database.db')
df = pd.read_sql_query("SELECT * FROM table", conn)

# Files
import pandas as pd
df = pd.read_csv('data.csv')
df = pd.read_json('data.json')
df = pd.read_excel('data.xlsx')
df = pd.read_parquet('data.parquet')
```

**Resources:**
- [Requests Documentation](https://requests.readthedocs.io/)
- [Beautiful Soup Tutorial](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
- [Pandas I/O Tools](https://pandas.pydata.org/docs/user_guide/io.html)

**Practice:**
1. Collect data from a public API (e.g., GitHub, OpenWeather)
2. Scrape a website (e.g., Wikipedia tables)
3. Read data from multiple file formats

---

#### Day 3-4: Data Cleaning
**Topics:**
- Handling missing values (drop, impute, forward/backward fill)
- Dealing with duplicates
- Data type conversions
- String cleaning and standardization
- Outlier detection and handling
- Date/time parsing

**Learn:**
```python
import pandas as pd
import numpy as np

# Missing values
df.isnull().sum()  # Check missing
df.dropna()  # Drop rows with missing
df.fillna(df.mean())  # Impute with mean
df.fillna(method='ffill')  # Forward fill
df.fillna(method='bfill')  # Backward fill

# Duplicates
df.duplicated().sum()  # Count duplicates
df.drop_duplicates()  # Remove duplicates

# Data types
df.dtypes  # Check types
df['column'] = df['column'].astype('int64')

# String cleaning
df['text'] = df['text'].str.lower()  # Lowercase
df['text'] = df['text'].str.strip()  # Remove whitespace
df['text'] = df['text'].str.replace('[^a-zA-Z]', '', regex=True)

# Outliers
from scipy import stats
z_scores = np.abs(stats.zscore(df['column']))
df = df[z_scores < 3]  # Remove outliers > 3 std

# Dates
df['date'] = pd.to_datetime(df['date'])
df['year'] = df['date'].dt.year
df['month'] = df['date'].dt.month
```

**Resources:**
- [Pandas Missing Data](https://pandas.pydata.org/docs/user_guide/missing_data.html)
- [Data Cleaning with Python](https://realpython.com/python-data-cleaning-numpy-pandas/)

**Practice:**
1. Clean a messy dataset (Kaggle has many)
2. Handle all types of missing values
3. Detect and remove outliers
4. Standardize text data

---

#### Day 5-6: Exploratory Data Analysis (EDA)
**Topics:**
- Statistical summaries
- Distribution analysis
- Correlation analysis
- Data visualization
- Identifying patterns and anomalies
- Univariate and bivariate analysis

**Learn:**
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Statistical summaries
df.describe()  # Numerical columns
df.info()  # Data types and missing
df['column'].value_counts()  # Categorical

# Distribution
df['column'].hist(bins=50)
sns.distplot(df['column'])
sns.boxplot(data=df, x='column')

# Correlation
correlation_matrix = df.corr()
sns.heatmap(correlation_matrix, annot=True, cmap='coolwarm')

# Relationships
sns.pairplot(df)  # All vs all
sns.scatterplot(x='feature1', y='target', data=df)

# Categorical
sns.countplot(x='category', data=df)
sns.barplot(x='category', y='value', data=df)

# Time series
df.plot(x='date', y='value')
```

**Resources:**
- [Python Graph Gallery](https://python-graph-gallery.com/)
- [Seaborn Tutorial](https://seaborn.pydata.org/tutorial.html)
- [EDA Guide](https://towardsdatascience.com/exploratory-data-analysis-8fc1cb20fd15)

**Practice:**
1. Perform complete EDA on Titanic dataset
2. Create at least 10 different visualizations
3. Document insights discovered
4. Present findings in a notebook

---

### Week 6: Feature Engineering & Pipelines

#### Day 7-8: Feature Engineering
**Topics:**
- Feature scaling (normalization, standardization)
- Encoding categorical variables (one-hot, label, target encoding)
- Feature creation (polynomial, interaction, domain-specific)
- Binning and discretization
- Date/time features
- Text features

**Learn:**
```python
from sklearn.preprocessing import StandardScaler, MinMaxScaler, LabelEncoder, OneHotEncoder
from sklearn.preprocessing import PolynomialFeatures

# Scaling
scaler = StandardScaler()
df_scaled = scaler.fit_transform(df[['feature1', 'feature2']])

# Min-Max normalization
minmax = MinMaxScaler()
df_normalized = minmax.fit_transform(df[['feature1']])

# Label Encoding
le = LabelEncoder()
df['category_encoded'] = le.fit_transform(df['category'])

# One-Hot Encoding
df_encoded = pd.get_dummies(df, columns=['category'])
# OR
from sklearn.preprocessing import OneHotEncoder
ohe = OneHotEncoder(sparse=False)
encoded = ohe.fit_transform(df[['category']])

# Polynomial features
poly = PolynomialFeatures(degree=2, include_bias=False)
poly_features = poly.fit_transform(df[['x1', 'x2']])

# Date features
df['year'] = df['date'].dt.year
df['month'] = df['date'].dt.month
df['day_of_week'] = df['date'].dt.dayofweek
df['is_weekend'] = df['date'].dt.dayofweek.isin([5, 6])
df['quarter'] = df['date'].dt.quarter

# Binning
df['age_group'] = pd.cut(df['age'], bins=[0, 18, 35, 60, 100], 
                          labels=['child', 'young', 'middle', 'senior'])

# Custom features (domain-specific)
df['bmi'] = df['weight'] / (df['height'] ** 2)
df['price_per_sqft'] = df['price'] / df['area']
```

**Resources:**
- [Feature Engineering Guide](https://www.kaggle.com/learn/feature-engineering)
- [Scikit-learn Preprocessing](https://scikit-learn.org/stable/modules/preprocessing.html)
- [Feature Engineering Book](https://www.oreilly.com/library/view/feature-engineering-for/9781491953235/)

**Practice:**
1. Create 10+ new features from existing ones
2. Try different encoding strategies
3. Test feature importance
4. A/B test different feature sets

---

#### Day 9-10: Data Transformation & Pipelines
**Topics:**
- Creating sklearn pipelines
- Custom transformers
- Feature unions
- Column transformers
- Pipeline best practices
- Saving and loading pipelines

**Learn:**
```python
from sklearn.pipeline import Pipeline, FeatureUnion
from sklearn.preprocessing import StandardScaler, OneHotEncoder
from sklearn.compose import ColumnTransformer
from sklearn.base import BaseEstimator, TransformerMixin
import joblib

# Simple pipeline
pipe = Pipeline([
    ('scaler', StandardScaler()),
    ('model', LogisticRegression())
])

pipe.fit(X_train, y_train)
predictions = pipe.predict(X_test)

# Column Transformer (different processing for different columns)
numeric_features = ['age', 'salary']
categorical_features = ['gender', 'city']

numeric_transformer = Pipeline([
    ('scaler', StandardScaler())
])

categorical_transformer = Pipeline([
    ('onehot', OneHotEncoder(handle_unknown='ignore'))
])

preprocessor = ColumnTransformer(
    transformers=[
        ('num', numeric_transformer, numeric_features),
        ('cat', categorical_transformer, categorical_features)
    ])

# Full pipeline
full_pipeline = Pipeline([
    ('preprocessor', preprocessor),
    ('classifier', RandomForestClassifier())
])

full_pipeline.fit(X_train, y_train)

# Custom Transformer
class CustomTransformer(BaseEstimator, TransformerMixin):
    def __init__(self, feature_name):
        self.feature_name = feature_name
    
    def fit(self, X, y=None):
        return self
    
    def transform(self, X):
        X = X.copy()
        X['new_feature'] = X[self.feature_name] ** 2
        return X

# Save pipeline
joblib.dump(full_pipeline, 'pipeline.pkl')

# Load pipeline
loaded_pipeline = joblib.load('pipeline.pkl')
```

**Resources:**
- [Scikit-learn Pipelines](https://scikit-learn.org/stable/modules/compose.html)
- [Custom Transformers Tutorial](https://towardsdatascience.com/custom-transformers-and-ml-data-pipelines-with-python-20ea2a7adb65)

**Practice:**
1. Build end-to-end preprocessing pipeline
2. Create 2-3 custom transformers
3. Handle mixed data types in pipeline
4. Save and load pipelines

---

#### Day 11-12: Advanced Topics & Best Practices
**Topics:**
- Handling imbalanced datasets (SMOTE, undersampling, oversampling)
- Data validation and schema enforcement
- Versioning datasets
- Large dataset handling (chunking, Dask)
- Data quality metrics
- Documentation

**Learn:**
```python
# Imbalanced data
from imblearn.over_sampling import SMOTE
from imblearn.under_sampling import RandomUnderSampler
from imblearn.pipeline import Pipeline as ImbPipeline

# SMOTE
smote = SMOTE(random_state=42)
X_resampled, y_resampled = smote.fit_resample(X, y)

# In pipeline
imb_pipeline = ImbPipeline([
    ('scaler', StandardScaler()),
    ('smote', SMOTE()),
    ('classifier', RandomForestClassifier())
])

# Large files (chunking)
chunk_size = 10000
for chunk in pd.read_csv('large_file.csv', chunksize=chunk_size):
    # Process chunk
    processed = process(chunk)
    # Save or aggregate

# Dask for large data
import dask.dataframe as dd
ddf = dd.read_csv('large_file.csv')
result = ddf.groupby('column').mean().compute()

# Data validation
from pandera import DataFrameSchema, Column, Check

schema = DataFrameSchema({
    'age': Column(int, Check.in_range(0, 120)),
    'salary': Column(float, Check.greater_than(0)),
    'name': Column(str)
})

validated_df = schema.validate(df)

# Data versioning (DVC)
# Install: pip install dvc
# Initialize: dvc init
# Track data: dvc add data/dataset.csv
# Commit: git add data/dataset.csv.dvc .gitignore
```

**Resources:**
- [Imbalanced-learn](https://imbalanced-learn.org/)
- [Dask Tutorial](https://tutorial.dask.org/)
- [DVC Documentation](https://dvc.org/doc)
- [Pandera Guide](https://pandera.readthedocs.io/)

**Practice:**
1. Handle imbalanced dataset
2. Process large file in chunks
3. Create data validation schema
4. Set up DVC for dataset versioning

---

## 🛠️ Essential Tools & Libraries

### Core
```bash
pip install pandas numpy scipy
```

### Data Collection
```bash
pip install requests beautifulsoup4 scrapy
pip install sqlalchemy psycopg2-binary
```

### Visualization
```bash
pip install matplotlib seaborn plotly
```

### Feature Engineering
```bash
pip install scikit-learn category_encoders
```

### Advanced
```bash
pip install imbalanced-learn
pip install dask[complete]
pip install pandera
pip install dvc
pip install great-expectations  # Data quality
```

---

## 📊 Complete Data Engineering Workflow

### Step 1: Data Collection
```python
import pandas as pd
import requests

# Collect from API
response = requests.get('https://api.example.com/data')
raw_data = response.json()
df = pd.DataFrame(raw_data)

# Save raw data
df.to_csv('data/raw/dataset.csv', index=False)
```

### Step 2: Data Cleaning
```python
# Load data
df = pd.read_csv('data/raw/dataset.csv')

# Handle missing values
df = df.dropna(subset=['critical_column'])
df['optional_column'].fillna(df['optional_column'].median(), inplace=True)

# Remove duplicates
df = df.drop_duplicates()

# Fix data types
df['date'] = pd.to_datetime(df['date'])
df['category'] = df['category'].astype('category')

# Remove outliers
from scipy import stats
z_scores = np.abs(stats.zscore(df.select_dtypes(include=[np.number])))
df = df[(z_scores < 3).all(axis=1)]

# Save cleaned data
df.to_csv('data/processed/cleaned_dataset.csv', index=False)
```

### Step 3: EDA
```python
import matplotlib.pyplot as plt
import seaborn as sns

# Statistical summary
print(df.describe())
print(df.info())

# Visualizations
fig, axes = plt.subplots(2, 2, figsize=(15, 10))

# Distribution
df['target'].hist(bins=50, ax=axes[0, 0])
axes[0, 0].set_title('Target Distribution')

# Correlation
sns.heatmap(df.corr(), annot=True, ax=axes[0, 1])
axes[0, 1].set_title('Correlation Matrix')

# Categorical
df['category'].value_counts().plot(kind='bar', ax=axes[1, 0])
axes[1, 0].set_title('Category Counts')

# Relationships
sns.scatterplot(data=df, x='feature', y='target', ax=axes[1, 1])
axes[1, 1].set_title('Feature vs Target')

plt.tight_layout()
plt.savefig('results/eda_report.png')
```

### Step 4: Feature Engineering
```python
from sklearn.preprocessing import StandardScaler, OneHotEncoder

# Date features
df['year'] = df['date'].dt.year
df['month'] = df['date'].dt.month
df['day_of_week'] = df['date'].dt.dayofweek

# Interaction features
df['feature_interaction'] = df['feature1'] * df['feature2']

# Encoding
categorical_cols = df.select_dtypes(include=['object', 'category']).columns
df_encoded = pd.get_dummies(df, columns=categorical_cols)

# Scaling
scaler = StandardScaler()
numeric_cols = df_encoded.select_dtypes(include=[np.number]).columns
df_encoded[numeric_cols] = scaler.fit_transform(df_encoded[numeric_cols])
```

### Step 5: Pipeline Creation
```python
from sklearn.pipeline import Pipeline
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import StandardScaler, OneHotEncoder
from sklearn.ensemble import RandomForestClassifier

# Define columns
numeric_features = ['age', 'salary', 'experience']
categorical_features = ['city', 'department']

# Create transformers
numeric_transformer = StandardScaler()
categorical_transformer = OneHotEncoder(handle_unknown='ignore')

# Preprocessing
preprocessor = ColumnTransformer(
    transformers=[
        ('num', numeric_transformer, numeric_features),
        ('cat', categorical_transformer, categorical_features)
    ])

# Full pipeline
pipeline = Pipeline([
    ('preprocessor', preprocessor),
    ('classifier', RandomForestClassifier(random_state=42))
])

# Train
from sklearn.model_selection import train_test_split
X = df.drop('target', axis=1)
y = df['target']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)

pipeline.fit(X_train, y_train)

# Evaluate
score = pipeline.score(X_test, y_test)
print(f'Accuracy: {score:.3f}')

# Save pipeline
import joblib
joblib.dump(pipeline, 'models/preprocessing_pipeline.pkl')
```

---

## 📝 Practice Projects

### Project 1: Complete EDA Report
**Dataset:** Titanic or House Prices (Kaggle)
**Tasks:**
1. Load and inspect data
2. Handle missing values
3. Create 15+ visualizations
4. Document insights
5. Present findings in notebook

**Deliverable:** Jupyter notebook with complete analysis

---

### Project 2: Data Cleaning Challenge
**Dataset:** Messy dataset from Kaggle
**Tasks:**
1. Identify all data quality issues
2. Fix missing values (try 3 strategies)
3. Handle outliers
4. Standardize formats
5. Validate cleaned data

**Deliverable:** Clean dataset + cleaning script

---

### Project 3: Feature Engineering Competition
**Dataset:** Any regression/classification dataset
**Tasks:**
1. Create baseline with raw features
2. Engineer 20+ new features
3. Test feature importance
4. Compare model performance
5. Document feature rationale

**Deliverable:** Feature engineering notebook + performance comparison

---

### Project 4: End-to-End Pipeline
**Dataset:** Your choice
**Tasks:**
1. Collect data from source
2. Build cleaning pipeline
3. Create feature transformers
4. Build sklearn pipeline
5. Save and version everything
6. Create inference script

**Deliverable:** Complete reusable pipeline

---

## 📚 Learning Resources

### Books
1. **"Python for Data Analysis"** by Wes McKinney
   - Pandas creator's guide
   - Essential reference
   - Free online resources

2. **"Feature Engineering for Machine Learning"** by Zheng & Casari
   - Advanced techniques
   - Real examples

### Online Courses
1. **Kaggle Learn - Data Cleaning**
   - Free, interactive
   - Hands-on exercises
   - [Link](https://www.kaggle.com/learn/data-cleaning)

2. **Kaggle Learn - Feature Engineering**
   - Practical techniques
   - Kaggle datasets
   - [Link](https://www.kaggle.com/learn/feature-engineering)

3. **DataCamp - Data Manipulation with Pandas**
   - Interactive learning
   - Exercises

### Tutorials & Blogs
1. **Real Python - Data Cleaning**
   - [Tutorial](https://realpython.com/python-data-cleaning-numpy-pandas/)

2. **Towards Data Science**
   - Search for "EDA", "Feature Engineering"
   - Many practical examples

3. **Pandas Documentation**
   - [User Guide](https://pandas.pydata.org/docs/user_guide/index.html)
   - Official tutorials

### Video Tutorials
1. **Corey Schafer - Pandas Tutorials** (YouTube)
   - Clear explanations
   - Step-by-step

2. **Keith Galli - Data Science Tutorials**
   - EDA walkthroughs
   - Kaggle competitions

### Datasets for Practice
1. **Kaggle Datasets**
   - [Titanic](https://www.kaggle.com/c/titanic)
   - [House Prices](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)
   - [Data Cleaning Challenge](https://www.kaggle.com/rtatman/data-cleaning-challenge)

2. **UCI ML Repository**
   - Classic datasets
   - Various domains

3. **Data.gov**
   - Real government data
   - Often messy (good practice!)

---

## ✅ Assessment Checklist

After completing this module, you should be able to:

### Data Collection
- [ ] Fetch data from REST APIs
- [ ] Scrape data from websites responsibly
- [ ] Read data from multiple file formats
- [ ] Connect to databases and query data

### Data Cleaning
- [ ] Identify and handle missing values (5+ strategies)
- [ ] Detect and remove duplicates
- [ ] Handle outliers appropriately
- [ ] Convert and validate data types
- [ ] Clean and standardize text data

### EDA
- [ ] Generate statistical summaries
- [ ] Create 10+ types of visualizations
- [ ] Identify patterns and relationships
- [ ] Detect anomalies
- [ ] Document insights clearly

### Feature Engineering
- [ ] Scale and normalize features
- [ ] Encode categorical variables (3+ methods)
- [ ] Create interaction and polynomial features
- [ ] Engineer domain-specific features
- [ ] Extract date/time features

### Pipelines
- [ ] Build sklearn pipelines
- [ ] Create custom transformers
- [ ] Handle mixed data types
- [ ] Save and load pipelines
- [ ] Version control data

### Best Practices
- [ ] Handle imbalanced data
- [ ] Process large datasets efficiently
- [ ] Validate data quality
- [ ] Document code and decisions
- [ ] Write reusable code

---

## 🎯 Week-by-Week Goals

### Week 5
- **Days 1-2:** Collect data from 3 different sources
- **Days 3-4:** Clean 2 messy datasets
- **Days 5-6:** Complete EDA on Titanic dataset
- **Deliverable:** EDA notebook with 15+ visualizations

### Week 6
- **Days 7-8:** Engineer 20+ features for house prices
- **Days 9-10:** Build complete preprocessing pipeline
- **Days 11-12:** Handle imbalanced data + large dataset
- **Deliverable:** End-to-end data pipeline project

---

## 💡 Pro Tips

### Data Collection
- Always save raw data before processing
- Document data sources and collection date
- Check API rate limits
- Respect robots.txt when scraping

### Data Cleaning
- Make copies before modifying
- Track all transformations
- Validate after each step
- Don't delete outliers blindly - understand them first

### EDA
- Start simple, then go deeper
- Look for patterns AND anomalies
- Visualize, don't just calculate
- Document surprising findings

### Feature Engineering
- Domain knowledge is key
- Test features individually
- Remove correlated features
- Keep it simple initially

### Pipelines
- Make pipelines early, not late
- Test on small subset first
- Save intermediate outputs for debugging
- Version control everything

---

## 🔧 Common Issues & Solutions

### Issue: Large CSV won't load
```python
# Solution: Use chunking
chunks = []
for chunk in pd.read_csv('large.csv', chunksize=10000):
    processed = process(chunk)
    chunks.append(processed)
df = pd.concat(chunks)

# Or use Dask
import dask.dataframe as dd
ddf = dd.read_csv('large.csv')
```

### Issue: Memory error during processing
```python
# Solution: Process in batches and use efficient dtypes
df['category'] = df['category'].astype('category')  # Less memory
df['int_col'] = pd.to_numeric(df['int_col'], downcast='integer')
```

### Issue: Pipeline fails on new data
```python
# Solution: Handle unknown categories
from sklearn.preprocessing import OneHotEncoder
encoder = OneHotEncoder(handle_unknown='ignore')
```

### Issue: Inconsistent scaling in production
```python
# Solution: Save scaler with model
import joblib
joblib.dump(scaler, 'scaler.pkl')
# Load and use same scaler
scaler = joblib.load('scaler.pkl')
new_data_scaled = scaler.transform(new_data)
```

---

## 📅 Daily Study Schedule

### Hour 1: Theory & Reading
- Read documentation or tutorial
- Watch video if available
- Take notes in LEARNING_NOTES.md

### Hour 2: Hands-On Practice
- Code along with tutorial
- Try examples on your data
- Experiment and break things

### Hour 3: Project Work
- Apply to real dataset
- Build something reusable
- Document your code

### Review (30 min)
- Update PROGRESS.md
- Commit code to Git
- Plan tomorrow's topics

---

## 🎓 Next Steps

After mastering data engineering basics:
1. Move to [02-Classical-ML](../../02-Classical-ML/README.md)
2. Apply these skills to every ML project
3. Keep building your data pipeline library
4. Learn advanced tools (Airflow, Spark) later

---

**Remember:** Data engineering is the foundation of all ML. Master it now, benefit forever! 📊✨
