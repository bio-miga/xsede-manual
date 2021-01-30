---
description: How to select the resources to use in MiGA @ XSEDE
---

# Allocation

Once you have selected the appropriate application, it's a good idea to make sure the allocation settings are optimal for your task. We provide default settings that work well in most cases for a given application, but it's always better to double-check.

## Select a Queue and Node Count

There is no need to ever change the queue, you can simply use **compute**.

For the node count, the maximum number of cores you can use per node is 24. Therefore, once you decide the total core count \(see below\), come back here to determine the number of nodes. As a general rule, you should set the largest node count that doesn't excede the total core count or the maximum available nodes \(72\). For example, if you need 60 cores, you should set the node count to 60. But if you need 140 nodes, you should set the node count to 72.

{% hint style="info" %}
Use the **smaller value** between the **total core count** \(below\) and **72**
{% endhint %}

## Total core count

The maximum core count is 1,728. The maximum number of cores MiGA will use is the number of genomes. If you have fewer than 1,728 genomes, set this value to the number of genomes you have.

{% hint style="info" %}
Use the **smaller value** between the **number of genomes** and **1,728**
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

