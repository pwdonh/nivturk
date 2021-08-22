---
layout: default
title: jsPsych Integration
nav_order: 4
parent: Detailed documentation
has_children: false
---

# jsPsych Integration

This page details how to integrate a preexisting jsPsych experiment with NivTurk.

It assumes that you already have working a jsPsych experiment (i.e. an HTML file with the complete experiment timeline and all associated plugins).

## Required configurations

Integrating a preexisting jsPsych experiment with NivTurk should (hopefully) be easy, assuming you follow the steps below:

### 1) Download NivTurk

To download NivTurk, please see the [Downloads](/nivturk/docs/download) page for instructions.

### 2) Organize files

Copy all files associated with your experiment into the appropriate folders in NivTurk. For example, all custom jsPsych plugins and CSS stylesheets can be stored in `/app/static/js` and `/app/static/css`, respectively.

Note: by default, NivTurk ships with the latest version of jsPsych (found in `/app/static/lib`). As such, you can move over any local copies of native jsPsych plugins into NivTurk but it is not necessary since you can source NivTurk's copy instead.

### 3) Update 'experiment.html'



## Optional configurations
