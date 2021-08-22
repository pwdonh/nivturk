---
layout: default
title: Download
nav_order: 2
has_children: false
permalink: /docs/download
---

# Downloading NivTurk

NivTurk is hosted at and available for download from its [Github repository](https://github.com/nivlab/nivturk){:target="_blank"}. There are multiple versions of NivTurk available, each with its own branch and intended for a particular participant pool:

- [mturk](https://github.com/nivlab/nivturk/tree/mturk){:target="_blank"}: for collecting data from Amazon Mechanical Turk.
- [prolific](https://github.com/nivlab/nivturk/tree/prolific){:target="_blank"}: for collecting data from Prolific.
- [standalone](https://github.com/nivlab/nivturk/tree/standalone){:target="_blank"}: for collecting data from the Princeton undergraduate student recruiting system (SONA) or from the Center for Computational Cognitive Neuropsychiatry.

## How to download

### via Github

You can download NivTurk directly from Github at any of the links above. Once you are on the page corresponding to the desired branch (e.g. MTurk, Prolific), click on the green 'Code' button on the top-right of the page, and then select 'Download Zip'.

### via Git clone

If you are comfortable working with Git at the command line, you can also clone the repo with the following commands

```bash
git clone https://github.com/nivlab/nivturk.git
```

Please note, the Prolific branch will be downloaded by the default. So if you want to use the MTurk branch you will need to switch to it after you clone the repo:

```bash
cd nivturk
git checkout mturk
```

Alternately, you can download the branch of interest directly using the command:

```bash
git clone https://github.com/nivlab/nivturk.git --single-branch --branch <branch-name>
```
