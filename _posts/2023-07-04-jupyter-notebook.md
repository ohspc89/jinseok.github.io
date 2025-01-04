---
layout: post
title: a post with jupyter notebook
date: 2025-01-03 20:57:00-0700
description: jupyter notebooks, reading numbers
tags: OCR
categories: python-tricks
giscus_comments: false
related_posts: false
---

I am recently preparing a manuscript that describes the leg movement characteristics of infants who participated in the HBCD study.
One characteristic is the movement rate per hour awake. We obtained this measure from both legs, and I wanted to demonstrate that the measure was significantly correlated between legs. Thus I calculated a correlation coefficient of the two samples: [left leg movement rate] and [right leg movement rate].

To demonstrate that our finding is comparable to previous findings from small sample studies, I searched for [Smith et al. (2015)](https://doi.org/10.3390/s150819006), the very first paper on infant leg movement rates measured with wearable sensors.

Ah, but the authors did not _calculate_ the correlation coefficient. They reported raw values in Table 2:
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Selection_064.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Movement rates at the right-most columns of the table
</div>

This may also be the case for other researchers; they find data published in articles and want to do _something_ with the reported numbers. If diligent and meticulous, they will open Excel, type in numbers one by one, and then move to the next step.

In the era of ChatGPT, they can ask it to read the numbers from the publicly accessible pdf file and perform necessary statistical tests. Luckily, [Smith et al. (2015)] is published in [MDPI Sensors], an Open Access Journal.

I chose the third option - make it another reason to improve my Python skills and write a script that helps me read numbers in a screenshot I prepare.

I used [shutter](https://shutter-project.org) to screen capture the visual I see from my LG 29WN600-W 29-inch monitor.

{::nomarkdown}
{% assign jupyter_path = "assets/jupyter/Test_ocr.ipynb" | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/Test_ocr.ipynb %}{% endcapture %}
{% if notebook_exists == "true" %}
{% jupyter_notebook jupyter_path %}
{% else %}

<p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}
