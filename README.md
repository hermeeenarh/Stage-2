Task Code 2.7:
Public Health

import pandas as pd
import matplotlib.pyplot as plt

# Define the data source URL
data_source = "https://github.com/HackBio-Internship/public_datasets/raw/main/R/nhanes_dd.csv"

# Load the dataset into a pandas DataFrame
df = pd.read_csv(data_source)

# Remove rows with missing values (NaN)
df_filled = df.fillna(0)
print(df_filled.head())
import pandas as pd

# Define the data source URL
data_source = "https://raw.githubusercontent.com/HackBio-Internship/public_datasets/main/R/nhanes.csv"

# Load the dataset into a pandas DataFrame
df = pd.read_csv(data_source,sep = ',') #imports data from the web and assigns it to df

# Print the columns of the DataFrame to see the available columns
#print(df.columns)

# Assuming the actual column name is "Pulse", adjust the code accordingly
print(df["Pulse"].mean()) # Access using the actual column name "
import pandas as pd

# Define the data source URL
data_source = "https://raw.githubusercontent.com/HackBio-Internship/public_datasets/main/R/nhanes.csv"

# Load the dataset into a pandas DataFrame
df = pd.read_csv(data_source, sep=',')

# Print the columns of the DataFrame to see the available columns
#print(df.columns)

# * Replace 'dbp' with the actual column name for diastolic blood pressure *
# For example, if the column is named 'DiastolicBP', use:
min_dbp = df['BPDia'].min()
max_dbp = df['BPDia'].max()
# If the column name is "BPXDIAS" as it appears in the dataset columns, use that.

print(f"Diastolic blood pressure range:")
print(f"Minimum: {min_dbp}")
print(f"Maximum: {max_dbp}")
import pandas as pd

# Define the data source URL
data_source = "https://raw.githubusercontent.com/HackBio-Internship/public_datasets/main/R/nhanes.csv"

# Load the dataset into a pandas DataFrame
df = pd.read_csv(data_source, sep=',')
#print the columns of the dataset
print(df.columns)

# Calculate variance and standard deviation for income
income_variance = df['Income'].var()
income_std = df['Income'].std()

print(f"Income statistics:")
print(f"Variance: {income_variance:.2f}")
print(f"Standard Deviation: {income_std:.2f}")
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# Read the data
df = pd.read_csv("https://raw.githubusercontent.com/HackBio-Internship/public_datasets/main/R/nhanes.csv")

# Create a figure with 2x2 subplots
fig, axes = plt.subplots(2, 2, figsize=(15, 12))
fig.suptitle('Distribution of Health Metrics in NHANES Dataset', fontsize=16, y=1.02)

# Flatten the axes array to access individual subplots easily
axes = axes.flatten()  # <-- Add this line

# Create histograms with KDE
# BMI Distribution
sns.histplot(data=df, x='BMI', kde=True, ax=axes[0])  # <-- Now use axes[0]
axes[0].set_title('BMI Distribution')
axes[0].set_xlabel('BMI')
axes[0].set_ylabel('Count')
# Weight Distribution (kg)
sns.histplot(data=df, x='Weight', kde=True, ax=axes[1]) # <-- Now use axes[1]
axes[1].set_title('Weight Distribution (kg)')
axes[1].set_xlabel('Weight (kg)')
axes[1].set_ylabel('Count')

# Weight Distribution (lbs)
weight_lbs = df['Weight'] * 2.2
sns.histplot(x=weight_lbs, kde=True, ax=axes[2]) # <-- Now use axes[2]
axes[2].set_title('Weight Distribution (lbs)')
axes[2].set_xlabel('Weight (lbs)')
axes[2].set_ylabel('Count')

# Age Distribution
sns.histplot(data=df, x='Age', kde=True, ax=axes[3]) # <-- Now use axes[3]
axes[3].set_title('Age Distribution')
axes[3].set_xlabel('Age')
axes[3].set_ylabel('Count')

# Adjust layout to prevent overlap
plt.tight_layout()

# Show the plot
plt.show()
