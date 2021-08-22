---
layout: default
title: Using Prolific
nav_order: 6
parent: Detailed documentation
has_children: false
---

# Using Prolific

This page is a step-by-step guide to setting up an experiment on [Prolific](https://www.prolific.co/) using NivTurk.

It assumes that you already have working jsPsych code in your `/app/templates/experiment.html` file, have tested your code, and are able to serve your experiment via the web.

## Setting up a Prolific study

From the Prolific dashboard, either click 'New study', or duplicate a previous study from within the 'Completed' tab on the sidebar (click 'Action', then 'Duplicate').

<br>
#### Study details
- Add a brief description of your study, including an estimated completion time.
- If desired, under 'Show advanced', you can create an internal label to refer to this this study. This can be useful if you want to refer to it later in other studies (e.g., preventing those who completed this study from accessing a later study).
- Under 'Which devices should participants use?', make sure only 'Desktop' is selected.

<br>
#### URL and adding URL arguments
- Set the URL for your experiment to the desired URL in the format `http://<ip-address>:<port-number>/`, as discussed on the [Serving experiments page](../serving). Make sure you include the forward slash `/` at the end, and make sure that you do not include the angle brackets.
- NivTurk expects several arguments to be provided from Prolific in the study URL. To add these, for the question 'How do you want to record Prolific IDs?', select the option 'I'll use URL parameters'. They should get added to the URL, so that the 'What is the URL of your study?' box should look something like:

```
{% raw %}http://<ip-address>:<port-number>?PROLIFIC_PID={{%PROLIFIC_PID%}}&STUDY_ID={{%STUDY_ID%}}&SESSION_ID={{%SESSION_ID%}}{% endraw %}
```

<br>
#### Copying study link to NivTurk
- For the question 'How do you want to confirm participants have completed your study?', select 'I'll redirect them using a URL'.
- Prolific will then provide a default completion code (if you have duplicated the study, this code will be the same as in the study you duplicated from). The completion code is the 8-digit alphanumeric code in the link: `https://app.prolific.co/submissions/complete?cc=<code>`.
- Copy this code onto your clipboard and paste it into the `/app/app.ini` file in the NivTurk folder (line 15, replacing the default code `PROLIFIC_CODE_GOES_HERE`).
- Now that this is updated, you can launch your experiment via gunicorn as detailed [here](../serving/#serving-via-gunicorn-production).

<br>
#### Audience
- Set the prescreening requirements (if any) as desired.
    - For <ins>Niv lab</ins> experimenters: we always screen based on Current Country of Residence, since we do not have IRB approval to recruit in countries within the European Union. Countries we can recruit from include the USA, Canada, Australia, and New Zealand.
    - For <ins>Daw lab</ins> experimenters: we always screen based on Current Country of Residence, since we can recruit only participants from the USA.
- If you want to exclude participants who participated in previous studies, you can do so via Participation on Prolific > Previous Studies
- If you want to include participants based on their Prolific IDs, you can do so via Custom Screener > Custom Allowlist. This is helpful for recruiting back participants who took part in previous studies.

<br>
#### Launching study
Once you have specified the completion time, payment amount, and sample size, you can launch your experiment. If you need extra funds, you will be prompted to add them here.

The 'Preview' option gives you the chance to see the study advertisement as participants see it.
