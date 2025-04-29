---
Title: "Probability And Statistics 11"
Status: 
marker: 
tags: 
Date: "2025.04.17"
Time: "22:46"
---
# Probability And Statistics 11

# One-Way and Two-Way ANOVA Analysis in R

This document provides comprehensive analysis of several ANOVA problems, examining differences between group means in various experimental settings. Each exercise includes detailed R code implementation and statistical interpretation.

## Exercise 1: One-Way ANOVA Problems

### Problem 1: Comparing Five Samples

```R
# Problem 1: One-way ANOVA with 5 samples of unequal sizes

# Input the data
sample1 &lt;- c(14, 13, 10, 9, 10)
sample2 &lt;- c(10, 9, 12, 12)
sample3 &lt;- c(11, 12, 13, 16, 17)
sample4 &lt;- c(16, 17, 14, 13, 12, 14)
sample5 &lt;- c(14, 12, 13)

# Combine data into a data frame
data &lt;- data.frame(
  values = c(sample1, sample2, sample3, sample4, sample5),
  group = factor(c(rep("Sample1", length(sample1)),
                  rep("Sample2", length(sample2)),
                  rep("Sample3", length(sample3)),
                  rep("Sample4", length(sample4)),
                  rep("Sample5", length(sample5))))
)

# Display the data structure
str(data)
head(data)

# Perform one-way ANOVA
anova_result &lt;- aov(values ~ group, data = data)
summary(anova_result)

# Calculate critical F-value
alpha &lt;- 0.05
df1 &lt;- 4  # Number of groups - 1
df2 &lt;- 18  # Total observations - number of groups
critical_f &lt;- qf(1 - alpha, df1, df2)

# Extract the F-value from ANOVA results
f_value &lt;- summary(anova_result)[[^1]]["F value"][1,1]

# Decision
cat("\nObserved F-value:", f_value, "\n")
cat("Critical F-value:", critical_f, "\n")

if (f_value &gt; critical_f) {
  cat("Decision: Reject the null hypothesis.\n")
  cat("Conclusion: There is a significant difference between at least one pair of group means.\n")
} else {
  cat("Decision: Fail to reject the null hypothesis.\n")
  cat("Conclusion: There is no significant difference between group means.\n")
}

# Visualize the data
boxplot(values ~ group, data = data, 
        main = "Comparison of Five Samples",
        xlab = "Sample Groups", ylab = "Values",
        col = c("lightblue", "lightgreen", "lightpink", "lightyellow", "lightcyan"))
```


### Problem 2: Comparing Two Samples

```R
# Problem 2: One-way ANOVA with 2 samples

# Input the data
s1 &lt;- c(27, 31, 31, 29, 30, 27, 28)
s2 &lt;- c(22, 27, 25, 23, 26, 27, 23)

# Combine data into a data frame
data2 &lt;- data.frame(
  values = c(s1, s2),
  group = factor(c(rep("S1", length(s1)), rep("S2", length(s2))))
)

# Display the data structure
str(data2)
head(data2)

# Perform one-way ANOVA
anova_result2 &lt;- aov(values ~ group, data = data2)
summary(anova_result2)

# Calculate critical F-value
alpha &lt;- 0.05
df1 &lt;- 1  # Number of groups - 1
df2 &lt;- 12  # Total observations - number of groups
critical_f2 &lt;- qf(1 - alpha, df1, df2)

# Extract the F-value from ANOVA results
f_value2 &lt;- summary(anova_result2)[[^1]]["F value"][1,1]

# Decision
cat("\nObserved F-value:", f_value2, "\n")
cat("Critical F-value:", critical_f2, "\n")

if (f_value2 &gt; critical_f2) {
  cat("Decision: Reject the null hypothesis.\n")
  cat("Conclusion: There is a significant difference between the two group means.\n")
} else {
  cat("Decision: Fail to reject the null hypothesis.\n")
  cat("Conclusion: There is no significant difference between the two group means.\n")
}

# Visualize the data
boxplot(values ~ group, data = data2, 
        main = "Comparison of Two Samples",
        xlab = "Sample Groups", ylab = "Values",
        col = c("lightblue", "lightgreen"))
```


### Problem 3: Comparing Manager Levels

