# Filter rows where 'Mkt Cap' is less than 500
filtered_df = df_reversion[df_reversion['Mkt Cap'] < 500]

# Group by 'COUNTRY OF LISTING' and 'Final Adjustment' columns
grouped_country = filtered_df.groupby('COUNTRY OF LISTING')
grouped_final_adjustment = filtered_df.groupby('Final Adjustment')



# Calculate and print the ratio for each group
for country, country_group in grouped_country:
    sum_T1_weighted = country_group['T1_weighted'].sum()
    sum_Total_Absolute_USD_Flow = country_group['Total Absolute USD Flow'].sum()
    ratio = sum_T1_weighted / sum_Total_Absolute_USD_Flow
    print(f"For {country}:")
    print("Sum of T1_weighted:", sum_T1_weighted)
    print("Sum of Total Absolute USD Flow:", sum_Total_Absolute_USD_Flow)
    print("Ratio of Sum of T1_weighted to Sum of Total Absolute USD Flow:", ratio)
    print()

for adj, adj_group in grouped_final_adjustment:
    sum_T1_weighted = adj_group['T1_weighted'].sum()
    sum_Total_Absolute_USD_Flow = adj_group['Total Absolute USD Flow'].sum()
    ratio = sum_T1_weighted / sum_Total_Absolute_USD_Flow
    print(f"For Final Adjustment {adj}:")
    print("Sum of T1_weighted:", sum_T1_weighted)
    print("Sum of Total Absolute USD Flow:", sum_Total_Absolute_USD_Flow)
    print("Ratio of Sum of T1_weighted to Sum of Total Absolute USD Flow:", ratio)
    print()
