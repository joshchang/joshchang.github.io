---
title: "The biggest hurdle we had to overcome in formulating a calcium hypothesis for post-CSD vasoconstriction"
categories:
  - Blog
  - Research
tags:
  - research
  - CSD
  - calcium
  - ODE
link: https://www.biorxiv.org/content/10.1101/732362v1
---

About a decade ago now, I entered the field of biology by working in a neuroscience wet lab, studying this phenomenon known as cortical spreading depolarization (depression), or CSD. CSD is a physical wave of ionic movement and activity in cortical brain tissue that occurs in all sorts of pathological states. The lab was studying specifically how vasculature and blood delivery impact the propagation of the wave. A particular phenomenon we focused on, and characterized, was an hour long disturbance in blood supply along with derangements in neurovascular coupling (the matching of blood supply to neuronal activity). Most of the literature on CSD focuses on the minute-long timescale over which the wave is present in terms of intracellular ionic concentrations.

I had always been interested in the mechanism for this hour-long state. In the interim years, I studied the calcium-phosphate regulation machinery in the body, using mathematical modeling. I saw that there was potentially a link between calcium phosphate regulation and the long-term disturbance. My idea was that calcium and phosphate which clustered within mitochondria of smooth muscle cells during CSD can leak out slowly and cause vasoconstriction. The key point here is that the presence of clusters means that the free concentration of calcium  within mitochondria is elevated but not too-highly elevated. Because exchange rates are dependent on free rather than total concentrations, the leakage out of mitochondria is slow.

Perhaps the coolest implication of these mechanisms is potential production of ATP, using aerobic machinery, in the absense of oxygen-dependent substrates. Dissolution of calcium phosphate absorbs protons, increasing the pH within mitochondria. Aerobic ATP production is ultimately driven by H+ gradients across the mitochondrial inner membrane - typically, maintenance of the gradient is performed by pumping protons out of the matrix using chemical potential energy from NADH and FADH2. Removal of protons through this process is another avenue for maintaining the gradient. I looked extensively into the literature and did find anybody characterizing this potential phenomenon.

Over the last couple years a couple collaborators and I have attempted to distill the overall mechanistic picture into a mathematical model in order to study the timescale of the phenomenon and whether it can explain what we see in experiments. We eventually got this paper submitted - it is under review by PLOS Computation Biology currently. I thought it would be useful to comment on some of the difficulties we had when formulating the model.

<!--more-->

In science, we "stand on the shoulders of giants." What this means in practice is that we are highly dependent on the generalizability of prior results in the literature. I think this is especially true when doing quantitative modeling. The biggest issue here is that when you delve into the literature, you often find that models rely at some point on parameter fits that are highly over-parameterized. Worse, sometimes units within reported models are not consistent (Ahem models containing the NCX - though one of my own prior papers also suffers from this issue).

In our model, we required cellular calcium dynamics, a well-studied subject. However, the bulk of the existing work in the literature suffers from the aforementioned issues, regardless of whether they fit experimental data. Additionally, we required each of the model components to be valid in perturbed states of physiology. For instance, we found that many models of the SERCA pump lead to blow-up in ER calcium concentration within the context of our model, because these models are not mindful of free calcium concentration within the ER, not to mention solubility issues within the ER. We did eventually find a couple suitable SERCA models, though they yielded poor behavior. Delving into the manuscripts where they fit these models, we found that the parameter fits were highly over-parameterized.

Our solution to our issues was to modify some of the parameters to give reasonable behavior (fluxes going in the right direction at about the right magnitude), and to report model outputs over a wide parameter sweep. At a personal level, I find myself somewhat unsatisfied by all of this - the overall project only partially scratched an itch that I had. In order to fully scratch the itch, I would need someone to do detailed mechanism-specific measurements of each of the pumps and channels involved, with careful fitting where uncertainties and parametric dependencies are retained and characterized. Short of this, raw data would have been useful. As a follow-up paper, I hope we can provide better guidance to people when they fit kinetic models to data, so stay tuned...