```R
# Problem 3: One-way ANOVA for seminar evaluations by manager level

# Input the data
high_level &lt;- c(7, 7, 8, 7, 9, 10, 8)
midlevel &lt;- c(8, 9, 8, 10, 9, 8)
low_level &lt;- c(5, 6, 5, 7, 4)

# Combine data into a data frame
data3 &lt;- data.frame(
  ratings = c(high_level, midlevel, low_level),
  manager_level = factor(c(rep("High Level", length(high_level)),
                          rep("Midlevel", length(midlevel)),
                          rep("Low Level", length(low_level))))
)

# Display the data structure
str(data3)
head(data3)

# Perform one-way ANOVA
anova_result3 &lt;- aov(ratings ~ manager_level, data = data3)
summary(anova_result3)

# Calculate critical F-value
alpha &lt;- 0.05
df1 &lt;- 2  # Number of groups - 1
df2 &lt;- 15  # Total observations - number of groups
critical_f3 &lt;- qf(1 - alpha, df1, df2)

# Extract the F-value from ANOVA results
f_value3 &lt;- summary(anova_result3)[[^1]]["F value"][1,1]

# Decision
cat("\nObserved F-value:", f_value3, "\n")
cat("Critical F-value:", critical_f3, "\n")

if (f_value3 &gt; critical_f3) {
  cat("Decision: Reject the null hypothesis.\n")
  cat("Conclusion: There is a significant difference in evaluations according to manager level.\n")
} else {
  cat("Decision: Fail to reject the null hypothesis.\n")
  cat("Conclusion: There is no significant difference in evaluations according to manager level.\n")
}

# Visualize the data
boxplot(ratings ~ manager_level, data = data3, 
        main = "Seminar Evaluations by Manager Level",
        xlab = "Manager Level", ylab = "Evaluation Ratings (1-10)",
        col = c("lightblue", "lightgreen", "lightpink"))

# Optional: Perform Tukey's HSD test to identify which groups differ
TukeyHSD(anova_result3)
```


## Exercise 2: Two-Way ANOVA Problems

### Problem 1: Machines and Operators

```R
# Problem 1: Two-way ANOVA for machines and operators

# Input the data
machine1 &lt;- c(46, 54, 48, 46, 51)
machine2 &lt;- c(56, 55, 56, 60, 53)
machine3 &lt;- c(55, 51, 50, 51, 53)
machine4 &lt;- c(47, 56, 58, 59, 55)
operator &lt;- factor(rep(1:5, 4))
machine &lt;- factor(rep(1:4, each = 5))

# Combine data into a data frame
data4 &lt;- data.frame(
  length = c(machine1, machine2, machine3, machine4),
  operator = operator,
  machine = machine
)

# Display the data structure
str(data4)
head(data4)

# Perform two-way ANOVA
anova_result4 &lt;- aov(length ~ operator + machine + operator:machine, data = data4)
summary(anova_result4)

# Calculate critical F-values
alpha &lt;- 0.05
# For operator
df1_operator &lt;- 4  # Number of operators - 1
# For machine
df1_machine &lt;- 3  # Number of machines - 1
# For interaction
df1_interaction &lt;- 12  # (Number of operators - 1) * (Number of machines - 1)
# Residuals
df2 &lt;- 0  # Total observations - df1_operator - df1_machine - df1_interaction

# Note: Since each operator made exactly one spacer with each machine,
# there are no degrees of freedom left for the error term (no replication)
# Therefore, we'll analyze without the interaction term

# Re-perform two-way ANOVA without interaction
anova_result4_no_interaction &lt;- aov(length ~ operator + machine, data = data4)
summary(anova_result4_no_interaction)

# Extract F-values
f_value_operator &lt;- summary(anova_result4_no_interaction)[[^1]]["F value"][1,1]
f_value_machine &lt;- summary(anova_result4_no_interaction)[[^1]]["F value"][2,1]

# Calculate critical F-values
df2_no_interaction &lt;- 12  # Residual degrees of freedom
critical_f_operator &lt;- qf(1 - alpha, df1_operator, df2_no_interaction)
critical_f_machine &lt;- qf(1 - alpha, df1_machine, df2_no_interaction)

# Decision
cat("\nOperator Effect:\n")
cat("Observed F-value:", f_value_operator, "\n")
cat("Critical F-value:", critical_f_operator, "\n")

if (f_value_operator &gt; critical_f_operator) {
  cat("Decision: Reject the null hypothesis for operator effect.\n")
  cat("Conclusion: There is a significant difference between operators.\n")
} else {
  cat("Decision: Fail to reject the null hypothesis for operator effect.\n")
  cat("Conclusion: There is no significant difference between operators.\n")
}

cat("\nMachine Effect:\n")
cat("Observed F-value:", f_value_machine, "\n")
cat("Critical F-value:", critical_f_machine, "\n")

if (f_value_machine &gt; critical_f_machine) {
  cat("Decision: Reject the null hypothesis for machine effect.\n")
  cat("Conclusion: There is a significant difference between machines.\n")
} else {
  cat("Decision: Fail to reject the null hypothesis for machine effect.\n")
  cat("Conclusion: There is no significant difference between machines.\n")
}

# Visualize the data
par(mfrow = c(1, 2))
boxplot(length ~ operator, data = data4, 
        main = "Spacer Length by Operator",
        xlab = "Operator", ylab = "Length (mm)",
        col = "lightblue")

boxplot(length ~ machine, data = data4, 
        main = "Spacer Length by Machine",
        xlab = "Machine", ylab = "Length (mm)",
        col = "lightgreen")
par(mfrow = c(1, 1))

# Interaction plot
interaction.plot(data4$machine, data4$operator, data4$length,
                 type = "b", col = 1:5, lty = 1, pch = 19,
                 main = "Interaction Plot: Machine × Operator",
                 xlab = "Machine", ylab = "Mean Length (mm)",
                 trace.label = "Operator")
```


