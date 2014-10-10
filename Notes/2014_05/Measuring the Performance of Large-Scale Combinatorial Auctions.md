---
title: Measuring the Performance of Large-Scale Combinatorial Auctions: A Structural Estimation Approach
tags: ["paper reading notes", "May", "2014", "Management Science", "auction"]
notebook: Paper Reading -- May 2014
---

### Measuring the Performance of Large-Scale Combinatorial Auctions: A Structural Estimation Approach

by Sang Won Kim, Marcelo Olivares, Gabriel Y. Weintraub

Source: Management Science, May 2014

* This paper studies the combinatorial auctions: multiple firms bid for multiple items simultaneously in a one-round first-price auction.

* The case they pay special attentions to is the economy-of-scale effect. A firm could lower its costs if winning multiple bids because of the cost synergy: one fixed setup cost, manufacturing multiple items.

* To refresh the memory of the model for auction game: auctioneer attempts to maximize total revenue. We have multiple bidders, each bidder knows his/her own private costs but not others' costs. They assume a distribution (either from past observations or assumptions) of their opponents' bids (a function of costs and bidding strategies). Then they choose their best strategy.

* Key first-order optimality condition for a bidder:

    $$ b = c - ([dG(b)]^T)^{-1} * G(b)        \qquad (*) $$

    where `b` is the bidding vector of item combinations (i.e., `b` consists of the bid for each possible combination of items. It's size is up to 2^N - 1 where N is the number of items), `c` is the cost vector of item combinations, `G(b)` is the a matrix of winning probability of each bidder and each item using bid `b`, and `dG(b)` is the Jacobian matrix (derivative) of `G(b)` with respective to `b`.

    The first-order condition (*) shows that the optimal bid is cost `c` plus a cost markup term `-([dG(b)]^T)^-1 * G(b)`.

* The paper suggests a two-step process to estimate `G(b)` for a bidder and that bidder's cost vector:
    1. Use historical bid data to estimate the distribution of bids of all bidders.
    2. Use simulation to estimate the cost vector of each bidder.

    To be more specific, the simulation generates bids from the bid data, and determine who wins which bid. Then it averages over a large number of simulation results to get `G(b)` and the Jacobian matrix. Finally, use (*) to get the estimate cost.

* My thoughts:

    The paper is quite technical in some parts mostly due to the complexity of first-price auction. But it's great to read through it and jog the memory of auction games with incomplete information. The basic settings of these games and a possible solution are now quite clear to me and hopefully will be helpful when I encounter similar problems in the future.

