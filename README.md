Estimation & Bootstrapping — Quantifying Uncertainty Without a Formula
Objective
I used sampling distributions, confidence intervals, and bootstrap methods to measure uncertainty in estimates from real data.
Methodology
- Loaded the UCI Adult Census Income dataset with 32,561 respondents.
- Compared the standard deviation of individual observations with the standard error of a sample estimate.
- Checked the \(s/\sqrt{n}\) relationship across four different sample sizes.
- Built parametric confidence intervals using the Central Limit Theorem.
- Compared how quickly the sampling distribution became approximately normal for age versus capital gains.
- Implemented bootstrap resampling by hand and with scipy.stats.bootstrap.
- Examined a case where the bootstrap SE of median age was 0.0000 because repeated ages pinned the median at the same value.
- Compared percentile and BCa bootstrap confidence intervals.
- Bootstrapped the difference in mean weekly work hours between two groups.
- Used an AI-generated bootstrap interval function, revised the prompt, and checked the results against my own calculations.
- Ran a coverage simulation using lognormal data with a sample size of 50.
Key Findings
The standard deviation described variation among individual observations, while the standard error measured uncertainty in an estimate and became smaller as sample size increased.
The CLT worked relatively quickly for age, but much more slowly for the highly skewed capital gains variable. The bootstrap also showed that unusual results are not always errors. For median age, the bootstrap SE was exactly 0.0000 because the large number of tied ages kept the median fixed across resamples.
In the coverage simulation, the nominal 95% parametric interval for the mean covered 92.5% of the time, while the percentile bootstrap interval covered 91.5%. The difference was within the Monte Carlo standard error of about 1.3 percentage points, so the two methods performed similarly and both slightly under-covered. For the median, the mean-centered parametric interval covered only about 66.8%, while the bootstrap stayed much closer to the nominal level.
