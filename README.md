# Codeforces Problem Recommender

## TL;DR

`cf-recommender` gives you CF problems to practice taking the rating and solved problems into account.

Try it yourself: [asmaksimov2007.github.io/cf-recommender]()


## Important notice

This is a fork of the initial website. Adaptivity and overall structure have been improved. The theme is now dark by default, with lots of possible ways to change the look by editing the CSS. The codestyle and logic have been massively reworked as well (but there is still a huge room for improvement).

The idea and the original implementation have both been created by `Rishabh Srivastava, V. Khagesh Kumar, Pratham Arora, Param Kothari & Rohit Kumar`. You can find all necessary information in the original [GitHub repository](https://github.com/RishabhS66/Codeforces-Problem-Recommender).

## Overview

The tool fetches the user contest history, public profile data and submissions. The recommended problems' ratings are determined using the formulas below. The problems themselves then get picked out randomly from a problem archive if they satisfy the rating constraints (5 problems for each of 3 difficulty levels are displayed).

## Logic for problem recommendation

After some mathematical analysis and curve fitting, the authors derived the following equations to determine the acceptable range of ratings for the problems recommended in each category.

$$
-21.2 + 25.5e^{-\frac{20 * \text{user rating}}{1000}} \le \text{rating of an \textbf{easy} problem} \le -32.1 + 37.2e^{-\frac{10 * \text{user rating}}{1000}}
$$

$$
-38.8 + 44.8e^{-\frac{8 * \text{user rating}}{1000}} \le \text{rating of a \textbf{medium} problem} \le -53.2 + 59.9e^{-\frac{5 * \text{user rating}}{1000}}
$$

$$
-32.0 + 39.9e^{-\frac{8 * \text{user rating}}{1000}} \le \text{rating of a \textbf{hard} problem} \le -30.8 + 39.6e^{-\frac{6 * \text{user rating}}{1000}}
$$

