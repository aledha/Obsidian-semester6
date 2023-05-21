>The Anderson-Darling test is a statistical test used to determine if a given sample of data follows a particular distribution (usually normal distr.) . The test is an extension of the Kolmogorov-Smirnov test and provides a more <u>accurate assessment of normality</u>, particularly for smaller sample sizes.

The Anderson-Darling test evaluates the null hypothesis that a sample comes from a specific distribution, such as the normal distribution. The test calculates a test statistic, denoted as A^2, which is based on the discrepancies between the observed data and the expected values under the assumed distribution.

The Anderson-Darling test can be used to test for normality as well as other distributions, such as exponential, log-normal, and Weibull. However, <u>when applied to test for normality, it is specifically referred to as the Anderson-Darling normality test.</u>

### Example
---
	>ad.test(rstudent(fit1))
		 Anderson-Darling normality test 
	data: rstudent(fit1) 
	A = 1.7071, p-value = 0.0001729

The AndersonDarling normality test gives a p-value of 0.0002. This means that we reject the null hypothesis that the errors are normal. We can also see this in the example in [[Q-Q Plot]]