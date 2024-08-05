import pandas as pd
import matplotlib.pyplot as plt

# 假设df是你的DataFrame，包含所需的数据

# 1. 计算从列名'-4'开始的所有列的平均值
start_column = df.columns.get_loc('-4')
average_values = df.iloc[:, start_column:].mean(axis=1)

# 添加平均值列到DataFrame
df['Average'] = average_values

# 2. 绘制图表
plt.figure(figsize=(12, 6))
plt.plot(df.index, df['Average'], marker='o', color='b', label='Average')
plt.xlabel('Index')
plt.ylabel('Average Value')
plt.title('Average Values from Column -4 Onward')
plt.legend()
plt.grid(True)
plt.show()