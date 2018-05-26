---
title: "Week 2: Work on the REST API interface using DataOne"
date: 2018-05-27T01:18:33+05:30
draft: false
---

Hi everyone!

The second week has come to an end. This is the summary of what I have done over the previous week:

## Work
[PR #18](https://github.com/oxinabox/DataDepsGenerators.jl/pull/18): Provision to add checksum in Register Blocks. Till now checksums didn't have a separate block of space in the Register Block structure. A new function was created to handle the case of checksums along with the tests. Overall, this PR helped me a lot in learning Julia, thanks to the lengthy review it went through.

[PR #15](https://github.com/oxinabox/DataDepsGenerators.jl/pull/19): Implement DataDryadAPI. `DataDryad()` which was already added in the Pre-GSoC period scraped the Data Dryad website for Register Block generation. With this PR, `DataDryad()` was renamed to `DataDryadWeb()` and a new immutable `DataDryadAPI()` was added which did the same work but through the DataOne API. During this implementation it was decided to avoid premature (and potentially incorrect) abstraction. Hence, abstraction will be added iff we find another repository which uses DataOne API.

## Conclusion

The core of the project got started this week with the implementation of `DataDryadAPI()`. When working on the subsequent PR, I realised that DataOne has 2 different versions and on top of that, DataOne doesn't extensively cover it's member nodes' through it's API, which will be a hurdle in our way. Let's see how this week turns out to be.