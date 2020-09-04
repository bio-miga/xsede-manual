# Database Indexing

Index a collection of genomes to use as a custom MiGA database to query an unknown genome against this database or search the genomes of the database against each other by calculating the all-vs-all AAI and ANI matrixes.

{% hint style="info" %}
Use this application to fully process all the genomes in a collection and build a searchable database
{% endhint %}

## Input

A collection of genomes \(assemblies\), typically 10 or more.

## Parameters

* **Project type:** Select the type of project depending on how closely related the genomes in your collection are. For genome collections from different taxa \(_e.g._, collections of Metagenome-Assembled Genomes\), select **Genomes**. For collections of closely related genomes \(_i.e._, all from the same species or closely related species\), select **Clade**.
* **Index method:** Select the search engines for the all-vs-all distance estimation. We strongly recommend using the default, **Fast**, which uses Diamond-based AAI and FastANI. If you would like your results to be directly comparable to BLAST-based AAI and ANI, you should select **Sensitive**.

{% page-ref page="../allocation.md" %}

