# Project Title: Survey Data Analysis

## Overview
This project analyzes survey data collected from respondents regarding their satisfaction with various platforms. The analysis includes visualizations such as bar charts, pie charts, and heatmaps to provide insights into the data.

## Data Description
The dataset `survey_data.csv` contains the following columns:

- **RespondentID**: Unique identifier for each respondent.
- **PreferredPlatform**: The platform preferred by the respondent (e.g., YouTube, Instagram, Facebook).
- **Satisfaction**: Indicates whether the respondent is satisfied (Yes/No).
- **Rating**: A numerical rating given by the respondent (on a scale of 1 to 5).

### Sample Data
| RespondentID | PreferredPlatform | Satisfaction | Rating |
|--------------|-------------------|--------------|--------|
| 1            | YouTube           | Yes          | 5      |
| 2            | Instagram         | Yes          | 4      |
| 3            | Facebook          | No           | 2      |
| 4            | YouTube           | Yes          | 5      |
| 5            | Instagram         | No           | 3      |
| 6            | Facebook          | No           | 1      |
| 7            | YouTube           | Yes          | 4      |
| 8            | Instagram         | Yes          | 4      |
| 9            | YouTube           | No           | 2      |
| 10           | Facebook          | Yes          | 3      |

## Analysis and Visualizations

### 1. Bar Chart: Satisfaction Count
A bar chart is created to visualize the count of responses for each satisfaction level (Yes/No). This helps in understanding the overall satisfaction of respondents.

```python
satisfaction_counts = df['Satisfaction'].value_counts()
satisfaction_counts.plot(kind='bar', color='green')
plt.title('Satisfaction Count')
plt.xlabel('Satisfaction')
plt.ylabel('Number of Responses')
plt.tight_layout()
plt.savefig('bar_satisfaction.png')
plt.show()
```

### 2. Pie Chart: Platform Preference
A pie chart is generated to show the distribution of preferred platforms among respondents. This visualization provides a clear view of which platforms are favored.

```python
platform_counts = df['PreferredPlatform'].value_counts()
platform_counts.plot(kind='pie', autopct='%1.1f%%', startangle=140)
plt.title('Preferred Platforms')
plt.ylabel('')
plt.tight_layout()
plt.savefig('pie_platform.png')
plt.show()
```

### 3. Heatmap: Ratings by Platform
A heatmap is created to display the average ratings given by respondents for each platform, segmented by their satisfaction level. This visualization helps in identifying trends and patterns in ratings across different platforms.

```python
pivot = df.pivot_table(values='Rating', index='PreferredPlatform', columns='Satisfaction')
sns.heatmap(pivot, annot=True, cmap='coolwarm')
plt.title('Ratings Heatmap: Platform vs Satisfaction')
plt.tight_layout()
plt.savefig('heatmap_rating.png')
plt.show()
```

## Requirements
To run this project, ensure you have the following Python libraries installed:

- pandas
- matplotlib
- seaborn

You can install these libraries using pip:

```bash
pip install pandas matplotlib seaborn
```

## Conclusion
This project provides a comprehensive analysis of survey data regarding platform preferences and satisfaction levels. The visualizations created help in understanding the data better and can be used for further decision-making processes.

## License
This project is licensed under the MIT License. See the LICENSE file for more details.
