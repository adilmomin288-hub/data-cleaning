import pandas as pd

# Load dataset
df = pd.read_csv("customers-100.csv")

# Show first rows
print(df.head())

# Remove duplicate rows
df = df.drop_duplicates()

# Remove unwanted columns
# Example:
# df = df.drop(columns=["notes"])

# Fill missing values
df = df.fillna("Unknown")

# Convert text to lowercase
df["First Name"] = df["First Name"].str.lower()

# Remove spaces
df["First Name"] = df["First Name"].str.strip()

# Save cleaned file
df.to_csv("cleaned_data.csv", index=False)

print("Data cleaned successfully!")
