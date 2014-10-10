---
title: Hierarchical Bayes Models
tags: ["paper reading notes", "May", "2014", "hierarchical Bayes"]
notebook: Paper Reading -- May 2014
---

### Hierarchical Bayes Models

Source: Multiple sources found online.

**Purpose:** The paper _Examining the Impact of Ranking on Consumer Behavior and Search Engine Revenue_ uses hierachical Bayesian models. I searched online and found several papers and tutorials about hierachical Bayesian models. The file "Hierachical Bayes Presentation.pdf" provides the most clear introductory explanations of this approach.

* A key problem the hierarchical Bayes models try to solve is that we have data from many individuals, but only one or few data for each individual. If we aggregate all data, we ignore the heterogeneity of each individual, but if we analyze on the individual level, data is too few which means too much noise.

* Hierachical Bayes models take a compromise between the two extreme approaches mentioned above. It assumes that each individual's data come from a model whose parameters come from a common distribution.

* Examples:

    - With a table of data of the weights of each of 50 rats in every 10 days for a year (50 * 36 table), one can either pool all data and do a regression for the relation of weight `w` and time `t`: `w = b0 + b1 * t`. Or do a regression for each rat `i`: `w(i) = b0(i) + b1(i) * t`. Hierachical Bayes model instead assumes that each `b0(i)` and `b1(1)` come from a common distribution `b0 ~ Normal(mu, sigma^2)` and `b1 ~ Normal(mu', sigma'^2)`. Then one can use some comuptational approach (most commonly MCMC) to estimate the paramters `mu`, `sigma`, `mu'`, and `sigma'`.

    - With the numbers of home-game win-loss of all NFL football teams, one can either pool all the data and get the average home-game win rate, or take the average for each team. Hierachical Bayes model does a partial pooling, assuming the win rates (p1, p2, ..., pN) are random draws from a larger population. The distribution of the rates is called a _prior_ distribution.

        For this example, if we have the following assumptions:

            Y(i) ~ Binomial(n(i), p(i))

        `Y(i)` is the distribution of the number of winning home games for team `i`. `n(i)` is the number of home games team `i` played.

            p(i) ~ Beta(alpha, beta)

        `p(i)` is the distribution of the home-game winning probability for team `i`.

            Note: Poterior is proportional to likelyhood * prior.

        Then with some algebra, given the observed number of winning home games `[Y(1), Y(2), ..., Y(N)]`, we have:

            p(i) | [Y(1), Y(2), ..., Y(N)] ~ Beta(alpha + Y(i), beta + (n(i) - Y(i)))

        Using this result, we can obtain the distribution of the number of winning home games for each team.

        This is an over-simplified model for illustration purpose. In reality, hierachical models need to incorporate many other factors, such as opponents, timing, improvement, injuries, etc. The model quickly become too complicated, and one needs to use computational tools, majorly Markov Chain Monte Carlo (MCMC), to do the estimations.

* Quick summary: The hierachical model pools the statistics of data from all individuals to estimate for each individual -- this is called "learning from others". It is especially useful when individual data are scarce, but the data from all people are abundant.

