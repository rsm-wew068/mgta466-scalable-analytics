# MGTA 466: Scalable Analytics - Programming Assignments

This repository contains the programming assignments for MGTA 466: Scalable Analytics course. Each assignment builds upon the previous ones, teaching students progressively more advanced concepts in distributed computing, big data processing, and cloud-based analytics.

## 📁 Repository Structure

### **Included Files:**
- **Notebooks**: All Jupyter notebooks with complete solutions
- **Small Output Files**: Sample results showing assignment completion
- **Small Datasets**: Wine classification and salary datasets
- **Documentation**: Comprehensive README with data usage matrix

### **Excluded Files (Large Data):**
- `BookReviews_1M.txt` (209MB) - Available from course materials
- `Airline_2016_2018.csv` (2.3GB) - Available from course materials
- `results.txt` (78MB) - Generated output file

*Note: Large data files are excluded to keep repository size manageable. These files are available through the course materials and cloud storage.*

## Overview

The course covers five main programming assignments that progress from basic PySpark operations to advanced machine learning on cloud platforms:

1. **PA1**: PySpark and HDFS Basics
2. **PA2**: Word Count Analysis with Performance Testing
3. **PA3**: Exploratory Data Analysis on Airline Data
4. **PA4**: Cloud Computing with Amazon EMR
5. **PA5**: Machine Learning with XGBoost on SageMaker

---

## Programming Assignment 1 (PA1): PySpark and HDFS Setup

**File**: [`PA1_Starter.ipynb`](./PA1_Starter.ipynb)

### Purpose
Introduction to PySpark and Hadoop Distributed File System (HDFS) for distributed data processing.

### Learning Objectives
- Set up and work with PySpark
- Read from and write to HDFS
- Perform basic Spark DataFrame operations
- Understand distributed computing workflows

### Key Tasks
1. **Setup**: Copy data files to HDFS
2. **Spark Session**: Initialize PySpark with local configuration
3. **Data Loading**: Read 1M book reviews from HDFS
4. **Data Examination**: Explore DataFrame schema and content
5. **Data Transformation**: Extract first 100 characters and convert to lowercase
6. **Data Export**: Save results back to HDFS and local filesystem

### Technical Details
- **Data Source**: `BookReviews_1M.txt` (1 million book review records)
  - **Format**: Plain text file with book review content
  - **Size**: ~209MB
  - **Content**: Customer book reviews from Amazon
  - **Structure**: Each line contains a complete book review text
- **Processing**: Text extraction and transformation
- **Output**: Processed text file with transformed data
- **Points**: 7.5 total points

---

## Programming Assignment 2 (PA2): Word Count Analysis

**File**: [`PA2_Starter.ipynb`](./PA2_Starter.ipynb)

### Purpose
Advanced PySpark operations for text processing and performance analysis across different core configurations.

### Learning Objectives
- Advanced text processing with PySpark
- Performance analysis across different configurations
- Data filtering and word frequency analysis
- Scalability testing and optimization

### Key Tasks
1. **Data Cleaning**: Remove punctuation and convert to lowercase
2. **Word Processing**: Split sentences into words and filter by length (5-10 characters)
3. **Frequency Analysis**: Count word occurrences and sort by frequency
4. **Performance Testing**: Measure execution times across 1, 2, and 4 cores
5. **Data Export**: Save top 100 words to CSV format

### Technical Details
- **Data Source**: Same `BookReviews_1M.txt` (1 million reviews)
  - **Format**: Plain text file with book review content
  - **Size**: ~209MB
  - **Content**: Customer book reviews from Amazon
  - **Structure**: Each line contains a complete book review text
- **Processing**: Word extraction, filtering, counting, and sorting
- **Performance Analysis**: 3 trials each for 1, 2, and 4 cores
- **Output Files**: `100_words.csv`, `exec_times.csv`
- **Points**: 15 total points

---

## Programming Assignment 3 (PA3): Airline Data EDA

**File**: [`PA3_Starter.ipynb`](./PA3_Starter.ipynb)

