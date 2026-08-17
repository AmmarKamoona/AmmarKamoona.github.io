---
title: "Point patterns, energy, and defect detection: an RFS view of anomalies"
date: 2024-06-01
permalink: /posts/2024/06/rfs-defect-anomaly/
tags:
  - anomaly detection
  - random finite sets
  - computer vision
  - manufacturing
---

Defect detection on manufactured parts is a classic anomaly detection problem: most items are normal, defects are rare, and the visual signature of a defect varies from batch to batch. A common practical trick is to extract a set of local features from an image and score how "unusual" the set looks compared with clean examples.

The catch is that the *set* itself is the object of interest — not each feature independently. Standard classifiers assume a fixed feature vector, so they either flatten the set (losing spatial structure) or reduce it to a summary statistic (losing information).

In our *EAAI* (2024) paper we take a different route and treat the extracted features as a **point pattern**: a random finite set whose cardinality and locations both carry information. Under a random finite set (RFS) model, the "energy" of a point pattern gives a principled way to score how far the pattern is from the training distribution. Higher energy means the point pattern is unlikely under the model, which is exactly the signal we want for anomaly detection.

The framework is attractive because it plugs into any deep feature extractor: the network provides the points, and the RFS energy provides the anomaly score. We show on standard defect benchmarks that the point-pattern view is competitive with, and often better than, methods that treat the same features as a bag of vectors.

**Reference.** Kamoona A.M., Bab-Hadiashar A., Hoseinnezhad R. Anomaly detection of defect using energy of point pattern features within random finite set framework. *Engineering Applications of Artificial Intelligence*, 132, 107857, 2024.
