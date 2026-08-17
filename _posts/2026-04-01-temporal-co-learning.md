---
title: "Temporal co-learning for residential electricity forecasting"
date: 2026-04-01
permalink: /posts/2026/04/temporal-co-learning/
tags:
  - forecasting
  - multi-task learning
  - electricity demand
  - deep learning
---

Residential electricity forecasting sits between two hard problems. Household-level load is noisy and non-stationary, while feeder-level load is smoother but loses the behavioural signal that drives the peaks. Models trained on one level of aggregation often generalise badly to another.

Our *Applied Energy* (2026) paper proposes **temporal co-learning**: a multi-task learning framework in which the same encoder is trained to forecast at several temporal scales and aggregation levels at the same time. The shared representation is forced to capture features that are useful across tasks, which acts as a strong regulariser on the noisy household-level task.

Empirically, co-learning improves accuracy on the hardest short-horizon household forecasts without sacrificing performance on smoother feeder-level ones. It also cuts down the number of models a utility has to maintain, because one encoder covers several downstream forecasting products.

**Reference.** Song H., ..., Kamoona A.M. et al. Electricity consumption forecasting for residential sector using temporal co-learning. *Applied Energy*, 395, 125856, 2026.
