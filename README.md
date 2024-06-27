# Wode-Code

import pandas as pd

# Group the data by the factor level (e.g., 'Final Adjustment')
grouped = df_t1.groupby('Final Adjustment')

# Percentage of stocks with reversion in each bucket
percentage_reversion = grouped['T1_label'].mean() * 100

# Weighted average level of stocks with reversion in each bucket
weighted_avg_level_reversion = grouped.apply(lambda x: (x['Level'] * x['Total USD Flow']).sum() / x['Total USD Flow'].sum())

# Unweighted average level of stocks with reversion in each bucket
unweighted_avg_level_reversion = grouped['Level'].mean()

# Display the results
print("Percentage of stocks with reversion in each bucket:")
print(percentage_reversion)
print()

print("Weighted average level of stocks with reversion in each bucket:")
print(weighted_avg_level_reversion)
print()

print("Unweighted average level of stocks with reversion in each bucket:")
print(unweighted_avg_level_reversion)
print()