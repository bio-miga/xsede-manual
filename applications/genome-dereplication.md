# Genome Dereplication

Dereplicate a set of genomes using a threshold for ANI \(Average Nucleotide Identity\) or AAI \(Average Amino Acid Identity\).

{% hint style="info" %}
Use this application to identify representatives from a collection of \(redundant\) genomes
{% endhint %}

## Input

A collection of genomes \(assemblies\), typically 10 or more, where some are suspected to belong to the same genomic group.

## Parameters

* **Index method:** Select the search engines for the all-vs-all comparisons. We strongly recommend using the default, **Fast**, which uses Diamond-based AAI and FastANI. If you want your results to be directly comparable to BLAST-based AAI and ANI, you can select **Sensitive**.
* **Distance metric:** Select the type of distance metric to use. If you dereplicate your genomes at or below the species level, use Average Nucleotide Identity or **ANI**. If you want to dereplicate your genomes at or above the genus level, use Average Amino Acid Identity or **AAI**.
* **Metric threshold:** Minimum percentage value of AAI or ANI to group genomes together. For reference, species-level groups are typically formed with ANI ≥ 95%, whereas genus-level groups are typically formed with AAI ≥ 60%. You can increase this value to select smaller, more redundant groups; or increase it to generate larger groups.
* **Representative Criterion:** Criterion to pick cluster representatives. Once MiGA identify non-redundant groups of genomes, it will also propose a single genome from each group to serve as the representative. If your genomes vary widely in quality, it's a good idea to pick **Highest genome quality**. However, if all genomes in the collection are of comparable quality \(_e.g._, all are complete genomes\), you can ask MiGA to select instead the genome closest to the center of the cluster, **Cluster medoids**.

{% page-ref page="../allocation.md" %}

