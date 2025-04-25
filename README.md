# Analyze Students Engagement on an Online Learning Platform

## Project Overview

This project is focused on analyzing user engagement data from an online learning platform. The dataset includes detailed information about students, their course activities, and feedback provided on the courses. The objective is to clean and merge these datasets to generate valuable insights on user engagement, course completion rates, and feedback ratings, providing a deeper understanding of how students interact with the platform.

### Key Objectives:
- **Data Cleaning**: The raw data is cleaned to ensure it's consistent, accurate, and ready for analysis. This includes handling missing values, removing duplicates, and standardizing column names.
- **Data Merging**: Multiple datasets containing student information, course activity, and feedback are merged to create a unified dataset.
- **Feature Engineering**: New features, such as categorizing students by age group, are created to improve analysis.
- **Data Visualization**: Various visualizations are generated to uncover trends and insights, including engagement patterns by age group and location.
- **Saving Cleaned Data**: The final cleaned and merged dataset is saved for further use.

### Datasets Used:
- **students.csv**: Contains student information such as ID, name, age, gender, and location.
- **course_activity.csv**: Contains data about student engagement in various courses, including time spent and completion percentages.
- **feedback.csv**: Contains students' feedback and ratings for each course they attended.

### Technologies Used:
- **Python**: Programming language used for data manipulation and analysis.
- **Pandas**: Used for data cleaning, merging, and manipulation.
- **NumPy**: Used for numerical operations.
- **Seaborn/Matplotlib**: Used for creating visualizations.
  
---

## Usage

### Steps to Use the Project:

1. Install Required Libraries**:
Ensure that all required libraries are installed by running the following command:

   ```bash
   pip install pandas numpy seaborn matplotlib
   
2. Load the Data: Load the datasets into Python using Pandas for data analysis.
import pandas as pd

students = pd.read_csv('students.csv')
course_activity = pd.read_csv('course_activity.csv')
feedback = pd.read_csv('feedback.csv')

3. Data Cleaning and Merging: Clean and merge the datasets into a single DataFrame, handling missing values, removing duplicates, and standardizing column names.

 Clean and merge data
merged_data = pd.merge(course_activity, students, on='Student_ID', how='inner')
merged_data = pd.merge(merged_data, feedback, on=['Student_ID', 'Course_ID'], how='inner')

4. Generate Insights and Visualizations: Perform data analysis and generate visualizations to identify trends and patterns in user engagement.
import seaborn as sns
import matplotlib.pyplot as plt

Example: Engagement by Age Group
engagement_by_age_group = merged_data.groupby('Age_Group')['Time_Spent_Minutes'].mean()
sns.barplot(x=engagement_by_age_group.index, y=engagement_by_age_group.values)
plt.title('Average Engagement Time by Age Group')
plt.show()


5. Save Cleaned Data: Once the data has been cleaned and analyzed, save the final cleaned dataset.

merged_data.to_csv('cleaned_students_data.csv', index=False)


## Conclusion 
This project provides insights into user engagement on an online learning platform. By cleaning and merging data from different sources, 
we are able to analyze key engagement metrics, such as course completion rates and feedback patterns. The visualizations offer a clearer 
understanding of how students interact with the platform based on age, location, and other factors.



