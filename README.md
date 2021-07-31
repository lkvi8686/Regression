# Regression
****
Mulitpule Linear Regression
********
Assumptions of Linear Regression
********
**Linearity** – There should be linear relationship between dependent and independent variable. This is very logical and most essential assumption of Linear Regression. Visually it can be check by making a scatter plot between dependent and independent variable

**Homoscedasticity** – Constant Error Variance, i.e, the variance of the error term is same across all values of the independent variable. It can be easily checked by making a scatter plot between Residual and Fitted Values. If there is no trend then the variance of error term is constant.
A close observation of the above plot shows that the variance of residual term is relatively more for higher fitted values. 

****Testing for Homogeneity of Variance****
**Bartlett’s Test**
**Bartlett’s test for homogeneity of variances is used to test that variances are equal for all samples. It checks that the assumption of equal variances is true before running certain statistical tests like the One-Way ANOVA. It’s used when you’re fairly certain your data comes from a normal distribution. A similar test, called Levene’s test, is a better choice for non normal distributions.**
**The null hypothesis for the test is that the variances are equal for all samples. In statistics terms, that’s:
H0: σ12 = σ22 = … = σk2.
The alternate hypothesis (the one you’re testing), is that the variances are not equal for one pair or more:
H0: σ12 ≠ σ22 ≠… ≠ σk2.**
**Box’s M Test**
   ****Box’s M test (also called Box’s Test for Equivalence of Covariance Matrices) is a parametric test used to compare variation in multivariate samples. More specifically, it tests if two or more covariance matrices are equal (homogeneous).

**Null Hypothesis
The null hypothesis for this test is that the observed covariance matrices for the dependent variables are equal across groups. In other words, a non-significant test result (i.e. one with a large p-value) indicates that the covariance matrices are equal. The generated test statistic is called Box’s M statistic.****
****Brown-Forsythe Test******
********The Brown-Forsythe (B-F) Test is for testing the assumption of equal variances in ANOVA. It is a modification of the Levene Test.
How the Test Works
Both the Levene and B-F tests transform dependent variables for use in an ANOVA test. The only difference between the two tests is in how those transformed variables are constructed. The Levene test uses deviations from group means, which usually results in a highly-skewed set of data; This violates the assumption of normality. The Brown-Forsythe test attempts to correct for this skewness by using deviations from group medians. The result is a test that’s more robust. In other words, the B-F test is less likely than the Levene test to incorrectly declare that the assumption of equal variances has been violated.
The median is calculated for each factor level group.
The median value is subtracted from each dependent variable in the group.
An ANOVA is run with the transformed variables. If a factor’s p-value is less than the significance level (usually 5%), the population variances are not equal.
****W or F statistic?****
The test statistic used in a regular ANOVA is an F-statistic. The statistic used in an ANOVA with transformed variables is sometimes called a W-Statistic — but it’s really just an F-Statistic with a different name. It should not be confused with the coefficient of concordance W-statistic, which is used to assess agreement between raters.
********
**Hartley’s Fmax test**
  **The Fmax test (also called Hartley’s Fmax) is a test for homogeneity of variance. In other words, the spread (variance) of your data should be similar across groups or levels. Compared to Levene’s test, Hartley’s test is fairly simple to figure out by hand.

**An assumption of the Fmax test is that there are an equal number of participants in each group.

Steps
Example question: Run Hartley’s Fmax test for two conditions X and Y. Each condition (level) has 10 participants with variances of X = 12 and Y = 4.

Step 1: Find the variances for each group/level/condition. If you’re running an ANOVA test, the s2 values (i.e. the variances) will be shown in the output. Otherwise, you can calculate by hand (or use our variance and standard deviation calculator).
For this example, our variances are 12 and 4.

Step 2: Divide the larger variance by the smaller variance to find the Fmax ratio:
hartley's fmax test
Note: If the ratio is close to 1, you can stop here, as your data shows homogeneity of variance.
In this example, we have 12/4 = 3. This ratio isn’t close to 1, so go to the next step.



