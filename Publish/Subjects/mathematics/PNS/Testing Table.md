Based on the search results, I'll provide a comprehensive overview of statistical tests used in probability and statistics, organized in a markdown table that explains when to use each test.

Statistical tests are essential tools for analyzing data and making inferences about populations. They help researchers determine whether observed patterns in data are statistically significant or merely due to chance. Here's a detailed breakdown of the most common statistical tests and their appropriate applications:

## Common Statistical Tests in Probability and Statistics

|Test Type|When to Use|Key Assumptions|Example Application|
|---|---|---|---|
|**T-tests**||||
|One-sample t-test|When comparing a sample mean to a known value|Continuous data, approximately normal distribution|Testing if average height of sixth graders is greater than four feet[3](https://www.graphpad.com/guides/the-ultimate-guide-to-t-tests)|
|Independent samples t-test (Equal variances)|When comparing means of two unrelated groups with equal variances|Continuous data, independent samples, equal variances|Comparing average heights of men and women[1](https://www.enago.com/academy/right-statistical-test/)|
|Independent samples t-test (Unequal variances)|When comparing means of two unrelated groups with unequal variances|Continuous data, independent samples|Comparing cancer patients and pregnant women in a population[1](https://www.enago.com/academy/right-statistical-test/)|
|Paired samples t-test|When comparing two related samples (before/after)|Continuous data, paired observations|Measuring performance scores before and after training[1](https://www.enago.com/academy/right-statistical-test/)|
|**ANOVA Tests**||||
|One-way ANOVA|When comparing means of three or more groups with one factor|Continuous data, independent samples, normal distribution|Comparing effectiveness of multiple drug treatments[4](https://www.graphpad.com/guides/the-ultimate-guide-to-anova)|
|Two-way ANOVA|When comparing means with two factors|Continuous data, independent samples, normal distribution|Testing how two factors (e.g., drug and dosage) affect outcomes[1](https://www.enago.com/academy/right-statistical-test/)|
|MANOVA|When comparing multiple dependent variables across groups|Multiple continuous dependent variables|Examining statistical differences between one continuous dependent variable and independent grouping variables[1](https://www.enago.com/academy/right-statistical-test/)|
|**Regression Tests**||||
|Simple Linear Regression|When determining relationship between one independent and one dependent variable|Linear relationship, continuous variables|Financial forecasting, house price estimates[6](https://www.appier.com/en/blog/5-types-of-regression-analysis-and-when-to-use-them)|
|Multiple Linear Regression|When determining relationship between multiple independent variables and one dependent variable|Linear relationships, continuous variables|Sales forecasting with multiple factors[1](https://www.enago.com/academy/right-statistical-test/)[6](https://www.appier.com/en/blog/5-types-of-regression-analysis-and-when-to-use-them)|
|Logistic Regression|When predicting categorical outcomes|Binary or categorical dependent variable|Identifying data anomalies, predictive fraud analysis[1](https://www.enago.com/academy/right-statistical-test/)|
|**Correlation Tests**||||
|Pearson Correlation|When measuring linear relationship between two continuous variables|Continuous data, linear relationship, neither variable is a response variable|Measuring relationship between math and science exam scores[7](https://www.statology.org/when-to-use-correlation/)|
|**Non-parametric Tests**||||
|Chi-square test|When comparing categorical variables|Categorical data, random sample|Analyzing survey responses, comparing observed vs. expected frequencies[5](https://www.investopedia.com/terms/c/chi-square-statistic.asp)|
|Mann-Whitney U Test|When comparing two independent groups with non-normal distributions|Continuous data, non-normal distribution, independent samples|Comparing viral load between treated and untreated groups in an HIV study[8](https://www.technologynetworks.com/informatics/articles/mann-whitney-u-test-assumptions-and-example-363425)|
|Kruskal-Wallis H Test|When comparing three or more independent groups with non-normal distributions|Continuous data, non-normal distribution, independent samples|Comparing multiple groups when ANOVA assumptions are violated[9](https://decodingdatascience.com/statistical-tests-understanding-their-significance-and-types/)|
|Wilcoxon Signed-Rank Test|When comparing two related samples with non-normal distributions|Continuous data, non-normal distribution, paired samples|Comparing before and after measurements when t-test assumptions are violated[9](https://decodingdatascience.com/statistical-tests-understanding-their-significance-and-types/)|
|**Other Tests**||||
|Z-test|When comparing two population means with known variances and large sample sizes|Normal distribution, known population variances, large samples|Determining if two population means are different[1](https://www.enago.com/academy/right-statistical-test/)|

## Choosing the Right Statistical Test

The selection of an appropriate statistical test depends on several factors:

1. **Type of data**: Continuous (numerical) vs. categorical
    
2. **Number of groups**: One, two, or multiple groups
    
3. **Relationship between groups**: Independent vs. dependent (paired) samples
    
4. **Distribution assumptions**: Parametric (normal distribution) vs. non-parametric
    
5. **Research question**: Comparison, relationship, or prediction
    

Understanding these factors helps in selecting the most appropriate test for your specific analysis needs. For example, if you're comparing means between two independent groups with continuous data that follows a normal distribution, an independent samples t-test would be appropriate. However, if your data is categorical, a chi-square test would be more suitable[11](https://builtin.com/data-science/t-test-vs-chi-square).

I hope this comprehensive table helps you understand when to use different statistical tests in probability and statistics.

### Citations:

1. [https://www.enago.com/academy/right-statistical-test/](https://www.enago.com/academy/right-statistical-test/)
2. [https://www.jmp.com/en_in/statistics-knowledge-portal/t-test.html](https://www.jmp.com/en_in/statistics-knowledge-portal/t-test.html)
3. [https://www.graphpad.com/guides/the-ultimate-guide-to-t-tests](https://www.graphpad.com/guides/the-ultimate-guide-to-t-tests)
4. [https://www.graphpad.com/guides/the-ultimate-guide-to-anova](https://www.graphpad.com/guides/the-ultimate-guide-to-anova)
5. [https://www.investopedia.com/terms/c/chi-square-statistic.asp](https://www.investopedia.com/terms/c/chi-square-statistic.asp)
6. [https://www.appier.com/en/blog/5-types-of-regression-analysis-and-when-to-use-them](https://www.appier.com/en/blog/5-types-of-regression-analysis-and-when-to-use-them)
7. [https://www.statology.org/when-to-use-correlation/](https://www.statology.org/when-to-use-correlation/)
8. [https://www.technologynetworks.com/informatics/articles/mann-whitney-u-test-assumptions-and-example-363425](https://www.technologynetworks.com/informatics/articles/mann-whitney-u-test-assumptions-and-example-363425)
9. [https://decodingdatascience.com/statistical-tests-understanding-their-significance-and-types/](https://decodingdatascience.com/statistical-tests-understanding-their-significance-and-types/)
10. [https://www.investopedia.com/terms/t/t-test.asp](https://www.investopedia.com/terms/t/t-test.asp)
11. [https://builtin.com/data-science/t-test-vs-chi-square](https://builtin.com/data-science/t-test-vs-chi-square)
12. [https://builtin.com/data-science/probability-questions](https://builtin.com/data-science/probability-questions)
13. [https://thirdspacelearning.com/us/blog/probability-questions/](https://thirdspacelearning.com/us/blog/probability-questions/)
14. [https://testbook.com/objective-questions/mcq-on-probability--5eea6a1039140f30f369e860](https://testbook.com/objective-questions/mcq-on-probability--5eea6a1039140f30f369e860)
15. [https://www.sajaa.co.za/index.php/sajaa/article/view/2916/3193](https://www.sajaa.co.za/index.php/sajaa/article/view/2916/3193)
16. [https://www.statsmadeasy.com/stats-concepts/6-probabilities-hypothesis-testing](https://www.statsmadeasy.com/stats-concepts/6-probabilities-hypothesis-testing)
17. [https://www.khanacademy.org/math/statistics-probability/probability-library](https://www.khanacademy.org/math/statistics-probability/probability-library)
18. [https://www.scribbr.com/statistics/statistical-tests/](https://www.scribbr.com/statistics/statistical-tests/)
19. [https://www.scribbr.com/statistics/test-statistic/](https://www.scribbr.com/statistics/test-statistic/)
20. [https://www.math.ucdavis.edu/~gravner/MAT135A/resources/chpr.pdf](https://www.math.ucdavis.edu/~gravner/MAT135A/resources/chpr.pdf)
21. [https://en.wikipedia.org/wiki/List_of_statistical_tests](https://en.wikipedia.org/wiki/List_of_statistical_tests)
22. [https://www.simplilearn.com/tutorials/statistics-tutorial/hypothesis-testing-in-statistics](https://www.simplilearn.com/tutorials/statistics-tutorial/hypothesis-testing-in-statistics)
23. [https://www.statstutor.ac.uk/resources/uploaded/tutorsquickguidetostatistics.pdf](https://www.statstutor.ac.uk/resources/uploaded/tutorsquickguidetostatistics.pdf)
24. [https://www.jmp.com/en_in/statistics-knowledge-portal/t-test.html](https://www.jmp.com/en_in/statistics-knowledge-portal/t-test.html)
25. [https://www.scribbr.com/statistics/t-test/](https://www.scribbr.com/statistics/t-test/)
26. [https://statisticsbyjim.com/hypothesis-testing/kruskal-wallis-test/](https://statisticsbyjim.com/hypothesis-testing/kruskal-wallis-test/)
27. [https://datatab.net/tutorial/wilcoxon-test](https://datatab.net/tutorial/wilcoxon-test)
28. [https://www.qualtrics.com/en-au/experience-management/research/t-test-analysis/](https://www.qualtrics.com/en-au/experience-management/research/t-test-analysis/)
29. [https://www.scribbr.com/statistics/one-way-anova/](https://www.scribbr.com/statistics/one-way-anova/)
30. [https://www.scribbr.com/statistics/chi-square-tests/](https://www.scribbr.com/statistics/chi-square-tests/)
31. [https://www.qualtrics.com/en-au/experience-management/research/regression-analysis/](https://www.qualtrics.com/en-au/experience-management/research/regression-analysis/)
32. [https://www.scribbr.com/methodology/correlational-research/](https://www.scribbr.com/methodology/correlational-research/)
33. [https://www.statstutor.ac.uk/resources/uploaded/mannwhitney.pdf](https://www.statstutor.ac.uk/resources/uploaded/mannwhitney.pdf)
34. [https://www.technologynetworks.com/informatics/articles/the-kruskal-wallis-test-370025](https://www.technologynetworks.com/informatics/articles/the-kruskal-wallis-test-370025)
35. [https://www.technologynetworks.com/informatics/articles/the-wilcoxon-signed-rank-test-370384](https://www.technologynetworks.com/informatics/articles/the-wilcoxon-signed-rank-test-370384)
36. [https://www.testprepreview.com/modules/probabilty.htm](https://www.testprepreview.com/modules/probabilty.htm)
37. [https://byjus.com/maths/probability-questions/](https://byjus.com/maths/probability-questions/)
38. [https://www.geeksforgeeks.org/probability-questions/](https://www.geeksforgeeks.org/probability-questions/)
39. [https://www.hitbullseye.com/Probability-Examples.php](https://www.hitbullseye.com/Probability-Examples.php)
40. [https://www.youtube.com/watch?v=IIFjF0tiE_M](https://www.youtube.com/watch?v=IIFjF0tiE_M)

---

Answer from Perplexity: [pplx.ai/share](https://www.perplexity.ai/search/pplx.ai/share)