Subject: Proposed Strategies and Challenges in Data Collection for Trading Analysis

Dear [Recipient's Name],

I hope this email finds you well. I wanted to follow up on our previous discussion regarding enhancing our trading strategies. I have made significant efforts to gather comprehensive data for the three examples we discussed, and I would like to share my findings and challenges with you.

Despite my best efforts, obtaining data on a large scale through web scraping proved to be infeasible. The attached file represents the most well-rounded data I could obtain for the three examples. I reached out to multiple sources, but unfortunately, in Australia, there is no data disclosure system similar to CCASS. This presents a significant challenge in scaling up the data collection process. 

For instance, when more clients are added, manually downloading data by clicking links becomes an arduous and time-consuming task, similar to manually pasting the data. It is only possible to obtain the quarterly reports of a fund through manual downloads. Moreover, without the ability to web scrape, we are unable to automate the process unless the data is available in a downloadable file format from an online source.

One potential solution for scaling up the data collection process is to leverage Bloomberg. By setting the date range, we can guarantee access to data from the latest quarter. However, the availability of data on Bloomberg depends on the level of disclosure by the companies. For example, Paradice has 60+ available data points, L1 Capital has 30+, but Wavestone has no available data due to certain constraints. I have reached out to the Bloomberg engineering team to address this issue, but unfortunately, I do not have a specific timeline for when this feature will be available (attached is the conversation log for reference). Until then, copying and pasting data or manual input remains the most efficient method.

In general, data disclosure can occur through various channels, such as exchange filings (e.g., ASX for voting power exceeding 5%), 13F filings with the SEC (for institutions controlling over $100 million in assets), or aggregated market information from Bloomberg. To access filing information, we need to visit the respective exchange or SEC website, trace the relevant dates, and manually download the corresponding files. This process is similar to downloading and scraping data from monthly reports and presents challenges when attempting to do it on a large scale.

Considering the potential addition of more clients and assuming their nature is similar to the three trial examples (private-held funds), I propose the following directions:

1. Continue discussing the function update with the Bloomberg team, seeking a resolution to the limitations we have encountered.

2. Gather the calendar for each client's report date to ensure timely data download and updates, both from Bloomberg and the respective company websites. In this scenario, the information extracted from the PDFs will likely be limited to a few key details that need updating.

However, I must emphasize that these proposals are somewhat hypothetical and based on the trials conducted with the three examples. They assume that all clients have similar disclosure practices as private-held funds.

I appreciate your understanding of the challenges we face in data collection and analysis. I remain committed to finding the most efficient and effective ways to enhance our trading strategies. If you have any further suggestions or insights, please do not hesitate to share them.

Thank you for your attention, and I look forward to discussing these challenges and potential solutions in more detail.

Best regards,
[Your Name]