---
layout: post
title:  "A Beginner's Guide to Neural Engineering: What Tools to Choose? "
date:   2025-01-02 20:05:26 -0500
categories: jekyll update
---
# Introduction

Starting an adventure in human neuroscience can be very exciting.
Let's be honest, doing neuroscience research sounds a little bit like being in a science-fiction movie. A lot of neologisms are made from the suffix "Neuro"—neuro-this, neuro-that—some justified, some just blatant marketing.

There has been a resurgence of interest and activity around neuro-whatever businesses in the last few years. A good case in point is the current craze for so-called ‘brain training’ products (and a lot of BS, pardon my French). It’s a buzzword, though its hype has been somewhat overshadowed by AI/LLMs/Generative AI lately. But still, media go crazy every time "brain-computer interface" is mentioned. I’ve heard many excited students say they were going to cure Alzheimer's, Parkinson’s, or whatnot!

Cute.

But things become serious and scary when it comes to getting our hands dirty dealing with real-world neural data. And it can be daunting for those just getting in. Where to start? How do I analyze the data? What programming language? What package? Let’s talk about the modality I know best: Electroencephalography (EEG) and intracerebral EEG (sEEG).

# Matlab vs. Python: The Eternal Debate

When I started working with EEG data, my first experience was with Matlab. Matlab is the go-to for many labs, primarily because of its comprehensive built-in toolboxes and ease of use for signal processing.

But here’s the catch: Matlab is expensive. As an academic, I had access to it through my institution, but the moment I left, it became clear that sticking to Matlab meant being locked into a costly ecosystem. Plus, I strongly believe in open science, and proprietary software is fundamentally at odds with that philosophy.

Enter Python.

Python is open-source, free, and extremely powerful. Over the years, it has grown into an essential tool in neuroscience, thanks to libraries like NumPy, SciPy, pandas, and scikit-learn. But more importantly, it now has MNE-Python, a full-fledged library for EEG and MEG data analysis, which rivals the best Matlab toolboxes.

While Matlab still has its place in certain workflows, especially due to its precision in certain calculations, I gradually transitioned almost everything to Python. It wasn’t just about cost—it was about flexibility, community support, and the ability to integrate machine learning workflows seamlessly (try integrating scikit-learn into a Matlab script and tell me how much fun that is).

The Three Main Toolboxes I Used

Over the years, I have worked with multiple toolboxes for EEG analysis, but three stand out as the most comprehensive and widely used:

## EEGLAB (Matlab)

EEGLAB is probably the most cited EEG toolbox in the world. It is mature, well-documented, and packed with cutting-edge algorithms. It provides preprocessing pipelines, Independent Component Analysis (ICA) for artifact removal, time-frequency decomposition, and statistical tools tailored for EEG research.

Some notable features:

PREP pipeline: A great preprocessing pipeline that helps clean raw EEG data.

Artifact Subspace Reconstruction (ASR): One of the best tools for automatic artifact rejection, particularly useful for removing movement artifacts.

Support for ICA: EEGLAB is arguably the best toolbox when it comes to ICA-based preprocessing, something that remains a gold standard in EEG artifact removal.

However, the GUI feels a bit outdated. It’s not the most beginner-friendly toolbox to navigate, and while powerful, it requires a solid understanding of signal processing to get the most out of it.

## Brainstorm (Matlab)

Now, if you’re looking for something more user-friendly, Brainstorm is a fantastic alternative. It has, in my opinion, the best GUI of all EEG/MEG toolboxes, making it far more approachable for beginners.

Why do I love Brainstorm?

Intuitive GUI: The visualization tools are excellent. You can inspect EEG signals, 3D brain activity, and even intracerebral electrode recordings with ease.

Great visualization capabilities: Beautiful cortical mapping and time-frequency analysis.

Integration with other toolboxes: Brainstorm serves as a hub that connects with SPM, FieldTrip, and other Matlab-based toolboxes, making it an incredibly powerful platform.

Unlike EEGLAB, Brainstorm is structured more like a workflow platform than just a raw toolbox. This makes it ideal for users who want a more guided experience without diving too deep into code immediately.

## MNE-Python (Python)

MNE-Python is the Python toolbox for EEG/MEG research. It has an active developer community, strong industry backing, and a well-thought-out philosophy that makes working with EEG data a pleasure.

Some reasons why I love MNE:

Object-Oriented Data Handling: EEG data is treated as an object with attributes such as channels, sampling frequency, and metadata. This makes manipulation intuitive and scalable.

Integration with Scikit-Learn: Many functions are built with machine learning in mind. In fact, many MNE contributors are also scikit-learn contributors, ensuring seamless compatibility.

Visualization: The built-in plotting functions are excellent for inspecting data, power spectral densities, ICA components, and event-related potentials.

MEG and iEEG support: Unlike EEGLAB or Brainstorm, which are more EEG-centric, MNE is designed to handle any neural time-series data, including MEG and intracranial EEG.

If you are just starting in neuroscience research and want a free, open-source solution that integrates with modern machine learning workflows, MNE-Python is the way to go. The documentation is excellent, and there are many tutorials available.

## Final Thoughts: What Should You Choose?

If you’re in a lab that heavily relies on Matlab and you’re just starting out, EEGLAB or Brainstorm will likely be your go-to choices. If you want a smooth GUI experience, Brainstorm is fantastic. If you prefer more control and advanced processing, EEGLAB has some of the most powerful preprocessing tools available.

However, if you want something that will future-proof your skills, learn MNE-Python. Python is not just a programming language for neuroscience—it’s a gateway to data science, machine learning, and software engineering. It has a strong, active community, and the shift towards Python in neuroscience research is undeniable.

That being said, there is no one-size-fits-all. The best toolbox is the one that fits your needs and the needs of your lab. But if you’re a strong advocate for open science (like I am), then Python is the clear winner.

