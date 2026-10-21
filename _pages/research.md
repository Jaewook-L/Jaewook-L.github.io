---
layout: single
title: "Research"
permalink: /research/
author_profile: true
---

My research combines physics-based electrochemical models with machine learning to build AI-driven frameworks for reliable battery diagnostics and prognostics under real-world operating conditions. I also use Bayesian optimization and self-driving labs to accelerate electrolyte design.

## Research Interests

**Hybrid Physics-informed and Data-driven Modeling**

{% assign research_figure = site.data.figures.research["hybrid-modeling"] %}
{% include content-figure.html figure=research_figure title="Hybrid Physics-informed and Data-driven Modeling" variant="research" %}

Conventional black-box models can produce physically inconsistent predictions and generalize poorly when experimental data are limited. I embed electrochemical principles into neural networks as physical constraints, which keeps predictions thermodynamically consistent and improves generalization from small datasets. These models capture intra-cycle voltage and current dynamics as well as inter-cycle degradation trends to track capacity fade and resistance growth.

{% include research-publications.html topic="hybrid-modeling" %}

---

**Real-time Lifetime Diagnosis and Prognosis**

{% assign research_figure = site.data.figures.research["lifetime-diagnosis"] %}
{% include content-figure.html figure=research_figure title="Real-time Lifetime Diagnosis and Prognosis" variant="research" %}

Safe operation of large-scale battery systems depends on health monitoring in the field, where costly laboratory tests are impractical. I develop lightweight algorithms that diagnose battery health in real time from operating data and field-accessible electrochemical indices such as direct current internal resistance. This includes quantifying surface degradation and identifying the dominant degradation modes under dynamic electric vehicle profiles.

{% include research-publications.html topic="lifetime-diagnosis" %}

---

**Bayesian Optimization and Self-Driving Lab for Accelerated Battery Design**

{% assign research_figure = site.data.figures.research["self-driving-lab"] %}
{% include content-figure.html figure=research_figure title="Bayesian Optimization and Self-Driving Lab for Accelerated Battery Design" variant="research" %}

The design space of electrolyte compositions and formation protocols is too large to explore by trial and error, which slows the discovery of high-performance battery materials. I search this space with Bayesian optimization and inverse design, coupling Gaussian process regression with automated experiments in a self-driving lab. With this closed-loop approach, I identify optimal multi-solvent formulations and explain how high-entropy effects improve rate capability and cycle life.

{% include research-publications.html topic="self-driving-lab" %}

---

**Transfer Learning for Next-generation Batteries**

{% assign research_figure = site.data.figures.research["transfer-learning"] %}
{% include content-figure.html figure=research_figure title="Transfer Learning for Next-generation Batteries" variant="research" %}

Next-generation batteries, such as silicon-anode lithium-ion and aqueous zinc-ion cells, lack the large cycling datasets available for conventional lithium-ion batteries. I use transfer learning to adapt models trained on these well-characterized systems to new chemistries and predict their degradation from limited data. This reduces the time and cost of material validation and is a step toward a diagnostic platform that works across electrode materials and electrolytes.

{% include research-publications.html topic="transfer-learning" %}
