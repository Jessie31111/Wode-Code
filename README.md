# Wode-Code

import pandas as pd
import matplotlib.pyplot as plt

# Create a copy of the original DataFrame
df_analysis = df.copy()

# Group by 'Final Adjustment' and calculate the average return for each group
final_adjustment_group = df_analysis.groupby('Final Adjustment')['return_t1'].mean()

# Plot the average returns for each 'Final Adjustment' group
final_adjustment_group.plot(kind='bar', figsize=(8, 6))
plt.xlabel('Final Adjustment')
plt.ylabel('Average Return')
plt.title('Average Return by Final Adjustment')
plt.show()

# Group by 'Sector' and calculate the average return for each group
sector_group = df_analysis.groupby('Sector')['return_t1'].mean()

# Plot the average returns for each 'Sector' group
sector_group.plot(kind='bar', figsize=(8, 6))
plt.xlabel('Sector')
plt.ylabel('Average Return')
plt.title('Average Return by Sector')
plt.show()