### Problem 2: Paint Types and Steel Alloys

```R
# Problem 2: Two-way ANOVA for paint types and steel alloys

# Input the data
paint_type &lt;- factor(rep(1:3, 3))
steel_alloy &lt;- factor(rep(1:3, each = 3))
resistance &lt;- c(40, 54, 47, 51, 55, 56, 56, 50, 50)

# Combine data into a data frame
data5 &lt;- data.frame(
  resistance = resistance,
  paint_type = paint_type,
  steel_alloy = steel_alloy
)

# Display the data structure
str(data5)
head(data5)

# Perform two-way ANOVA
anova_result5 &lt;- aov(resistance ~ paint_type + steel_alloy + paint_type:steel_alloy, data = data5)
summary(anova_result5)

# Calculate critical F-values
alpha &lt;- 0.05
# For paint_type
df1_paint &lt;- 2  # Number of paint types - 1
# For steel_alloy
df1_steel &lt;- 2  # Number of steel alloys - 1
# For interaction
df1_interaction &lt;- 4  # (Number of paint types - 1) * (Number of steel alloys - 1)
# Residuals
df2 &lt;- 0  # No residual degrees of freedom since there's only one observation per cell

# Re-perform two-way ANOVA without interaction
anova_result5_no_interaction &lt;- aov(resistance ~ paint_type + steel_alloy, data = data5)
summary(anova_result5_no_interaction)

# Extract F-values
f_value_paint &lt;- summary(anova_result5_no_interaction)[[^1]]["F value"][1,1]
f_value_steel &lt;- summary(anova_result5_no_interaction)[[^1]]["F value"][2,1]

# Calculate critical F-values
df2_no_interaction &lt;- 4  # Residual degrees of freedom
critical_f_paint &lt;- qf(1 - alpha, df1_paint, df2_no_interaction)
critical_f_steel &lt;- qf(1 - alpha, df1_steel, df2_no_interaction)

# Decision
cat("\nPaint Type Effect:\n")
cat("Observed F-value:", f_value_paint, "\n")
cat("Critical F-value:", critical_f_paint, "\n")

if (f_value_paint &gt; critical_f_paint) {
  cat("Decision: Reject the null hypothesis for paint type effect.\n")
  cat("Conclusion: There is a significant difference between paint types.\n")
} else {
  cat("Decision: Fail to reject the null hypothesis for paint type effect.\n")
  cat("Conclusion: There is no significant difference between paint types.\n")
}

cat("\nSteel Alloy Effect:\n")
cat("Observed F-value:", f_value_steel, "\n")
cat("Critical F-value:", critical_f_steel, "\n")

if (f_value_steel &gt; critical_f_steel) {
  cat("Decision: Reject the null hypothesis for steel alloy effect.\n")
  cat("Conclusion: There is a significant difference between steel alloys.\n")
} else {
  cat("Decision: Fail to reject the null hypothesis for steel alloy effect.\n")
  cat("Conclusion: There is no significant difference between steel alloys.\n")
}

# Visualize the data
par(mfrow = c(1, 2))
boxplot(resistance ~ paint_type, data = data5, 
        main = "Corrosion Resistance by Paint Type",
        xlab = "Paint Type", ylab = "Resistance",
        col = "lightblue")

boxplot(resistance ~ steel_alloy, data = data5, 
        main = "Corrosion Resistance by Steel Alloy",
        xlab = "Steel Alloy", ylab = "Resistance",
        col = "lightgreen")
par(mfrow = c(1, 1))

# Interaction plot
interaction.plot(data5$steel_alloy, data5$paint_type, data5$resistance,
                 type = "b", col = 1:3, lty = 1, pch = 19,
                 main = "Interaction Plot: Steel Alloy × Paint Type",
                 xlab = "Steel Alloy", ylab = "Mean Resistance",
                 trace.label = "Paint Type")
```


### Problem 3: Tyre Types and Shock Absorber Settings

