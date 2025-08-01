---
layout: post
title:  "A Beginner's Guide to Neural Engineering Part 1: What Tools to Choose?"
date:   2025-07-02 20:05:26 -0500
categories: jekyll update
---
Starting an adventure in human neuroscience can be very exciting.
Let's be honest, doing neuroscience research sounds a little bit like being in 
a science-fiction movie. There is an increasing interest in neural engineering due to 
recent technological advances (8 core processors with 16Gb of RAM in the palm of
my hand for around $200, advances in Machine Learning models etc.).
But we can easily get lost in the amount of information out there... 
Where to start? How do I analyze the data? What programming language? What package? 
What is the science behind the methodology we are using?

In this serie I will try to give a bird's eye view of what neural engineering 
consists of, how to get started how to process and analyze the data and what 
kind of data.

But before I start I would like to emphasize on the most important 
thing in neuroscience (maybe in science in general?): No matter your experience in Engineering (signal processing, software engineering, 
electrical engineering, ML/AI...) treat the data with ==humility==.
There is a reason why we still rely on Neurologists, Neurophysiologists and
Neuroscientists visual expertise... Because neural data are far more complex 
than they look like and people can miss very important discoveries by assuming 
that neural data is like any other time-series that can be processed by one's
homemade algorithm that they developed for stock market analysis...

# Programming language
I wrote codes in Python, C, MATLAB, R, C++, Rust etc. But what I want to
present here are the 2 Programming languages I used the most for post-hoc data analysis in neuroscience: MATLAB and Python.

I mentionned "post-hoc" data analysis because "real-time" would be a topic for
another post (dedicated to Brain-Computer Interface).

## MATLAB
When I started working with EEG and intracerebral EEG data, my first
experience was with MATLAB. It is usually the go-to for many labs, 
primarily because of its ease of use in term of installation, running, 
data organization that can be "easier" for some people to understand. 
The learning curve is less steep than other programming language. 
One can just install matlab on the computer and start "coding". 
The primary purpose of MATLAB is data wrangling and visualization and it is 
very good at it, it is a very powerful tool for that.

But here’s the catch: MATLAB is not free. As an academic, I had access to it
through my institution, but the moment I left, it became clear that sticking
to MATLAB meant being locked into a costly ecosystem. Secondly, we want open
science, a good scientific study is the one where the results are reproducible 
with the code provided and the data used. 
How can we run a MATLAB script without MATLAB? (Yes ok there is Octave. But 
do you see the point? I hope you do ^^'.)

## Python
Python is open-source, extremely powerful and versatile. As of 2024 it became
the most popular programming language according to [GitHub](https://github.blog/news-insights/octoverse/octoverse-2024/). We see python absolutely
everywhere and it has grown into an essential tool in neuroscience, thanks to libraries like [MNE-Python](https://mne.tools/stable/index.html)
NumPy, SciPy, pandas, and scikit-learn. Python is more widely used in industry and for more application such as software engineering.

# The Three Main Toolboxes I Used

Over the years, I have worked with multiple toolboxes for EEG analysis, but three stand out as the most comprehensive and widely used:

## EEGLAB (MATLAB)

EEGLAB is probably the most cited EEG toolbox in the world. It is mature, well-documented, and packed with cutting-edge algorithms. It provides preprocessing pipelines for artifact removal and data cleaning and statistical tools tailored for EEG research.

Some notable features:

PREP pipeline: A great preprocessing pipeline that helps clean raw EEG data and automated bad sensors detection.

Artifact Subspace Reconstruction (ASR): One of the best tools for automatic artifact rejection and data cleaning.

However, the GUI feels a bit outdated. It’s not the most beginner-friendly toolbox to navigate.

## Brainstorm (MATLAB)

Now, if you’re looking for something more user-friendly, Brainstorm is a fantastic alternative. It has, in my opinion, the best GUI of all EEG/MEG toolboxes, making it far more approachable for beginners.

Why do I love Brainstorm?

Intuitive GUI: The visualization tools are excellent. You can inspect EEG signals, 3D brain activity, and even intracerebral electrode recordings with ease.

Great visualization capabilities: Beautiful cortical mapping and time-frequency analysis.

Integration with other toolboxes: Brainstorm serves as a hub that connects with SPM, FieldTrip, and other MATLAB-based toolboxes, making it an incredibly powerful platform.

Unlike EEGLAB, Brainstorm is structured more like a workflow platform than just a raw toolbox. This makes it ideal for users who want a more guided experience without diving too deep into code immediately.

## MNE-Python (Python)

MNE-Python is the Python toolbox for EEG/MEG research. It has an active developer community, strong industry backing, and a well-thought-out philosophy that makes working with EEG data a pleasure. This is, in my opinion, the best tool out there.

Some reasons why I love MNE:

Object-Oriented Data Handling: EEG data is treated as an object with attributes such as channels, sampling frequency, and metadata. This makes manipulation intuitive and scalable.

Integration with Scikit-Learn: Many functions are built with machine learning in mind. In fact, many MNE contributors are also scikit-learn contributors, ensuring seamless compatibility.

Visualization: The built-in plotting functions are excellent for inspecting data, power spectral densities, ICA components, and event-related potentials.

MEG and iEEG support: Unlike EEGLAB or Brainstorm, which are more EEG-centric, MNE is designed to handle any neural time-series data, including MEG and intracranial EEG.

If you are just starting in neuroscience research and want a free, open-source solution that integrates with modern machine learning workflows, MNE-Python is the way to go. The documentation is excellent, and there are many tutorials available.

## Special Mention
Special mention to Neurokit2 which is more a mutlimodal lighter package that has
some data simulation technique (ECG or respiration data simulation).

## Final Thoughts: What Should You Choose?

If you’re in a lab that heavily relies on MATLAB and you’re just starting out, EEGLAB or Brainstorm will likely be your go-to choices. If you want a smooth GUI experience, Brainstorm is fantastic. If you prefer more control and advanced processing, EEGLAB has some of the most powerful preprocessing tools available.

However, if you want something that will future-proof your skills, learn MNE-Python. Python is not just a programming language for neuroscience, it’s a gateway to data science, machine learning, and software engineering. It has a strong, active community, and the shift towards Python in neuroscience research is undeniable.

That being said, there is no one-size-fits-all. The best toolbox is the one that fits your needs and the needs of your lab. But if you’re a strong advocate for open science, then Python is the clear winner.

