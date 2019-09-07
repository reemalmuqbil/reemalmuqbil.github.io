---
layout: post
title: MTA Turnstile Analysis
---

### Introduction

A client has approached us from WomenTechWomenYes organization asking for our help in data analytics to support some of their work strategies. Since they are having a gala at the beginning of summer, they wish to optimize the effectiveness of their street team work and get as much signatures from people at subway stations in New York city to attend the gala and cntribute to their cause.

### About MTA Turnstile Dataset
This is what the original dataset looks like, and you can find an exact description for each field [here](http://web.mta.info/developers/resources/nyct/turnstile/ts_Field_Description.txt) 

![original]({{ site.url }}/images/original-ds.png)

### Hypothesis 
The street teams shall be distributed on stations which are applicable to the following conditions:
* Stations with highest traffic record across NYC in May 2019.
* Stations located near to tech companies. 

### Methodology
#### 1-Data acquisition: 
We acquired Four datasets representing each week of May 2019 from [MTA Turnstile data](http://web.mta.info/developers/turnstile.html)
