This document, "Introduction to bootstrapping SAMPLING IN PYTHON" by James Chapman, Curriculum Manager at DataCamp, covers sampling with replacement (resampling) and its application in bootstrapping, standard error, and confidence intervals.

**Sampling and Resampling**

  * **Sampling without replacement** is a simple random sample from a population.
  * **Sampling with replacement** (resampling) is a proxy where each item in a sample is treated as a representation of many hypothetical population items.

**Bootstrapping**

  * Bootstrapping is the opposite of sampling; it builds a theoretical population from a single sample.
  * Its use case is to develop an understanding of sampling variability using one sample.
  * The **bootstrapping process** involves:
    1.  Making a resample of the same size as the original sample.
    2.  Calculating the statistic of interest (e.g., mean flavor) for this bootstrap sample.
    3.  Repeating steps 1 and 2 many times (e.g., 1000 or 5000 times).
  * The resulting statistics are **bootstrap statistics**, which form a **bootstrap distribution**.
  * The mean of the bootstrap distribution is usually close to the sample mean but may not be a good estimate of the population mean because bootstrapping cannot correct biases from sampling.

**Standard Error and Confidence Intervals**

  * **Standard error** is the standard deviation of the statistic of interest.
  * The standard deviation of a bootstrap statistic is a good approximation of the standard error.
  * **Estimated standard error** is the standard deviation of the bootstrap distribution for a sample statistic.
  * The population standard deviation is approximately the standard error multiplied by the square root of the sample size ($\\text{Population std. dev} \\approx \\text{Std. Error} \\times \\sqrt{\\text{Sample size}}$).
  * A **confidence interval** (CI) is a range of plausible values for an estimate, such as a point estimate.
      * The difference between the point estimate and the CI boundary is the **margin of error**.
      * CIs can be calculated using the **quantile method** (e.g., $\\text{np.quantile}(\\text{coffee\_boot\_distn}, 0.025)$ and $0.975$).
      * CIs can also be calculated using the **standard error method** with the Inverse Cumulative Distribution Function (Inv. CDF), implemented in Python as $\\text{norm.ppf()}$.
  * Bootstrap distributions can be assumed to be normally distributed for confidence intervals.
