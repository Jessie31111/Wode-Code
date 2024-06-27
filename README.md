# Wode-Code

import pandas as pd

# Group the data by the factor level (e.g., 'Final Adjustment')
grouped = df_t1.groupby('Final Adjustment')

# Percentage of stocks with reversion in each bucket
percentage_reversion = grouped['T1_label'].mean() * 100

# Weighted average of stocks with reversion in each bucket
weighted_avg_reversion = grouped['T1_label'].mean() * grouped['Total USD Flow'].sum()
unweighted_avg_reversion = grouped['T1_label'].mean()

# Weighted average of all stocks without reversion
non_reversion_mask = df_t1['T1_label'] == 0
weighted_avg_non_reversion = (df_t1.loc[non_reversion_mask, 'Total USD Flow'] * df_t1.loc[non_reversion_mask, 'T1_label']).sum() / df_t1.loc[non_reversion_mask, 'Total USD Flow'].sum()
unweighted_avg_non_reversion = df_t1.loc[non_reversion_mask, 'T1_label'].mean()

# Interaction between the buckets
bucket_interaction = grouped[['T1_label', 'Total USD Flow']].sum()

# Display the results
print("Percentage of stocks with reversion in each bucket:")
print(percentage_reversion)
print()

print("Weighted average of stocks with reversion in each bucket:")
print(weighted_avg_reversion)
print()

print("Unweighted average of stocks with reversion in each bucket:")
print(unweighted_avg_reversion)
print()

print("Weighted average of all stocks without reversion:")
print(weighted_avg_non_reversion)
print()

print("Unweighted average of all stocks without reversion:")
print(unweighted_avg_non_reversion)
print()

print("Interaction between the buckets:")
print(bucket_interaction)