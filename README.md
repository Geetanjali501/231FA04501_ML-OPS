# MLOps – Feast Feature Store for Employability Skill Gap Prediction
## Student Details
* **Student Name:** Geetanjali
* **Project:** MLOps – Feast Feature Store
* **Dataset:** Balanced Employability Dataset
* **Feast Version:** 0.64.0
## 1. Problem Statement
The objective of this project is to use Feast, a feature store framework, to manage machine learning features for predicting student employability.
The project uses an employability skill-gap dataset containing academic performance, technical skills, soft skills, internship experience, projects, certifications, aptitude, industry requirements, and skill-gap information.
Feast is used to:
* Define and manage features.
* Retrieve historical features for model training.
* Materialize features into the online store.
* Retrieve online features for prediction.
  
## 2. Objectives
The main objectives of this project are:
* To understand the concept of a feature store.
* To install and configure Feast.
* To define entities and features using Feast.
* To create a feature view for the employability dataset.
* To retrieve historical features for machine learning.
* To materialize features into the online store.
* To retrieve online features for prediction.

## 3. Dataset

The project uses a balanced employability dataset related to student skills and employability.

The dataset contains information related to:

* Academic performance
* Technical skills
* Soft skills
* Internship experience
* Project experience
* Certifications
* Aptitude skills
* Industry requirements
* Skill gaps
* Employability outcome

The dataset is used as the source for creating and managing features using Feast.

## 4. Technologies Used

* Python
* Google Colab
* Feast 0.64.0
* Pandas
* PyArrow
* Parquet
* SQLite

## 5. Installation
Feast and PyArrow were installed in Google Colab using the following command:

```python
!pip install feast==0.64.0 pyarrow
```
The installed Feast version was then verified.

## 6. Feature Store

Feast is used as the feature store for the project.
The feature store manages the features required for the employability prediction task.
The main steps performed are:
1. Create the Feast feature repository.
2. Define the data source.
3. Define the entity.
4. Define the features.
5. Create the feature view.
6. Apply the Feast configuration.
7. Retrieve historical features.
8. Materialize features.
9. Retrieve online features.

## 7. Entity

An entity represents the object for which features are stored and retrieved.
In this project, the student identifier is used as the entity.

Example:

```python
student_id = Entity(
    name="student_id",
    join_keys=["student_id"]
)
```

The `student_id` is used to identify individual students when retrieving their features.

## 8. Features

The employability dataset contains different attributes that are used as machine learning features.

Examples include:

* Academic scores
* Technical skills
* Soft skills
* Internship experience
* Project experience
* Certifications
* Aptitude scores
* Industry requirements
* Skill-gap information

These features are managed by Feast and can be retrieved for machine learning purposes.

## 9. Feature View

A Feature View is used to group related features together.

The Feature View connects the features with the entity and the underlying data source.

It allows Feast to manage and retrieve the required features for model training and prediction.

## 10. Historical Feature Retrieval

Historical feature retrieval is used to obtain feature values for model training.

Feast retrieves the required features from the offline data source based on the entity and timestamp information.

The resulting historical feature data can be used as input for training a machine learning model.

## 11. Materialization

Materialization loads feature values from the offline store into the online store.

This makes the latest feature values available for online feature retrieval.

The materialization step is useful when features are required for real-time machine learning predictions.

## 12. Online Feature Retrieval

After materialization, features can be retrieved from the online store using the entity key.

For a given `student_id`, Feast can retrieve the corresponding feature values.

This demonstrates the use of Feast for serving features during prediction.

## 13. Workflow

The overall workflow of the project is:

**Dataset → Data Source → Entity → Features → Feature View → Feast Apply → Historical Retrieval → Materialization → Online Retrieval**

## 14. Conclusion

This project demonstrates the use of Feast as a feature store for an employability skill-gap prediction problem.

Feast provides a systematic way to define, manage, retrieve, and serve machine learning features.

The project demonstrates both historical feature retrieval for model training and online feature retrieval for prediction.
## 15. CLA-1 Implementation

The CLA-1 implementation was carried out using Google Colab and Feast 0.64.0.

### Step 1: Dataset Loading

The balanced employability dataset was loaded using Pandas.

The dataset contains student-related academic, technical, and employability information.

### Step 2: Data Preprocessing

The dataset was converted into Feast-compatible feature columns.

The following types of features were prepared:

- Student ID
- CGPA
- Attendance
- Programming
- Data Structures
- Algorithms
- DBMS
- Operating Systems
- Computer Networks
- OOP
- Python
- Java
- SQL
- Web Development
- Git/GitHub
- Cloud Computing
- AI/ML
- Communication
- Problem Solving
- Teamwork
- Internship
- Projects
- Certifications
- Aptitude
- Average Skill
- Industry Requirement
- Skill Gap
- Gender

Gender was encoded numerically and the employability value was stored as the target label.

### Step 3: Timestamp Creation

Event timestamps and created timestamps were generated for the feature records.

These timestamps allow Feast to manage feature values based on time.

### Step 4: Feature Data Creation

The required feature columns were selected and stored as a separate feature dataset.

The feature data was saved in Parquet format.

### Step 5: Feast Repository Creation

A Feast repository was created at:

`/content/employability_feast`

The repository contains the configuration and data required for the Feast feature store.

### Step 6: Feature Store Configuration

The Feast configuration defines:

- Project name: `employability_project`
- Registry: `data/registry.db`
- Provider: Local
- Offline store: File
- Online store: SQLite

### Step 7: Entity and Feature Management

`student_id` was used as the entity key.

The student-related attributes were defined as features that can be retrieved through Feast.

### Step 8: Historical Feature Retrieval

Historical feature retrieval was performed to obtain feature values associated with the required entities and timestamps.

These features can be used for machine learning model training.

### Step 9: Materialization

The feature values were materialized into the online store.

This makes the latest feature values available for online retrieval.

### Step 10: Online Feature Retrieval

Online features were successfully retrieved for:

`student_id = 1001`

The retrieved feature values included:

- **CGPA:** 8.14
- **Industry Requirement:** 89.0
- **Skill Gap:** 19.47
- **Average Skill:** 69.53

This confirms that the Feast online feature retrieval process was successfully completed.

## 16. Final Result

The CLA-1 implementation successfully demonstrated the use of Feast as a feature store.

The project successfully performed:

**Dataset → Preprocessing → Feature Creation → Feast Repository → Historical Retrieval → Materialization → Online Feature Retrieval**

The final online retrieval successfully returned feature values for student `1001`.

## 17. Google Colab

The complete implementation, source code, and execution outputs are available in the `MLops_Feast.ipynb` notebook included in this repository.
