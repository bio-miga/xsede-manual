---
description: What application can help me in MiGA @ XSEDE?
---

# Selecting an Application

Different applications in [**MiGA @ XSEDE**](https://xsede.microbial-genomes.org/) automate commonly used workflows in MiGA. Explore the different tabs to identify the workflow that works for you.

{% hint style="info" %}
**Important:** Whenever possible, it's always better to submit a single task with many genomes instead of one task per genome
{% endhint %}

{% tabs %}
{% tab title="Indexing" %}
## Database Indexing

Index a collection of genomes to use as a custom MiGA database to query an unknown genome against this database or search the genomes of the database against each other by calculating the all-vs-all AAI and ANI matrixes.

{% page-ref page="applications/database-indexing.md" %}
{% endtab %}

{% tab title="Classification" %}
## Genome Classification

Classify query genomes against the TypeMat MiGA genome database as a reference: All genomes from prokaryotic type material available in NCBI.

{% page-ref page="applications/genome-classification.md" %}
{% endtab %}

{% tab title="Typing " %}
## Genome Typing

Perform a fine sequence \(Average Nucleotide Identity or ANI\) and gene content diversity analysis for genome-based typing of query genomes within a well-characterized species.

{% page-ref page="applications/genome-typing.md" %}
{% endtab %}

{% tab title="Dereplication" %}
## Genome Dereplication

Dereplicate a set of genomes using a threshold for ANI \(Average Nucleotide Identity\) or AAI \(Average Amino Acid Identity\).

{% page-ref page="applications/genome-dereplication.md" %}
{% endtab %}
{% endtabs %}



