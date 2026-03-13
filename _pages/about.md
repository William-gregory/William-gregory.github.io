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
Welcome! I'm a climate scientist interested in how artificial intelligence (AI) can advance our understanding and predictions of polar climate processes. My work is multi-disciplinary; I have used to AI to improve remote sensing data sets over sea ice, as well as to build the first hybrid global sea ice model (see [Projects](https://william-gregory.github.io/projects/)). My current focus is on sea ice emulation. In collaboration with the Allen Institute for AI, I am researching whether coupling a stand-alone sea ice emulator to the atmosphere-ocean emulator, SamudrACE ([Duncan, ..., Gregory et al., 2025](https://doi.org/10.48550/arXiv.2509.12490)), improves the representation of coupled climate processes in SamudrACE rollouts.

The AI techniques I have used throughout my various projects include:
- Hierarchical clustering
- Gaussian process models
- Convolutional neural networks (Fully CNN, U-Net)
- Graph neural networks

*****

## Latest work

<img src="http://William-gregory.github.io/images/FloeNet_dynamics.gif" alt="arXiV2" width="300" align="right"/>
<span style="font-size: 16px;">My latest publication introduces FloeNet, a mass-conserving global sea ice model, based entirely on AI. FloeNet is an auto-regressive graph neural network which has been trained to emulate the GFDL sea ice model, SIS2. With a 6-hour timestep, FloeNet can respond rapidly to atmospheric dynamics, as seen in the animation on the right, which shows the wind stress forcing overlain on FloeNet's sea ice concentration (can you spot the 2012 Great Arctic Cyclone!?)..</span><br>

## Other info

I am currently a postdoctoral research associate at Princeton University. Here, I am hired through the [M$^2$LInES](https://m2lines.github.io) initiative, which is a Schmidt-Sciences-funded programme dedicated to the improvement of climate models using AI. Prior to this, I obtained my PhD in polar climate and machine learning from University College London. For more information on my research activities, you can check out my [Google Scholar](https://scholar.google.com/citations?user=zgcx9eQAAAAJ&hl=en&oi=sra).

I am also developing a series of educational Python notebooks which cover the fundamental concepts of various statistical and machine learning methodologies. The aim is to cover concepts related to linear algebra, as well as supervised/unsupervised learning techniques; starting from linear regression and working towards deep neural networks. These notebooks will be routinely uploaded to the [Code](code) page of this website.

