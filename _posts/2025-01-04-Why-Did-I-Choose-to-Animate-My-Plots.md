---
title: "Why Did I Choose to Animate My Plots?"
date: 2025-01-04
layout: post
categories: [Data Visualization, Machine Learning]
tags: [animation, plots, EEG, fMRI]
---
# Introduction/Context
I am working on a project that aims to develop machine learning models to predict brain states from electroencephalography data. By brain-states, I refer to co-activation patterns obtained from fMRI recordings (BOLD signal) during specific cognitive tasks (e.g., video viewing, Steady State Visual Evoked Potentials (SSVEP), etc.).

fMRI offers good spatial resolution but poor temporal resolution. On the other hand, electroencephalography provides great temporal resolution but very poor spatial resolution, as it only captures the brain's electrical activity from the surface.

It would be amazing to obtain the same information from EEG as we do from fMRI. This is a very simplified way to put it.

The purpose of this post is to explain how and why I animated the data plots. Therefore, I will not delve deeply into details about data pre-processing, model training, feature selection, and the rationale behind these choices. These topics might be covered in another post.

# The Data
Despite my intention to keep this post simple, I still need to provide some context about the data.

## Subjects
We have a population of 22 subjects.

## Brain States
1. The brain states consist of 8 co-activation patterns (CAP) over time, forming a time series.
2. Each subject has 8 brain-states.

The brain-states were resampled to a 3.8 Hz sampling rate.

Each subject has 8 time-series.

## EEG Data
We have EEG dynamics over time for every frequency band from 1 Hz to 39 Hz, with 1 Hz increments. This dynamic is captured through 61 electrodes. Therefore, we have 61 * 39 = 2379 time-series per subject. The EEG data were resampled over time to match the brain-states time-series.

## Data Organization
Data were organized into [`numpy`](https://numpy.org/doc/stable/reference/arrays.ndarray.html) arrays:

- Brain-states: 3D array of shape (n_subjects, n_brain_states, n_time_points)
- EEG: 4D array of shape (n_subjects, n_electrodes, n_time_points, n_frequency_bands)




