---
permalink: /
title: "Welcome!"
header:
  overlay_image: "venice.jpg"
# excerpt: "About me"
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

About me
======
Welcome! I'm a climate scientist interested in how artificial intelligence (AI) can advance our understanding and predictions of polar climate processes. My work is multi-disciplinary; I have used to AI to improve remote sensing data sets over sea ice, as well as to build the first hybrid global sea ice model and the first global sea ice emulator (see [Projects](https://william-gregory.github.io/projects/)).

The AI techniques I have used throughout my various projects include:
- Hierarchical clustering
- Gaussian process models
- Convolutional neural networks (Fully CNN, U-Net)
- Graph neural networks

*****

## Latest work

<img src="http://William-gregory.github.io/images/FloeNet_dynamics.gif" alt="arXiV2" width="300" align="right"/>
My latest publication introduces FloeNet, a mass-conserving global sea ice model, based entirely on AI. FloeNet is an auto-regressive graph neural network which has been trained to emulate the GFDL numerical sea ice model, SIS2. With a 6-hour timestep, FloeNet can respond rapidly to atmospheric dynamics, as seen in the animation on the right; this shows the wind stress forcing overlain on FloeNet's sea ice concentration, where you can see how storms break up the sea ice and cause localised areas of low concentration. In our paper we show how FloeNet also shows accurate response to forcing on climate timescales. We evaluate 140-year rollouts where FloeNet is forced by atmosphere and ocean conditions from a pre-industrial control climate and a climate with increasing 1% per year atmospheric CO2 concentration. Under these climates, FloeNet shows remarkable skill, particularly in capturing inter-annual sea ice volume variability.

## Other info

I am currently a postdoctoral research associate at Princeton University. Here, I am hired through the [M$^2$LInES](https://m2lines.github.io) initiative, which is a Schmidt-Sciences-funded programme dedicated to the improvement of climate models using AI. Prior to this, I obtained my PhD in polar climate and machine learning from University College London. For more information on my research activities, you can check out my [Google Scholar](https://scholar.google.com/citations?user=zgcx9eQAAAAJ&hl=en&oi=sra).

I am also developing a series of educational Python notebooks which cover the fundamental concepts of various statistical and machine learning methodologies. The aim is to cover concepts related to linear algebra, as well as supervised/unsupervised learning techniques; starting from linear regression and working towards deep neural networks. These notebooks will be routinely uploaded to the [Code](code) page of this website.

