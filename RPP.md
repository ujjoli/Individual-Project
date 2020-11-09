# Analysis of Relative Cost of Living and Expenses

As we came to know that housing and utility seem to be top priority of many residents, it is relevant to see which state in US have high cost of living and expenses.Relative Cost of living and expenses is measured on RPP which is Regional Price Parity (RPP). It is an index (ratio) that sets the national average cost of goods and services at 100, with a particular region's RPP showing how the cost of living in that region compares to that average. 

So lets move on our analysis from following plot.

Click the [link](https://github.com/ujjoli/Individual-Project/blob/gh-pages/Individual%20Project%2002.ipynb) to see the code.

![4 a](4.a..png)

This is comparison of RPP in 2018. This plot shows that the darkest color laids on Hawii, California, Massachussets, Disctrict of Colombia and New York. They have the index more than 115 where 100 is said to be the average. So the plot shows that Hawaii, California , Massachussets, DC and New York have highest RPP indicating they are the moest expensive place to live. It is interesting that California has the highest spending rate, more contributed by housing and rental utility, seems to have similar pattern with RPP. This plot is not only important to policy makers, but can also be a good indication for job seekers and people like who want to settle down. We can be convinced that, if we get job offer from California and Alaska with equal salaries and benefits (assuming all other facilites to be similar) and want cheaper place to live in, we have to go with job offer from Alaska and Alabama.

In addition, there is much disparity between the metropolitan area and non-metropolitan area. Metropolitan area are expensive than non-metropolitan area. This can also be shown from following figure.
```
#getting list of states names
state_name = list(cost_state_metro_both_state.States)
state_name

fig = go.Figure()   #using plotly graph objects
fig.add_trace(go.Scatter(       
    x=list(cost_state_metro_both_state['2018']),
    y=state_name,
    marker=dict(color="crimson", size=8),
    mode="markers",
    name="Metropolitan-area",
))

fig.add_trace(go.Scatter(
    x=list(cost_state_nonmetro_both_state['2018']),
    y=state_name,
    marker=dict(color="gold", size=8),
    mode="markers",
    name="Non-metropolitan area",
))

fig.update_layout(   #updating layout
    height = 1000,
    title="Living cost and rental cost disparity between metropolitan area and non-metropolitan area",
    xaxis_title="RPP (ratio)",
    yaxis_title="States")

fig.show()
```


![4 b](4.b..png)

With all these findings, now lets move on our [last section](comparison.md)
