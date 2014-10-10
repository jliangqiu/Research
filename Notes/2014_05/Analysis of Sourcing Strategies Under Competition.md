---
title: Home or Overseas? An Analysis of Sourcing Strategies Under Competition
tags: ["paper reading notes", "May", "2014", "Management Science", "game theory", "sourcing"]
notebook: Paper Reading -- May 2014
---

### Home or Overseas? An Analysis of Sourcing Strategies Under Competition

by Xiaole Wu, Fuqiang Zhang

Source: Management Science, May 2014

* Motivated by recent backshoring trend in US, the authors study a sourcing game where firms choose between _efficient sourcing_ (sourcing from overseas) and _responsive sourcing_ (sourcing from a home country).

* Key findings:
    1. A firm may still use efficient sourcing in equilibrium even when the cost advantage associated with efficient sourcing does not exist.
    2. A cost hike in efficient sourcing (such as increase of labor cost in Asia) may benefit all firms in the industry.
    3. More firms will shift from efficient sourcing to responsive sourcing (i.e., backshore) if market size shrinks, or demand becomes more volatile, or the sourcing costs rise.
    4. Backshoring reduces the competition on the cost dimension, but also has big impact on the other firms in the market.

* Approach:
    - Game theoretic model with _two_ firms.
    - The firms engage in quantity competition by selling substitutable goods.
    - Two strategy options:
        1. Efficient sourcing -- low procurement cost, but long lead time.
        2. Responsive sourcing -- high procurement cost, but short lead time. Also, they observe better market signal when making the decision.
    - Two-stage game:
        1. They first choose strategies.
        2. Then they compete by determining the quantities they want to sell in market (Cournot game).

* The timeline of the game:

        +-------------------------+-------------------------------+--------------------------------+-----------------+
        | Time 0                  | Time 1                        | Time 2                         | Time 3          |
        +=========================+===============================+================================+=================+
        | Firms choose strategies | Efficient firm(s) place order | Responsive firm(s) place order | Sell products   |
        +-------------------------+-------------------------------+--------------------------------+-----------------+
        |                         | Demand signals at time 1      | Demand signals at time 2       | Demand realized |
        +-------------------------+-------------------------------+--------------------------------+-----------------+

    Demand signal at time 2 is less noisy than the signal at time 1.

* Under deterministic demand (variance = 0), both firms using efficient sourcing is the unique equilibrium.

* There exists a unique Bayesian Nash Equilibrium (equilibrium based on each player's belief) with one firm choosing efficiency sourcing and one firm choosing responsive sourcing.

    The equilibrium profit for each firm has two terms -- a term with profit under no demand uncertainty (efficiency term), and a term with additional profit due to demand uncertainty (information term).

    Assume firm A chooses efficiency sourcing, and firm B chooses responsive sourcing. The efficiency profit term for firm A is greater than the one for firm B, but firm A's information profit term is smaller.

* There is also a unique Bayesian Nash Equilibrium if both firms choose the same strategy. It is a symmetric equilibrium, i.e., both firms choose the same quantity to produce. Firms' profits increase in the signal accuracy (equivalently, decrease of the variance).

* A surprising result: even when the cost for efficient sourcing is equal to the cost of responsive sourcing, there still exists an equilibrium where one firm chooses efficient sourcing and the other chooses responsive sourcing. Assume firm B chooses responsive sourcing. Consider the impact of firm A's strategies:

    1. Firm A still benefits from observing a more accurate demand signal if they choose responsive sourcing. This is called _accuracy effect_ in the paper.
    2. If firm A choses responsive sourcing, however, it means that the signal they get has a higher correlation with firm B's signal.

        Increased correlation will intensify competition, making firm A’s order quantity less responsive to observed signal and resulting in a lower profit. This is called the _correlation effect_ in the paper.

    3. As a result, firm A only chooses responsive sourcing when the accuracy effect dominates the correlation effect, which happens when signal in the second period is sufficiently more accurate than the signal in the first period (i.e., the gap between the variances of the demand signals in the two periods is sufficiently large).

    In the academic literature, it is well known that correlation of information plays an important role in Cournot competition. See `Vives 1999`. In the previous literatures of sourcing, competition is rarely considered. The analysis is this paper shows that in a competing environment, firms may choose differentiated sourcing strategies to reduce competition.

    Note that this is an interesting theorical result that is not yet verified by empirical studies. Its correctness is still in doubt until verified by actual data.

* The authors point out that there are literatures on the information acquisition game:

        Novshek and Sonnenschein 1982, Li et al. 1987, Vives 1988

    These papers discuss the problem that if given multiple opportunities to observe several signals at the same time, which signal is the best to observe. They found generally only symmetric equilibriua exist. This paper points out that this is because they all assume independent signals. If the signal random variables are correlated, there might exist asymmetric equilibria.

    They also mentioned the following paper:

        Daughety and Reinganum 1994

    This paper shows that a leader can obtain the perfect information, and the follower is uninformed but can infer the demand information from the leader's quantity decision. This provides incentives for a firm not to acquire any information early on because it may obtain the same information later at no cost by observing the leader’s action. This resembles the KFC's following strategy with McDonald's.

* The authors also show the following results from their model if the cost of efficient sourcing is lower than responsive sourcing:

    1. A more volatile market demand, i.e., a higher variance of demand signals, drives more firms to choose responsive sourcing.
    2. With small market size, both firms will choose responsive sourcing. With medium market size, they'll differenciate. With large market size, they will both choose efficient sourcing.
    3. If the costs of both efficient sourcing and responsive sourcing increase, but the gap maintains the same, more firms will choose responsive sourcing. This is because the relative advantage of costs as a fraction of overall costs decreases, and makes the efficient sourcing less attractive.
    4. If the cost of efficient sourcing increases (e.g., higher labor cost in Asia), sourcing equilibrium might go from both efficient sourcing to one of each. And surprisingly, both firms' profits increase in the new equilibrium. This is because the backshoring firm decreases the correlation of demand signals and alleviates the intensity of competition for the other firm. But the cost hike must be large enough to make the firm benefit from backshoring.

* The authors further examine the equilbria for multiple firms and establish similar results. It shows the robustness of these conclusions.

* My thoughts:
    - This is an interesting paper. It uses game theoretic models to explain the recent backshoring trend, and purely theoretical.
    - The paper uses Bayesian Nash Equilibrium (BNE) with incomplete information. Need to review the concepts and main results.
    - The paper also uses Cournot equilibrium. I reviewed it while reading the paper, but need some further and detailed reviews.
    - For practical purpose, most conclusions are quite intuitive and match common senses, except 1) differenciating strategies help both firms even when the cost advantage is not significant, and 2) increasing cost of efficient sourcing actually helps both firms. The first effect, however, is not verified yet by data, so one should still be skeptical. The second effect might be true, but I think it hurts the consumers.

