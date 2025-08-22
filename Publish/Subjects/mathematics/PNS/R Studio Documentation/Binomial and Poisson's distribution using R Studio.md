---
Title: Binomial and Poisson's distribution using R Studio
Status: 
marker:
  - "[[Documentations]]"
tags: 
Date: 2025.02.18
Time: 16:07
---
# Binomial and Poisson's distribution using R Studio

| Method Name                                                   | Documentation                                                 |
| ------------------------------------------------------------- | ------------------------------------------------------------- |
| [[Binomial and Poisson's distribution using R Studio#dbinom]] | Computes the PMF for the binomial distribution.               |
| [[Binomial and Poisson's distribution using R Studio#pbinom]] | Computes the CDF for the binomial distribution.               |
| [[Binomial and Poisson's distribution using R Studio#qbinom]] | Computes the quantile function for the binomial distribution. |
| [[Binomial and Poisson's distribution using R Studio#dpois]]  | Computes the PMF for the Poisson distribution.                |
| [[Binomial and Poisson's distribution using R Studio#ppois]]  | Computes the CDF for the Poisson distribution.                |
| [[Binomial and Poisson's distribution using R Studio#qpois]]  | Computes the quantile function for the Poisson distribution.  |

# R Function Documentation

## dbinom()

**Description:** Computes the probability mass function (PMF) for the binomial distribution.

**Usage:**

```r
dbinom(x, size, prob, log = FALSE)
```

**Arguments:**

- `x` _(integer)_: Number of successes.
- `size` _(integer)_: Total number of trials.
- `prob` _(numeric)_: Probability of success per trial.
- `log` _(logical, default = FALSE)_: If `TRUE`, returns the log probability.

**Example:**

```r
dbinom(48, 51, 0.5)
```

---

## pbinom()

**Description:** Computes the cumulative distribution function (CDF) for the binomial distribution.

**Usage:**

```r
pbinom(q, size, prob, lower.tail = TRUE, log.p = FALSE)
```

**Arguments:**

- `q` _(integer)_: Number of successes.
- `size` _(integer)_: Total number of trials.
- `prob` _(numeric)_: Probability of success per trial.
- `lower.tail` _(logical, default = TRUE)_: If `TRUE`, returns P(X ≤ q); if `FALSE`, returns P(X > q).
- `log.p` _(logical, default = FALSE)_: If `TRUE`, returns the log probability.

**Example:**

```r
pbinom(40, 51, 0.5)
```

---

## qbinom()

**Description:** Computes the quantile function (inverse CDF) for the binomial distribution.

**Usage:**

```r
qbinom(p, size, prob, lower.tail = TRUE, log.p = FALSE)
```

**Arguments:**

- `p` _(numeric)_: Cumulative probability.
- `size` _(integer)_: Total number of trials.
- `prob` _(numeric)_: Probability of success per trial.
- `lower.tail` _(logical, default = TRUE)_: If `TRUE`, returns smallest x such that P(X ≤ x) ≥ p.
- `log.p` _(logical, default = FALSE)_: If `TRUE`, returns log probability.

**Example:**

```r
qbinom(0.25, 51, 0.5)
```

---

## dpois()

**Description:** Computes the probability mass function (PMF) for the Poisson distribution.

**Usage:**

```r
dpois(x, lambda, log = FALSE)
```

**Example:**

```r
dpois(3, 7.6)
```

---

## ppois()

**Description:** Computes the cumulative distribution function (CDF) for the Poisson distribution.

**Usage:**

```r
ppois(q, lambda, lower.tail = TRUE, log.p = FALSE)
```

**Example:**

```r
ppois(3, 7.6)
```

---

## qpois()

**Description:** Computes the quantile function for the Poisson distribution.

**Usage:**

```r
qpois(p, lambda, lower.tail = TRUE, log.p = FALSE)
```

**Example:**

```r
qpois(0.25, 7.6)
```

---


# References

###### Information

- date: 2025.02.18
- time: 16:07