### Purpose
Exploratory Data Analysis on real-world airline data using PySpark and matplotlib for visualization.

### Learning Objectives
- Complex data schema management
- Real-world data cleaning and transformation
- Advanced data visualization
- Statistical analysis of operational metrics

### Key Tasks
1. **Schema Management**: Define complex data types for airline data
2. **Data Cleaning**: Remove cancelled flights and missing values
3. **Feature Engineering**: Extract day of week and month from dates
4. **Airport Analysis**: Analyze top 10 origin airports and flight patterns
5. **Carrier Analysis**: Study smallest carriers and delay patterns
6. **Visualization**: Create bar charts and pie charts

### Technical Details
- **Data Source**: `Airline_2016_2018.csv` (3 years of US airline data)
  - **Format**: CSV file with airline flight records
  - **Size**: ~823MB
  - **Content**: US domestic airline flight data from 2016-2018
  - **Structure**: 6.6M+ records with flight details, delays, cancellations
  - **Key Fields**: FL_DATE, OP_CARRIER, ORIGIN, DEST, DISTANCE, ARR_DELAY, CANCELLED
- **Features**: Flight dates, carriers, origins, distances, delays
- **Visualizations**: Bar charts, pie charts with specific formatting
- **Output Files**: `50_rows.csv` with filtered data
- **Points**: 20 total points

---

## Programming Assignment 4 (PA4): Cloud Computing with Amazon EMR

**File**: [`PA4_Starter.ipynb`](./PA4_Starter.ipynb)

### Purpose
Cloud-based distributed computing using Amazon EMR (Elastic MapReduce) for large-scale data processing.

### Learning Objectives
- Cloud computing with AWS EMR and S3
- Scalability analysis across different cluster configurations
- Performance measurement and optimization
- Big data processing in the cloud

### Key Tasks
1. **Cloud Setup**: Upload data to S3 and configure EMR clusters
2. **Data Processing**: Word count analysis on 4M reviews
3. **Performance Testing**: Compare 1M vs 4M datasets across different cluster sizes
4. **Scalability Analysis**: Test 1 master + 1 worker vs 1 master + 3 workers
5. **Cloud Management**: Create, configure, and terminate clusters

### Technical Details
- **Data Sources**: 
  - **BookReviews_1M.txt**: Local file (~209MB, 1M reviews)
  - **BookReviews_4M.json**: Cloud-hosted on S3 (`s3://mgta466-w25/data/BookReviews_4M.json`)
    - **Format**: JSON format with structured review data
    - **Size**: ~4M book review records
    - **Content**: Amazon book reviews with reviewText field
- **Cloud Platform**: Amazon EMR with S3 storage
- **Cluster Configurations**: Various master/worker node combinations
- **Output Files**: `50_words.csv`, `exec_times.csv`
- **Points**: 15 total points

---

## Programming Assignment 5 (PA5): Machine Learning with XGBoost

**Files**: [`PA5_Starter.ipynb`](./PA5_Starter.ipynb), [`PA5_Inference.ipynb`](./PA5_Inference.ipynb)

### Purpose
End-to-end machine learning pipeline using XGBoost on Amazon SageMaker for salary prediction.

### Learning Objectives
- Complete ML pipeline from data to deployment
- Cloud ML services with Amazon SageMaker
- Advanced gradient boosting for regression
- Hyperparameter tuning and model optimization
- Real-time inference and model evaluation

### Key Tasks

#### PA5_Starter.ipynb (Training Pipeline)
1. **Data Preparation**: Load, clean, and split salary prediction data
2. **Feature Engineering**: Select relevant features and handle correlations
3. **Model Training**: Train XGBoost regression model on SageMaker
4. **Model Deployment**: Deploy model as real-time endpoint
5. **Hyperparameter Tuning**: Optimize model parameters using SageMaker Tuner

#### PA5_Inference.ipynb (Inference & Evaluation)
1. **Model Inference**: Use deployed endpoints for predictions
2. **Performance Evaluation**: Calculate RMSE on test data
3. **Model Comparison**: Compare base vs tuned model performance
4. **Resource Management**: Clean up endpoints and resources

