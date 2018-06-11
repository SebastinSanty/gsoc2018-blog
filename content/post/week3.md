---
title: "Week 3: Implement DataOneV2 Abstraction"
date: 2018-06-03T01:18:33+05:30
draft: false
---

Hi everyone!

The third week has come to an end. It was a roller coaster week with failing tests and attempts to fix them. Anyways, one of the major work in the project, that is integrating DataOneV2 abstraction was completed. This is the summary of what I have done over the previous week:

## Work
[PR #21](https://github.com/oxinabox/DataDepsGenerators.jl/pull/21): Implemented 2 APIs, TERN(Terrestrial Ecosystem Research Network, Australia) (which features `TERN()`) and KNB(Knowledge Network for Biocomplexity) (which features `ArcticDataCenter()` and `KnowledgeNetworkforBiocomplexity()`) as a part of DataOneV2 API. This gave us a proper knowledge of how to go about the abstractions. This PR has helped in providing a basic structure which will be substantial for subsequent API implementation. We also started segregating the related files into a folder in order avoid confusion.

## Conclusion

We are a little behind according to the set project schedule in which we were planning to cover CKAN APIs also this week. This was due to multiple test failures and attempts at fixing them. Anyways, I feel multiple iterations have made the logic and abstractions strong which will help us in future. Also, it was noticed in between that DataDeps.jl has changed the structure of the input(Register Block) it needs, which needs to be accounted for (as a PR) this week. I also wrote a talk proposal for ODSC India Conference regarding this project, let’s see if it gets accepted.