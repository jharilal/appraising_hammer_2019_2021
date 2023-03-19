# Appraising Hammer Indicator Behavior Between 2019-2021


### About this Project

An aspect of my life I want to improve at is being able to trade effectively in the stock market, and as a result, I came up with this project to assess the capabilities of the hammer indicator. The hammer is a technical indicator that is not intended to be traded alone, but the presence of one can influence a trader to make an informed trading decision. Being that it is a technical indicator, it's expected to appear in charts without discerning the fundamentals or shape of the chart. I started with python and pandas to collect hammer data in the Nasdaq 100 between the years of 2019 to 2021, and then used Tableau to aid in visualizations. 

<img src="Pictures/covershort_AMD.png">

[Data Collection and Preparation](https://github.com/jharilal/appraising_hammer_2019_2021/blob/main/Candlestick_Analysis.ipynb)

## Analysis

### <b><p align="center">How many "true" hammers were identified?</p></b>
<img src="Pictures/true_hammers_id.png" width=200px height=auto align=left><br/>
"True" hammers are considered hammers that occur on a downtrend, since the hammer is a reversal technical indicator. Both bullish and bearish hammers are considered 'entry' signals, but bullish hammers are a stronger indicator. We were able to identify approximately 400 'true' hammers. For this analysis, we will consider all our data, but it will be important to see how these true hammers can compare to the hammer candlestick that does not appear on a downtrend.

<br clear="right"/>
<br clear="left"/>

### <b><p align="center">What effect did the pandemic have on the efficiency of the indicator?</p></b>
<img src="Pictures/avg_change_pand.png" width=200px height=auto align=right><br/>
Between the period from 2/17/2020 to 4/17/2020, the market crashed due to lockdown procedures originating from the    Covid-19 pandemic. Since this period represents a 'market crash', including this data into further analysis would not be characteristic of the hammer under normal market conditions and has potential to affect trends. 

<br clear="right"/>
<br clear="left"/>

### <b><p align="center">How does removing pandemic data affect the analysis?</p></b>
<img src="Pictures/count_before_pand.png" width=200px height=200px align=left> 
<img src="Pictures/count_after_pand.png" width=200px height=200px align=left><br/>
On the left, we can see the counts of data we have before including the pandemic data, and after excluding the data. This creates a decrease in about 50 total data points, however, this is more than plenty to gain valuable insight. 

<br clear="right"/>
<br clear="left"/>
<br/>
<br/>
<br/>

### <b><p align="center">How does the distribution of % change differ at different time periods?</p></b>

<img src="Pictures/1d_change.png" width=400px height=auto align=left padding-left=20px> 
<img src="Pictures/3d_change.png" width=400px height=auto align=right  padding-right=20px>

<br clear="left"/>
<br clear="right"/>

<img src="Pictures/5d_change.png" width=400px height=auto align=left padding-left=20px> 
<img src="Pictures/10d_change.png" width=400px height=auto align=right padding-right=20px> 

<br clear="right"/>
<br clear="left"/>

These charts display the % change over days relative to the hammer candlestick. As more time passes, we can see that the mean remains the same at a near 0 value, however variance increases relative to the initial day, which is expected since there is less certainty of behavior after more time passes. This raises the question: If a hammer is discovered, will it continue to trend as more time passes?

### <b><p align="center">Does the frequency of hammers change by GICS sector?</p></b>
<img src="Pictures/hammer_rep.png" width=480px height=auto align=left> 
<img src="Pictures/ticker_rep.png" width=480px height=auto align=right> 

<br clear="right"/>
<br clear="left"/>

The bar chart on the left shows the distribution of hammers across the GICS sectors, while the chart on the right shows the distribution of companies within the Nasdaq. At a quick glance, these distributions are approximately equal, but just to be safe, we can perform a statistical test on the largest differential in percentage.
<p align="center">
<img src="Pictures/stat_prob.png" width=300px height=auto align='center'> 
</p>
Comparing these charts, the biggest differential in representation occurs in the consumer staples sector. When statistically comparing these proportions, we arrive at a p-value of 0.6144, which means that these values are not statistically different. This supports that the hammers occur without preference of GICS sector.

<br clear="right"/>
<br clear="left"/>

### <b><p align="center">Does the hammer perform differently between GICS Sectors?</p></b>

<p align='center'> <img src="Pictures/change_by_gics.png" width=800px height=auto> </p>

In order to analyze the GICS in a way that is more resistant to outliers, we can compare the medians of each metric. Above, it is evident that the Information Technology and Consumer Discretionary sectors are overall performing better in response to a hammer, compared to the other industries. On the other hand, the Health Care industry has seems to be performing poorly after a hammer. This is not conclusive that the hammer indicator is the cause of these changes, but trading hammers will tend to have higher return on investment in Information Tech and Consumer Discrectionary.

<br clear="right"/>
<br clear="left"/>

### <b><p align="center">Is there evidence to support that hammers are generally recognized by traders?</p></b>
<img src="Pictures/vol_by_trend.png" width=200px height=auto align=right> 
On this chart, we can see that on days of the hammer, there tends to be a greater volume of trading present. This means that there are a significant amount of people recognizing the pattern and believe it is a good opportunity to invest.  Especially with new traders in technical analysis,  the hammer is one of the earliest indicators taught. There's approximately 25% greater volume in the presence of a true hammer

<br clear="right"/>
<br clear="left"/>

### <b><p align="center">What is the average gain or loss of the hammer?</p></b>
<p align='center'>
<img src="Pictures/avg_change_by_day.png" width=800px height=auto> 
</p>
The average gain whenever the hammer candlestick appears is positive. A interesting aspect to note about the chart below is that the 'true' hammer and the other hammers all display some amount of gain. Expectations would say that the 'other' hammer would not display a significantly positive change. Another important aspect to note is that even though the bearish hammer is not supposed to be as strong as the bullish hammer, at 3 days and 5 days, the average percent change reaches above 1%, while the bullish hammer reaches 0.5% after 5 days. The change between 5 days and 10 days for the bullish hammer is significant and reaches almost 2% return. A key point to note is that this does not mean a hammer indicator is a 100% guarantee for profit.  

<br clear="right"/>
<br clear="left"/>


### <b><p align="center">Taking a closer look at sub-industries</p></b>

<p align='center'><img src="Pictures/sub_ind0.png" width=400px height=auto>
<img src="Pictures/sub_ind3.png" width=400px height=auto></p>
<p align='center'><img src="Pictures/sub_ind1.png" width=600px height=auto></p>


Above, we can see the sub-industries for the highlighted GICS Sectors above. Major contributors to the average % change are compared against the rest of the industries.

For IT, it is clear that Semiconductors and Application Software demonstrate a  very strong positive response to the hammer, and demonstrate an average increase of nearly 2% for Application software, and 3% for the Semiconductors + Equipments at 10 days.

The Healthcare industry seems to perform relatively flat, or experiences minor gains from the hammer, however, the presence of the Biotech sub-industry causes the entire sector to demonstrate poor performance.

In  the Consumer Discretionary sector, Internet and Direct Marketing Retail is mainly responsible for the positive performance of the sector, since 40% of the hammers present for this sector occur in this sub-industry. At the 10 day mark, we can see an average gain of approximately 4.5% across 20 true hammer instances.

<br clear="right"/>
<br clear="left"/>

### <b><p align="center">What is the relationship between each time period?</p></b>

<p align='center'><img src="Pictures/corr_plot.png" width=800px height=auto></p>

Above we can visualize the correlation between each of the time periods with each other. This would essentially tell us the strength of the indicator days ahead, and give an indication of how well the hammer will perform, based on the previous time points. As expected, as time moves forward, the correlation begins to decline, however, an important plot to notice is the 3d% / 5d% plot, and the 5d% /10d% plot. These plots demonstrate the strength of the hammer many days after its appearance, and demonstrate that after the 3d% point, the change will tend to trend either positively or negatively based on how it already has performed. This may mean that 3 days after a hammer can be a good indication of whether the indicator will continue to increase / decrease.
