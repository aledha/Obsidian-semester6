>The t-tests in the model summary provide information about the statistical significance of each independent variable in the regression model. The t-test assesses whether the estimated coefficient for each independent variable is significantly different from zero.

The t-value represents the estimated coefficient divided by its standard error. A higher absolute t value indicates a larger magnitude of the estimated coefficient relative to its variability.

The p-value represents the probability of observing the estimated coefficient, assuming the null hypothesis that the true coefficient is zero. A small p-value (typically less than 0.05) suggests that the independent variable has a statistically significant effect on the dependent variable.

### Example
In the model summary below, the t-tests are reported under the "t value" column, along with the corresponding p-values under the "Pr(>|t|)" column.
![[Pasted image 20230521151516.png|400]]
Interpreting the t-tests for each independent variable in the model:
1. <u>Area</u>: The t value is $-1.068$, and the p-value is $0.296318$. Since the p-value is greater than $0.05$, we do not have enough evidence to reject the null hypothesis that the true coefficient for Area is zero. Therefore, Area does not appear to have a significant effect on the number of species.
2. <u>Elevation</u>: The t value is $5.953$, and the p-value is $3.82 \times 10^{-6}$. The small p-value indicates that Elevation has a statistically significant effect on the number of species. The positive coefficient suggests that an increase in Elevation is associated with an increase in the number of species.
3. <u>Nearest</u>: The t value is $0.009$, and the p-value is $0.993151$. The large p-value suggests that Nearest does not have a significant effect on the number of species. We do not have enough evidence to reject the null hypothesis that the true coefficient for Nearest is zero.
4. <u>Scruz</u>: The t value is $-1.117$, and the p-value is $0.275208$. Similar to Nearest, the p-value for Scruz is greater than $0.05$, indicating that Scruz does not have a significant effect on the number of species.
5. <u>Adjacent</u>: The t value is $-4.226$, and the p-value is $0.000297$. The small p-value suggests that Adjacent has a statistically significant effect on the number of species. The negative coefficient implies that an increase in Adjacent is associated with a decrease in the number of species.

In summary, based on the t-tests, Elevation and Adjacent are found to be statistically significant predictors of the number of species in the Galapagos islands. Area, Nearest, and Scruz, on the other hand, do not appear to have a significant effect on the number of species.

