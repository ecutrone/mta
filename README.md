Evaluating MTA Performance: Mean distance between failures

Mean distance between failures is one metric of NYC Subway performance--the average distance trains travel before failing 
(so higher numbers indicate better performance). 

This dataset (from Enigma: https://www.enigma.com/public-data) includes the monthly report of mean distance between failures from 2008-2011, 
to which I fit a linear regression model, to see if this metric changed over time. 

In the simplest version of the model I fit a straight line to the data--slight positive slope, not a great fit.

It looks like there's some kind of regular pattern over the months of the year (and that makes sense--winter weather + above-ground tracks, for example).
So I took the mean value for each month to get a rough approximation of the normaly yearly cycle of the mean distance between failures.
(Some other analysis might take into account the cyclical aspect of the time dimension here. Maybe doing a fourrier transform and pulling out the
 biggest components?)

Then I added this pattern as a factor in the regression analysis. The resulting predictions do explain more of the variance than the straight line, 
and they suggest that performance actually is getting worse over time. But there are still definitely systematic errors in the model's predictions.

There are more rigorous ways to regularize this model and probably better ways to accout for seasonal effects, so I will explore in future updates.