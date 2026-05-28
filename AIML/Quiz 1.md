# 1. Intro
## 1.1 Def
- **Task** (T): The specific problem the system aims to solve (ex: ==classification, prediction, clustering==).
- **Performance Measure** (P): The metric used to evaluate how well the system is performing (e.g., ==accuracy, error rate==).
- Experience (E): The training data, such as examples, labels, or trial-and-error interactions, that the model processes to optimize its internal parameters.
Example:
`A robot driving learning problem: How to drive a robotic automobile autonomously?`
- T: Drive safely to destination
- P: Average distance, safety score
- E: Driving data

## 1.2 ML Process
1. Data preparation
2. Algorithm and model development
3. Final evaluation using the test
4. Integrate into application
---

# 2. Intro 2
## 2.1 Data mining
Process:
- Data gathering
- Data preparation
- Mining the data
- Data Analysis and interpretation

## 2.1 Type of ML
- Supervised Learning: Training with labeled data
	- Classification:
		- Linear
		- Polynomial
	- Regression:
		- k-Nearest Neighbor (kNN)
		- Decision Tree, Random Forest
		- Logistic Regression
		- Naïve-Bayes, Support Vector Machine (SVM)
- Unsupervised Learning: Training with unlabeled data
	- Clustering:
		- K-means
		- Gaussian Mixture Models (GMMs)
- Reinforcement Learning: take action in the environment then received state update and feedbacks
	- ![[Pasted image 20260507185549.png]]

## 2.2 Problem
- Regression problem
	- Predict a continuous value
- Classification problem
	- Predict a category
- Clustering problem
	- Group similar data without predefined labels
- Anomaly detection Problem
	- Detect unusual or abnormal data
- Decision Making and planning problem
---

## 2.3 Pipeline
#### Standard
Data > Train classifier > Model > Prediction
#### Complete
![[Pasted image 20260507203905.png]]
> Data Collection: Web scraping, databases, API's, IoT devices, public datasets
> Data Validation: Ensuring data integrity, accuracy, consistency, verifying
> Data Preprocessing: Cleaning, Integration, Transformation, Reduction  
> Model Training: Choose the most appropriate model for training
> 	- Type of problem: Classification, regression, clustering
> 	- Data characteristic: Size, dimension, linearity
> Model Tuning: Improve model performance through parameter optimization
> 	- Grid Search
> 	- Random Search
> 	- Bayesian optimization
> Model Analysis
> 	- Accuracy
> 	- precision
> 	- Recall
> 	- F1 Score
> 	- etc.
> Model Validation: Evaluating the model performance on validation dataset.
> 	- Detect overfitting and underfitting
> 	- Cross validation
> Model Deployment: take the trained ML and making it to use
> 	- Hosting, running, API's, UI, etc.
> Model feedback: Continuous process of monitoring and maintaining model
---

# 3. Feature Engineering
## 3.1 Feature Creation
Generating new feature according to domain knowledge or observing pattern in the data.
- ==Domain Specific== Example:
	- Healthcare: Calculating "time since last hospital admission" to ==predict== readmission.
	- Finance: Creating features that represent “frequency of transactions in last 24 hours" for fraud detection.
- ==Data Driven== Example:
	- Aggregation: ==Aggregating data== such as calculating the mean, sum, or std.
	- Interaction Features: ==Combining multiple features==, such as dividing the "Total Charge" by "Total Minutes" to create a "Cost per Minute" metric.
- ==Synthetic: Combined existing feature==
	- Mean std median
 
## 3.2 Feature Transformation
- Scaling
	- Adjust range feature to consistency
- Log Transform
	- Handle Skewed distribution
- Encoding
	- Converts categorical data to numerical form
- Binning
	- Group values into intervals 
		- Equal frequency
		- Equal width
		- Smoothing
			- Mean
			- Median
			- Boundaries

## 3.3 Feature Selection
==Choosing a ***subset*** of relevant features from the original dataset==
- ==Filter Method==
	- Correlation Coefficient: Select features highly correlated with the target and minimally correlated with each other.
	- Chi-Square Test: Evaluates relationships between categorical features and the target variable.
- ==Wrapper methods==
## 3.4 FEATURE EXTRACTION
==***Transforming*** the original features into a new, lower dimensional==
- ==Dimensionality Reduction Techniques==:
	- Principal Component Analysis (PCA): Reduces the number of features by projecting data onto a lower-dimensional space, retaining the most variance.
	- Singular Value Decomposition (SVD): Another method to reduce dimensionality by decomposing the data matrix into component matrices.
- ==Text Feature Extraction==: Bag of Words, TF-IDF.
- ==Image Feature Extraction==: CNN
## 3.5 PCA Steps
1. Standardize Data
2. Compute Covariance matrix
3. Compute eigenvectors and eigen values
4. Select top PC's
5. Transform data

## 3.6 Calculation
![[Pasted image 20260509112940.png]]

---

# 4. MODEL EVALUATION, SAMPLING & OPTIMIZATION
