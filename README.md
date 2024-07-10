for region in df['REGION OF LISTING'].unique():
    plt.figure(figsize=(20, 10))
    plt.suptitle(region)
    df_region = df[df['REGION OF LISTING'] == region]
    for i, col in enumerate(['T1_level', 'T2_level', 'T5_level', 'T10_level', 'T30_level']):
        plt.subplot(2, 3, i + 1)
        plt.boxplot(df_region[col])
        plt.title(col)
    plt.show()

for region in df['REGION OF LISTING'].unique():
    df_region = df[df['REGION OF LISTING'] == region]
    for col in ['T1_level', 'T2_level', 'T5_level', 'T10_level', 'T30_level']:
        max_ticker = df_region.loc[df_region[col].idxmax(), 'Ticker']
        min_ticker = df_region.loc[df_region[col].idxmin(), 'Ticker']
        print(f'{region} - {col} - max: {max_ticker}, min: {min_ticker}')
        
