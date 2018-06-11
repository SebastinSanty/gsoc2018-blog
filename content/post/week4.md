---
title: "Week 4: Implement CKAN API and change RegBlock structure"
date: 2018-06-10T01:18:33+05:30
draft: false
---

Hi everyone!

The fourth week has come to an end. This week was smooth considering the previous experiences I had handling the issues.

## Work
[PR #26](https://github.com/oxinabox/DataDepsGenerators.jl/pull/26): Implemented CKAN API setup. CKAN is used by a lot of government data providing agencies like data.gov, data.gov.au. Hence, adding CKAN brings us atleast over 1 million datasets (800,000 from DataOne, 281,000 from Data.Gov, 28,000 from Data.Gov.au). CKAN was the most successful API we integrated till today, as the API structure was uniform across multiple data sources which is a boon as we didn't need a constructor for each and every dataset separately.

[PR #25](https://github.com/oxinabox/DataDepsGenerators.jl/pull/25): DataDeps.jl had changed the structure of its Register Blocks, which led to warnings being displayed for integration tests. Hence, there was a need to change the structure of generated register blocks which was done by this PR.

## Conclusion

We are back on the schedule which was decided on the proposal. The first phase is over and evaluations are starting next week. At present, I am writing a long block post about all the features that have been integrated as a part of GSoC work. I'll start working on the Phase2 work next week.