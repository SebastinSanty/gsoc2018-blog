---
title: "Week 1: Making DataDepsGenerators.jl ready"
date: 2018-05-24T03:56:04+05:30
# thumbnail: "path/thumbnail.jpg"
draft: false
---

Hi everyone!

The first week has come to an end. Including the previous work, this is the summary of what I have done till now:

## Work
[PR #17](https://github.com/oxinabox/DataDepsGenerators.jl/pull/17): Added DataDeps-based Integration tests. These were needed in order to check whether the Register Blocks we are generating using DataDepsGenerators.jl are in the format DataDeps.jl wants it to be. These tests were crucial as it gives a verification that DataDeps.jl is able to understand the generated Register Block output from DataDepsGenerators.jl without which the whole point of Register Block generation is useless.

[PR #15](https://github.com/oxinabox/DataDepsGenerators.jl/pull/15): Github changed their front-end code structure owing to which existing `GitHub()` code in DataDepsGenerators.jl was not able to retrieve the commits. This pull request fixed it. It was a bit tricky as GitHub now uses front-end rendering techniques because of which what appears is not what the source code is.

[Others](#) Worked on getting the CI tests green: [PR #13](https://github.com/oxinabox/DataDepsGenerators.jl/pull/15), [PR #14](https://github.com/oxinabox/DataDepsGenerators.jl/pull/14), [PR #16](https://github.com/oxinabox/DataDepsGenerators.jl/pull/16)

## Conclusion

These PRs are helping us to get near to the meat of the project which is adding repository support to DataDepsGenerators.jl. The work has been a bit erratic as my exams had just got over the day GSoC began. Shifting from a 30&deg;C to a 45&deg;C (university to home) region made things more worse. Though I feel, we are on schedule with the timeline on my proposal.
