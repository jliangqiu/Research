---
title: Markov Chain Monte Carlo
tags: ["paper reading notes", "May", "2014", "MCMC"]
notebook: Paper Reading -- May 2014
---

### Markov Chain Monte Carlo

Source Multiple sources found online

**Purpose:** Review the Markov Chain Monte Carlo method that is used for comutational in Hierarchical Bayes models (and many other applications).

- We want a Markov chain whose stationary distribution is the poterior distribution `p(theta | Y)`, where `theta` is the unkown parameters that we want to characterize, and `Y` is the observation of outcome. Let this distribution be `f(theta)`. (With given `Y`.)

- For a stationary distribution, the probability of having each state should be balanced. Let `q(theta, theta')` be the probability of jumping from state `theta` to `theta'`. If `f(·)` is a stationary distribution, we have

        f(theta) * q(theta, theta') = f(theta') * q(theta', theta)

    It means the mass that jumps from `theta` to `theta'` is equal to the mass jumping back from `theta'` to `theta`.

- If we have, for example,

        f(theta) * q(theta, theta') > f(theta') * q(theta', theta)

    It means either too much mass is put on `theta`/too little mass is put on `theta'`, or we jump too much from `theta` to `theta'` than `theta'` to `theta`.

- **Idea:** Correct this "imbalance" with a simple accept-reject step: Reject some of the jumps from `theta` to `theta'`. (Metropolis-Hastings Algorithm.)

    * Let `alpha(theta, theta')` be the probability of accepting a jump from `theta` to `theta'` (and `alpha(theta', theta)` is the probability of the reverse jump).

    * The modified balance equation is now:

            f(theta) * q(theta, theta') * alpha(theta, theta') = f(theta') * q(theta', theta) * alpha(theta', theta)

    * Set `alpha(theta', theta)` to 1 because we don't need to reject any of these jumps. Therefore the acceptance probability is:

            alpha(theta, theta') = [ f(theta') * q(theta', theta) ] / [ f(theta) * q(theta, theta') ]

        __Accept every step that goes "uphill" and accept only some fraction of the steps that go "downhill".__

- Complete Procedure:

    Start with `theta(0)`. For iterations `t` = 1, 2, ..., `T`:

    * Generate a candidate value `theta'` from `q(theta(t - 1), theta')`.
    * Compute the acceptance probability:

            alpha = min{ [ f(theta') * q(theta', theta(t-1)) ] / [ f(theta(t-1)) * q(theta(t-1), theta') ], 1 }

    * Draw `u ~ U(0, 1)`
    * If `u < alpha`, set `theta(t) = theta'`.
    * If `u > alpha`, set `theta(t) = theta(t - 1)` (keep a new copy of the previous draw).

- People usually plot the chosen `theta` with each iteration. This is called a _trace plot_. By picking sample `theta` out of every 10 or 20 iterations after the procedure converges, one can plot the posterior distribution.

- Two practical issues:

    1. Convergence: How do we know the Markov chain converged, and how do we know if the initial value `theta(0)` has an impact on the results?

        Solution: Run multiple chains with widespread starting points. Compute `R` by `Gelman and Robin (1992)`, the most common convergence  diagnostic. Throw away the first half of iterations, and use only the second half, if `R < 1.1`. Otherwise, run the chain longer.

    2. Tuning parameters. If we use normal distribution `theta' ~ Normal(theta(t), sigma^2)` to generate new `theta'`, we need to choose a right `sigma`. If it is too small, we explore the space too slowly, and maybe we'll get stuck in a local mode forever. If it is too big, we'll skip lots of posterior mass and will accept in very few steps.

        Solution: Tune `sigma` for the first 100 iterations, in order to achieve around 50% acceptance rate.

