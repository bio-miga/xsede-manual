---
description: How to select the resources to use in MiGA @ XSEDE
---

# Allocation

Once you have selected the appropriate application, it's a good idea to make sure the allocation settings are optimal for your task. We provide default settings that work well in most cases for a given application, but it's always better to double-check.

## Total core count

The first step is to determine the number of cores you will need. The maximum core count is 4,096. The maximum number of cores MiGA will use is the number of genomes. If you have fewer than 4,096 genomes, set this value to the number of genomes you have.

{% hint style="info" %}
Use the **smaller value** between the **number of genomes** and **4,096**
{% endhint %}

## Select a Queue

{% hint style="info" %}
For a total core count &lt; 128: use **shared** \(default\)  
****For a total core count ≥ 128: use **compute**
{% endhint %}

## Node Count

#### In the shared queue

{% hint style="info" %}
Use **1**
{% endhint %}

**In the compute queue**

You need to estimate the minimum number of nodes that can accomodate your job. For that, simply take the total core count above, divide it by 128 \(maximum cores por node\), and round it up. For example, if you have 300 cores: 300/128 = 2.34, so you should request 3 nodes.

{% hint style="info" %}
Divide the **total core count** by **128** and **round up**
{% endhint %}

## Wall Time Limit

This is the maximum number of minutes that the task will be running. If your task exceeds this number, it will be terminated without completing. However, if you pick a number too high, the task will stay a very long time in queue, so it's important to get this approximately right \(but slightly overestimating\).

{% hint style="info" %}
Estimate the limit based on the type of **application** used
{% endhint %}

### For Database Indexing and Genome Dereplication

The total time of these tasks grows quadratically with the number of genomes. A rule-of-thumb estimate using **Fast** indexing is:

$$
time = \frac{5n + n^2/10}{cores}
$$

Where _time_ is the total wall time \(in minutes\), _n_ is the number of genomes, and _cores_ is the total core count. We recommend you never set a total wall time below 60 minutes.

### For Genome Classification and Genome Typing

The total time of these tasks grows linearly with the number of genomes. A quick estimate is:

$$
time = \frac{10n}{cores}
$$

Where _time_ is the total wall time \(in minutes\), _n_ is the number of genomes, and _cores_ is the total core count. We recommend you never set a total wall time below 60 minutes.

