### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
# Visitor segmentation based on characteristics
# read the data

import pandas as pd
df = pd.read_csv('/content/clustervisitor.csv')
df
<img width="476" height="888" alt="image" src="https://github.com/user-attachments/assets/e94a370c-b6d9-4ab8-8184-8d0eb590cc72" />
<img width="438" height="207" alt="image" src="https://github.com/user-attachments/assets/62b4436c-cc66-4fcd-8589-3f89dd8401ec" />


# Perform segmentation based on characteristics (e.g., age groups)
age_groups = {
    'Young': visitor_df['Age'] <= 30,
    'Middle-aged': (visitor_df['Age'] > 30) & (visitor_df['Age'] <= 50),
    'Elderly': visitor_df['Age'] > 50
}

for group, condition in age_groups.items():
    visitors_in_group = visitor_df[condition]
    print(f"count : {len(visitors_in_group)}")
    print(f"Visitors in {group} age group:")
    print(visitors_in_group)
```
### Output:
<img width="531" height="781" alt="image" src="https://github.com/user-attachments/assets/26d800b2-fcb6-48cc-86a2-19469831deb7" />


### Visualization:
```python

import matplotlib.pyplot as plt
# Create a list to store counts of visitors in each age group
visitor_counts=[]

# Count visitors in each age group
for group,condition in age_groups.items():
  visitors_in_group=visitor_df[condition]
  visitor_counts.append(len(visitors_in_group))

# Define age group labels and plot a bar chart

age_group_labels=list(age_groups.keys())
plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()

```
### Output:
<img width="856" height="637" alt="image" src="https://github.com/user-attachments/assets/7896effd-0551-49a8-b129-2cba085a6eb1" />


### Result:
The implement Cluster and Visitor Segmentation for Navigation patterns in Python is execute successfully.