Step 3: Look up the number of levels and the degrees of freedom (number of items in each level minus 1) in the Fmax table.
For 9 degrees of freedom (n – 1 = 10 – 1 = 9) and a k of 2 (k is the number of levels/groups), the table shows an Fmax value of 4.04.

Step 4: Compare your calculated value from Step 2 to the table value from Step 3.

If your calculated value from Step 2 is smaller than the table value, the variance is homogeneous.
If your calculated value from Step 2 is larger than the table value, the variance is not homogeneous.
Our calculated value of 3 is smaller than the table value of 4.04, so our variance is homogeneous.

Hartley’s Fmax Table
Degrees of freedom: Subtract 1 from your sample size to find the degrees of freedom. For example, if you have 10 items in your sample, then df = 10 – 1 = 9.
k: is the number of levels/groups or conditions****
**Levene’s Test**
******Levene’s test is used to check that variances are equal for all samples when your data comes from a non normal distribution. You can use Levene’s test to check the assumption of equal variances before running a test like One-Way ANOVA.

If you’re fairly certain your data comes from a normal or nearly normal distribution, use Bartlett’s Test instead.



The null hypothesis for Levene’s is that the variances are equal across all samples. In more formal terms, that’s written as:
H0: σ12 = σ22 = … = σk2.
The alternate hypothesis (the one you’re testing), is that the variances are not equal for at least one pair:
H0: σ12 ≠ σ22 ≠… ≠ σk2.



The test statistic is a little ugly and involves a few summations:
levene test


Zi,j can take on three meanings, depending on if you use the mean, median, or trimmed mean of any subgroup. The three choices actually determine the robustness and power of the test.

Robustness, is a measure of how well the test does not falsely report unequal variances (when the variances are actually equal).
Power is a measure of how well the test correctly reports unequal variances.
According to Brown and Forsythe:

Trimmed means work best with heavy-tailed distributions like the Cauchy distribution.
For skewed distributions, or if you aren’t sure about the underlying shape of the distribution, the median may be your best choice.
For symmetric and moderately tailed distributions, use the mean.
Levene’s test is built into most statistical software. For example, the Independent Samples T Test in SPSS generates a “Levene’s Test for Equality of Variances” column as part of the output. The result from the test is reported as a p-value, which you can compare to your alpha level for the test. If the p-value is larger than the alpha level, then you can say that the null hypothesis stands — that the variances are equal; if the p-value is smaller than the alpha level, then the implication is that the variances are unequal******

**No Autocorrelation of residual** – This is typically applicable to time series data. Autocorrelation means the current value of Yt is dependent on historic value of Yt-n with n as lag period
**Durbin-Watson** test is a quick way to find if there is any autocorrelation.
The Durbin-Watson statistic will always have a value between 0 and 4. A value of 2.0 means that there is no autocorrelation detected in the sample. Values from 0 to less than 2 indicate positive autocorrelation and values from from 2 to 4 indicate negative autocorrelation

****KEY TAKEAWAYS
The Durbin Watson statistic is a test for autocorrelation in a data set.
The DW statistic always has a value between zero and 4.0.
A value of 2.0 means there is no autocorrelation detected in the sample. Values from zero to 2.0 indicate positive autocorrelation and values from 2.0 to 4.0 indicate negative autocorrelation.
Autocorrelation can be useful in technical analysis, which is most concerned with the trends of security prices using charting techniques in lieu of a company's financial health or management.********


**No Perfect Multi-Collinearity – Multi-Collinearity** is a phenomenon when two or more independent variables are highly correlated. Multi-collinearity is checked by Variance Inflation Factor (VIF). There should be no variable in the model having VIF above 2. (…for more details see our blog on Multi-Collinearity)

**Exogeneity** – Exogeneity is a standard assumption of regression and it means that each X variable does not depend on the dependent variable Y, rather Y depends on the Xs and on Error (e). In simple terms X is completely unaffected by Y.

**Sample Size – In linear regression**, it is desirable that the number of records should be at least 10 or more times the number of independent variables to avoid the curse of dimensionality