### Technical Details
- **Problem Type**: Regression (salary prediction)
- **Algorithm**: XGBoost (eXtreme Gradient Boosting)
- **Cloud Platform**: Amazon SageMaker
- **Data Source**: `person_records_merged.csv` (cloud-hosted on S3)
  - **Location**: `s3://mgta466-w25/data/person_records_merged.csv`
  - **Content**: Person records with demographic and employment features
  - **Target Variable**: WAGP (Wages or salary income)
  - **Features**: Demographic, educational, and employment characteristics
- **Points**: 15 total points

---

## Course Progression

The assignments follow a logical progression from basic concepts to advanced applications:

1. **PA1**: Foundation - Basic PySpark and HDFS operations
2. **PA2**: Text Analytics - Advanced text processing and performance analysis
3. **PA3**: Real-world EDA - Complex data analysis and visualization
4. **PA4**: Cloud Computing - Distributed processing on AWS EMR
5. **PA5**: Machine Learning - Production ML pipelines on SageMaker

## Technical Skills Developed

Throughout the course, students develop expertise in:

- **Distributed Computing**: PySpark, HDFS, and cluster management
- **Big Data Processing**: Handling datasets with millions of records
- **Cloud Computing**: AWS EMR, S3, and SageMaker
- **Data Visualization**: Matplotlib and statistical analysis
- **Machine Learning**: XGBoost, hyperparameter tuning, and model deployment
- **Performance Optimization**: Scalability analysis and resource management
- **Production Workflows**: End-to-end data processing pipelines

## Industry Relevance

These assignments prepare students for roles in:
- **Data Engineering**: Building scalable data processing systems
- **Data Science**: Advanced analytics and machine learning
- **Cloud Architecture**: Designing distributed computing solutions

---

## Data Sources Summary

This course uses a variety of real-world datasets to provide hands-on experience with different data formats and sizes:

### **Local Data Files**
- **`BookReviews_1M.txt`** (~209MB): 1 million Amazon book reviews in plain text format
- **`Airline_2016_2018.csv`** (~823MB): 6.6M+ US domestic airline flight records (2016-2018)
- **`Salary_Data.csv`** (~454B): Small salary dataset for regression examples
- **`wine_train.csv`** (~6.7KB): Wine classification dataset with 107 samples
- **`wine_val.csv`** (~2.4KB): Wine validation dataset with 38 samples
- **`wine_test.csv`** (~2.4KB): Wine test dataset with 38 samples

### **Cloud-Hosted Data (S3)**
- **`BookReviews_4M.json`**: 4 million book reviews in JSON format
  - **Location**: `s3://mgta466-w25/data/BookReviews_4M.json`
  - **Format**: Structured JSON with reviewText field
- **`person_records_merged.csv`**: Person records for salary prediction
  - **Location**: `s3://mgta466-w25/data/person_records_merged.csv`
  - **Content**: Demographic and employment features

### **Data Characteristics**
- **Text Data**: Book reviews for natural language processing
- **Structured Data**: Airline records for business analytics
- **Tabular Data**: Salary and wine datasets for machine learning
- **Big Data**: Multi-million record datasets for scalability testing
- **Real-world Data**: Actual business and consumer data for practical experience
- **ML Engineering**: Production machine learning systems
- **DevOps**: Infrastructure management and optimization

## Submission Requirements

Each assignment requires:
- **Notebook Files**: Complete Jupyter notebooks with all cells executed
- **Output Files**: CSV files with results and performance metrics
- **Screenshots**: Cloud service dashboards and cluster status
- **Documentation**: Clear explanations and analysis

## Getting Started

1. Ensure you have access to the required cloud platforms (AWS)
2. Follow the setup instructions in each assignment
3. Execute all cells in the notebooks
4. Generate the required output files
5. Submit according to the grading guidelines

---

*This course provides hands-on experience with industry-standard tools and platforms for scalable analytics and machine learning.*