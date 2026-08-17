---
title: "Aerial solar-panel segmentation on AWS"
excerpt: "Deep learning pipeline for solar panel segmentation from aerial imagery, deployed as an AWS Lambda service with SpendWatt.<br/>"
collection: portfolio
---

A deep learning pipeline for solar panel segmentation from aerial imagery, developed with SpendWatt (2022–present). Semantic segmentation models are trained on aerial tiles to detect and outline rooftop PV arrays, and used to estimate residential PV capacity at street, suburb, and network-wide scale.

The trained model is packaged as an AWS Lambda service so results can be produced on demand from new aerial captures without keeping a GPU server running. The pipeline supports the ARC Linkage electrification research program (AGL, AusNet, SpendWatt).
