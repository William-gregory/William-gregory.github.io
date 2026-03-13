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
Welcome! I'm a climate scientist interested in how artificial intelligence (AI) can advance our understanding and predictions of polar climate processes. My work is multi-disciplinary; I have used to AI to improve remote sensing data sets over sea ice, as well as to build the first hybrid global sea ice model and the first emulator of a global sea ice model (see [Projects](https://william-gregory.github.io/projects/)).

*****

## Latest work

<img src="http://William-gregory.github.io/images/FloeNet_dynamics.gif" alt="arXiV2" width="300" align="right"/>
My latest publication introduces FloeNet, a mass-conserving global sea ice model, based entirely on AI. FloeNet is an auto-regressive graph neural network which has been trained to emulate the GFDL numerical sea ice model, SIS2. The animation on the right shows the wind stress forcing overlain on FloeNet's sea ice concentration. Notice how FloeNet responds rapidly to atmospheric dynamics, with storms breaking up the sea ice to produce areas of low ice concentration. In our paper, we evaluate 140-year rollouts under a pre-industrial control climate and a climate with increasing 1% per year atmospheric CO2 concentration. Under these conditions, we show how FloeNet generates accurate thermodynamic and dynamic responses to forcing. FloeNet is also over 3x faster than the original numerical model and requires significantly fewer resouces. A 140-year simulation with FloeNet takes 4.75 hours on 1 GPU, whereas SIS2 takes over 17 hours on 4671 CPUs.

## Other info

I am currently a postdoctoral research associate at Princeton University. Here, I am hired through the [M$^2$LInES](https://m2lines.github.io) initiative, which is a Schmidt-Sciences-funded programme dedicated to the improvement of climate models using AI. Prior to this, I obtained my PhD in polar climate and machine learning from University College London. For more information on my research activities, you can check out my [Google Scholar](https://scholar.google.com/citations?user=zgcx9eQAAAAJ&hl=en&oi=sra).

I am also developing a series of educational Python notebooks which cover the fundamental concepts of various statistical and machine learning methodologies. The aim is to cover concepts related to linear algebra, as well as supervised/unsupervised learning techniques; starting from linear regression and working towards deep neural networks. These notebooks will be routinely uploaded to the [Code](code) page of this website.

