---
title: "DataDepsGenerators.jl: Access to over a Million datasets in Julia"
date: 2018-06-11T01:18:33+05:30
draft: false
---

## Introduction
I am Sebastin, a Google Summer of Code student working on DataDepsGenerators.jl a support package for DataDeps.jl. DataDeps.jl is a tool for reproducible data science. It means anyone trying to run your code later, in a different environment isn’t faffing around trying to work out where to download the data from and how to connect it to your scripts. DataDepsGenerators.jl helps DataDeps.jl by creating the register blocks which are needed as input to it. In short DataDepsGenerators.jl is responsible to bring access to millions of dataset at your fingertips. DataDeps.jl is responsible to use this information for downloading and integrating the datasets with the julia code. Together they help in `Repeatable Data Setup for Repeatable Science`.

## Description

The following list of APIs are extensively covered. It gives a description of the coverage and usage of the datasets and how important they are. If you wish to see only the functionality, click here.

* GitHub [`GitHub()`]: GitHub a VCS is alternatively used for hosting datasets by some organisations like fivethirtyeight and BuzzFeed. GitHub as a common constructor provides access to millions such datasets.

* UCI ML [`UCI()`]: UC Irvine Machine Learning Repository is a collection of databases, domain theories, and data generators that are used by the machine learning community for the empirical analysis of machine learning algorithms. It is widely regarded as a standard set of datasets and provides `437` datasets.


* Data One API: Dataone API is served in two versions (1 & 2) which are almost similar except some structural changes. This package provides support for both the versions. Overall, it provides a coverage for `~800k` datasets.
    * Version 1: [`DataOneV1()`] : This API covers the version 1 of DataOne API in general. At present, only DataDryad uses this API, hence the functions are largely based on this. Dryad is an international repository of data underlying peer-reviewed scientific and medical literature. It covers `~200k` datasets.

    * Version 2
        * TERN [`TERN()`]: Terrestrial Ecosystem Research Network (TERN) is Australia’s land ecosystem observatory. TERN observes and measures the cause and effect of ecosystem change-from site to continental scale-and delivers data streams that enable environmental research and management. It covers `~11k` datasets.

        * KNB:
            This is covered by `KnowledgeNetworkforBiocomplexity()` and `ArcticDataCenter()`. Arctic Data Center operates as the primary repository supporting the NSF Arctic community for data preservation and access.  Knowledge Network for Biocomplexity (KNB) is a national network intended to facilitate ecological and environmental research on biocomplexity. Together they cover `~10k` datasets.

* CKAN API [`CKAN()`]: The Comprehensive Knowledge Archive Network (CKAN) is a web-based open source management system for the storage and distribution of open data especially government released data. This helped in covering sites like data.gov, data.gov.au, data.gov.uk etc. Having a uniform API structure helped in having a single constructor for the whole CKAN API. Collectively this covers around `~300k` datasets.

## An end-to-end example

Lets try to work with the Gold Prices dataset which is available with the Demo Site of CKAN using `CKAN()`.
    
* Generating the Register Block for use by DataDeps:
    
    ```julia
    using DataDepsGenerators
    register_block = generate(CKAN(), "https://demo.ckan.org/dataset/gold-prices", "Gold Prices");
    ```

* Loading this data using DataDeps:

    ```julia
    using DataDeps
    eval(parse(register_block))
    data = datadep"Gold Prices/data.csv"
    ```

* Making it into a dataframe for further analysis:

    ```julia
    using DataFrames, FileIO, CSVFiles
    df = DataFrame(load(data; escapechar='"'));
    ```

* Making a simple plot (date vs price):

    ```julia
    using Plots
    plot(df[:date], df[:price], label="Gold Prices", legend=:topleft)
    ```

Following these steps produces this nice plot:


![Image](/static/GoldPrices.png)

# Conclusion

Work till now has been exciting. We have been able to provide access to over a million datasets and >50TB of data using DataDepsGenerators.jl. Future endeavours will bring support for many other data repositories (like CKAN, OAI-PMH, DataCite DOIs, Dataverse) eventually placing almost all of the open research data of the world at your fingertips.
