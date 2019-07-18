In this project, we will do data analysis on a/b test result to help our client decide whether to launch two new features on their website.

Here's the customer funnel for typical new users on their site:

View home page > Explore courses > View course overview page > Enroll in course > Complete course

Our client loses users as they go down the stages of this funnel, with only a few making it to the end. To increase student engagement, Our client is performing A/B tests to try out changes that will hopefully increase conversion rates from one stage to the next.

A/B tests are used to test changes on a web page by running an experiment where a control group sees the old version, while the experiment group sees the new version. A metric is then chosen to measure the level of engagement from users in each group. These results are then used to judge whether one version is more effective than the other. A/B testing is very much like hypothesis testing with the following hypotheses:

Null Hypothesis: The new version is no better, or even worse, than the old version
Alternative Hypothesis: The new version is better than the old version
If we fail to reject the null hypothesis, the results would suggest keeping the old version. If we reject the null hypothesis, the results would suggest launching the change. These tests can be used for a wide variety of changes, from large feature additions to small adjustments in color, to see what change maximizes your metric the most.

Summary of our steps:

First we set hypothesis:

null hypothesis is H0: CTR_{experiment} - CTR_{control} <= 0

alternative hypothesis is H1: CTR_{experiment} - CTR_{control} > 0.

In Step_1, we have calculated the observed difference in CTR between experiment and control group as obs_diff, i.e. CTR_{experiment} - CTR_{control} = 0.030034443684015644.

We can not make conclusion to say the click through rate in experiment group is higher than the click through rate in control group by this one number (the observed difference) calculated by our collected data, because only judging from one sample, the result might be by random chance. We need to run statistical test to see if this number is statistically significant in order to reject our null hypothesis.

With limited time and resources, we can not collect the same size of data 10000 times, thus We use bootstrapping technique to take sample from the a group (our sample data) with replacement 10000 times; this is to simulate the creation of sampling distribution for our statistics.

From the histogram of the sample distribution, we can see the majority of the number is centered around 0.03. Since our null hypothesis is CTR_{experiment} - CTR_{control} <= 0, we need to create a normal distribution centered at 0, with the same standard deviation as our sampling distribution we simulated here; this is to simulate the null.

We then calculate the p-value for our statistics, which is the observed difference in proportion by simulating the distribution under null hypothesis and then finding the probability that our statistic came from this distribution.

With p-value under 0.05, the difference in click through rates for the control and expriment group does appear to be significant, i.e. it seems unlikely that our statistic is from this null. Thus we can reject null hypothesis, and based on these results, we can give recommendation that our company should launch the new homepage design