```R
# Problem 3: Two-way ANOVA for tyre types and shock absorber settings

# Input the data
tyre_A1 &lt;- c(5, 6, 8)  # Tyre type A1 with comfort setting
tyre_A1 &lt;- c(tyre_A1, c(8, 5, 3))  # Tyre type A1 with normal setting
tyre_A1 &lt;- c(tyre_A1, c(6, 9, 12))  # Tyre type A1 with sport setting

tyre_A2 &lt;- c(9, 7, 7)  # Tyre type A2 with comfort setting
tyre_A2 &lt;- c(tyre_A2, c(10, 9, 8))  # Tyre type A2 with normal setting
tyre_A2 &lt;- c(tyre_A2, c(12, 10, 9))  # Tyre type A2 with sport setting

# Create factors for tyre type and shock absorber setting
tyre_type &lt;- factor(rep(c("A1", "A2"), each = 9))
shock_setting &lt;- factor(rep(rep(c("Comfort", "Normal", "Sport"), each = 3), 2))

# Combine data into a data frame
data6 &lt;- data.frame(
  roadholding = c(tyre_A1, tyre_A2),
  tyre_type = tyre_type,
  shock_setting = shock_setting
)

# Display the data structure
str(data6)
head(data6)

# Perform two-way ANOVA
anova_result6 &lt;- aov(roadholding ~ tyre_type + shock_setting + tyre_type:shock_setting, data = data6)
summary(anova_result6)

# Calculate critical F-values
alpha &lt;- 0.05
# For tyre_type
df1_tyre &lt;- 1  # Number of tyre types - 1
# For shock_setting
df1_shock &lt;- 2  # Number of shock settings - 1
# For interaction
df1_interaction &lt;- 2  # (Number of tyre types - 1) * (Number of shock settings - 1)
# Residuals
df2 &lt;- 12  # Total observations - df1_tyre - df1_shock - df1_interaction

# Extract F-values
f_value_tyre &lt;- summary(anova_result6)[[^1]]["F value"][1,1]
f_value_shock &lt;- summary(anova_result6)[[^1]]["F value"][2,1]
f_value_interaction &lt;- summary(anova_result6)[[^1]]["F value"][3,1]

# Calculate critical F-values
critical_f_tyre &lt;- qf(1 - alpha, df1_tyre, df2)
critical_f_shock &lt;- qf(1 - alpha, df1_shock, df2)
critical_f_interaction &lt;- qf(1 - alpha, df1_interaction, df2)

# Decision
cat("\nTyre Type Effect:\n")
cat("Observed F-value:", f_value_tyre, "\n")
cat("Critical F-value:", critical_f_tyre, "\n")

if (f_value_tyre &gt; critical_f_tyre) {
  cat("Decision: Reject the null hypothesis for tyre type effect.\n")
  cat("Conclusion: There is a significant difference between tyre types.\n")
} else {
  cat("Decision: Fail to reject the null hypothesis for tyre type effect.\n")
  cat("Conclusion: There is no significant difference between tyre types.\n")
}

cat("\nShock Absorber Setting Effect:\n")
cat("Observed F-value:", f_value_shock, "\n")
cat("Critical F-value:", critical_f_shock, "\n")

if (f_value_shock &gt; critical_f_shock) {
  cat("Decision: Reject the null hypothesis for shock absorber setting effect.\n")
  cat("Conclusion: There is a significant difference between shock absorber settings.\n")
} else {
  cat("Decision: Fail to reject the null hypothesis for shock absorber setting effect.\n")
  cat("Conclusion: There is no significant difference between shock absorber settings.\n")
}

cat("\nInteraction Effect:\n")
cat("Observed F-value:", f_value_interaction, "\n")
cat("Critical F-value:", critical_f_interaction, "\n")

if (f_value_interaction &gt; critical_f_interaction) {
  cat("Decision: Reject the null hypothesis for interaction effect.\n")
  cat("Conclusion: There is a significant interaction between tyre type and shock absorber setting.\n")
} else {
  cat("Decision: Fail to reject the null hypothesis for interaction effect.\n")
  cat("Conclusion: There is no significant interaction between tyre type and shock absorber setting.\n")
}

# Visualize the data
par(mfrow = c(1, 2))
boxplot(roadholding ~ tyre_type, data = data6, 
        main = "Roadholding by Tyre Type",
        xlab = "Tyre Type", ylab = "Roadholding",
        col = "lightblue")

boxplot(roadholding ~ shock_setting, data = data6, 
        main = "Roadholding by Shock Absorber Setting",
        xlab = "Shock Absorber Setting", ylab = "Roadholding",
        col = "lightgreen")
par(mfrow = c(1, 1))

# Interaction plot
interaction.plot(data6$shock_setting, data6$tyre_type, data6$roadholding,
                 type = "b", col = 1:2, lty = 1, pch = 19,
                 main = "Interaction Plot: Shock Setting × Tyre Type",
                 xlab = "Shock Absorber Setting", ylab = "Mean Roadholding",
                 trace.label = "Tyre Type")

# Optional: Perform Tukey's HSD test to identify which groups differ
TukeyHSD(anova_result6)
```




# References


###### Information
- date: 2025.04.17
- time: 22:46