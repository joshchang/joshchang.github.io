---
title: "Basketball, prediction, and data availability"
categories:
  - Blog
  - Research
tags:
  - research
  - statistics
  - bayesian
link: https://royalsocietypublishing.org/doi/full/10.1098/rsos.182174
---

Tl;dr: 
* Yes, hot hands exist
* People should stop uncritically using Bayes factors
* Look to sports if you want data to test out ideas

Oddly enough, for a government-funded mathematical biologist, it looks like I wrote a manuscript funded by the Social Security Administration on the hot hand effect in basketball. I thought I should explain a bit how this particular manuscript came to be.

# SSA and disability adjudication

In 2013, I first heard This American Life's episode [490 Trends With Benefits](https://www.thisamericanlife.org/490/trends-with-benefits), telling stories behind the disability crisis facing the United States. The episode always stuck with me and was a big factor in influencing me to join the NIH Clinical Center's [Epidemiology and Biostatistics group](https://clinicalcenter.nih.gov/rmd/eb/ebstaff.html), which is sponsored by the US Social Security Administration (SSA) and collaborates with the SSA on disability projects.

The particular project I was interested in involved using queueing theory to understand the case adjudication backlog. At the time, the backlog was two years. The government was interested in using analytical techniques to improve productivity and target resources in the aim of reducing the backlog.

# Modeling

As part of this project, I needed a method of modeling paths which cases take as they traverse through the system at SSA. Enter Markov Chains! However, standard memoryless Markov Chains were not suitable for this problem. There were some stereotyped patterns within case paths though with lots of variability. The simplest extension of memoryless Markov chains are higher-order Markov chains. In these Markov chains, the transition probability depends on the recent history of the trajectory, and not just the current state. I needed a general method for choosing the order.

# Publication

At the same time, I had been having success using the principle of evaluating Bayesian models based on their frequentist properties. What this entails is evaluating the out-of-sample predictive ability of well-regularized Bayesian model fits. For the Markov chain problem, there are certain metrics that one can compute for performing this evaluation. My original manuscript [arXiv:1702.06221](https://arxiv.org/abs/1702.06221) derived formulae for these metrics and evaluated the relative performance of the different metrics using simulated data.
**Notably, Bayes factors are very bad for this problem, if you want to make any mechanistic judgments downstream of your model selection procedure.**

Now it came time to publish the results. Editors were not interested in publishing me original manuscript since it didn't have data or a real-world problem. I didn't want to use the original social security application, because that information is sensitive. Being from the world of quantitative biology, I immediately started looking for biological applications (transitions between protein states for instance), but came up empty in searching for publically-available data.

# Hot hands

Fortunately, at that time, the NBA finals were going on. I realized that **sports data is public.** Additionally, there had been some debate in the media over the presence of the hot hand effect. As I was watching game two of the 2017 finals, I scrubbed LeBron James' free throw records from the season prior and lo and behold, I found statistical dependencies in his free throw shooting. He didn't exhibit hot hands per-se, but he clearly has a tendency to course-correct after missing a free throw. Over several seasons, he has hit a better percentage after a miss than otherwise.

Going forward in peer review, I eventually extended the analysis to other players, and to entire seasons. If you check out my paper, you will see that based on best-prediction, models for free throws with various types of dependencies between free throws do better than than models without dependencies. This varies by player but there are several general trends: Hot hands, cold hands, error correcting hands. As a variant of cold hands, many players shoot markedly worse on their first trip to the line. I think NBA coaches know this -- when a player gets injured and is unable to shoot his free throws, the opposing coach will often choose someone at the end of the injured player's bench to shoot free throws.

Additionally, from a mechanistic standpoint, it is no surprise that statistical dependencies between outcomes exist. Anybody who has ever played basketball would tell you that sometimes you are in the zone and sometimes you aren't feeling it. Shooting a basketball is a sequence of neuronal signals culminating in mechanistic actions. The underlying process is a result of a dynamical system dependent on the state of the player. It makes sense that hot hands exist.

Anyways, to summarize, no the SSA didn't fund a sports analytics study. The manuscript looks like a sports analytics study but it is actually a serious scholarly work on evaluating model choices.