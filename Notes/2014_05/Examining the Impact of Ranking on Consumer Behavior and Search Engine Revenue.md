---
title: Examining the Impact of Ranking on Consumer Behavior and Search Engine Revenue
tags: ["paper reading notes", "May", "2014", "Management Science", "ranking", "online business", "revenue management", "business analytics"]
notebook: Paper Reading -- May 2014
---

### Examining the Impact of Ranking on Consumer Behavior and Search Engine Revenue

by Anindya Ghose, Panagiotis G. Ipeirotis, Beibei Li

Source: Management Science, May 2014

* The paper studies the ranking effect, the interaction between ranking and rating, and personalized ranking effect.

* Data set: 1) Approximately one million online sessions from Travelocity between November 2008 and January 2009, and 2) randomized experiments using a real-world hotel search engine application.

* Goals of study:

    1. Examine the position effect in product search engines, conditional on its interaction with product ratings.
    2. Examine the effect of different ranking mechanisms on product search engine revenue.
    3. Examine how different kinds of personalized ranking mechanisms in product search engines affect consumer behavior and search engine revenues.

* The main conclusion are:

    1. A consumer-utility-based ranking mechanism can lead to a significant increase in overall search engine revenue.
    2. Significant interplay occurs between search engine ranking and product ratings. More expensive hotels are more sensitive to the online ranking effect. On the other hand, hotels with a lower customer rating are more likely to benefit from being placed on the top of the screen.
    3. An “active” personalized ranking system (wherein users can interact with and customize the ranking algorithm) leads to higher clicks but lower purchase propensities and lower search engine revenue compared with a “passive” personalized ranking system (wherein users cannot interact with the ranking algorithm).

* Approach: They build a model with multiple variables, such as Rank, Rank^2, Page, Price, Rating, Review Count, Total Number of Hotels, and Brand. They chose the functions using various equations from the literature. Then they fit it into a hierachical Bayesian model, and use MCMC to estimate the coefficients for the sum of all these variables.

* Noticeable points from other studied mentioned in this paper:
    * A consumer-utility-based search engine ranking system can lead to an increase in consumer surplus.

            Ghose et al. 2012

    * The paper finds that utility-based ranking mechanism not only maximizes the surplus for consumers (Ghose et al. 2012) but also maximizes the revenue for search engines.

    * Rank order and page number are significant determinant of clicks on the results of a search engine query.

            Rutz et al. 2012, Ghose and Yang 2009, Jerath et al. 2011, Rutz and Trusov 2011, Ghose et al. 2013

    * Rank has a significant and nonlinear effect in the context of keyword advertising. Meanwhile, negative effect of rank on CTR increases at a decreasing rate.

            Ghose and Yang 2009, Agarwal et al. 2011, Baye et al. 2009

    * User ratings affect click-through rates on search engines.

            De los Santos and Koulayev 2013, Yao and Mela 2011

    * Product brand can influence consumers’ perceptions of quality and willingness to buy.

            Dodds et al. 1991, Nevo 2001

* My thoughts:
    * It is an interesting conclusion that using a consumer-utility-based ranking can also lead to a higher revenue. This implies that the search engine revenue is more or less in line with consumers' preferences. Note that this does not mean to let consumers customize with various options individually, but to use a central formular.
    * Critics: The model presented in this paper is a bit too complicated. Even it is possible to verify each model they use by showing that they all lead to small error, it is still possible that the overall model suffers from a large error margin.
    * This paper is a typical "business analytics" paper. Seems these papers are popular online lately.

