+++
date = "2018-05-21T02:15:59+05:30"
title = "Accepted to GSoC 2018"
draft = false

+++

Hi everyone!

I am Sebastin Santy, a third year undergrad at [BITS Pilani K.K. Birla Goa Campus](http://www.bits-pilani.ac.in/Goa/). My proposal for GSoC 2018 has been accepted under [NumFOCUS](https://www.numfocus.org/) [[Julia Computing](https://juliacomputing.com/)]. I'll be working on adding support for more data repositories to [DataDepsGenerators.jl](https://github.com/oxinabox/DataDepsGenerators.jl/). DataDepsGenerators.jl is a support package for [DataDeps.jl](https://github.com/oxinabox/DataDeps.jl/) which helps in creating Register Blocks for DataDeps.jl. A Register Block is a chunk of julia code which describes the data to be downloaded. This description includes Dataset Name, Author Name, Website, Citations, Links etc. which aid researchers in effectively concentrating on the logic than data collection. Example of a register block:

```julia
RegisterDataDep( "MNIST train" ,
"""
Dataset: THE MNIST DATABASE of handwritten digits, (training subset) Authors: Yann LeCun, Corinna Cortes, Christopher J.C. Burges Website:  http://yann.lecun.com/exdb/mnist/
      [LeCun et al., 1998a]
            Y. LeCun, L. Bottou, Y. Bengio, and P. Haffner.
            "Gradient-based learning applied to document recognition."
            Proceedings of the IEEE, 86(11):2278-2324, November 1998
The files are available for download at the offical website linked above. We can download these files for you if you wish, but that doesn't free you from the burden of using the data responsibly and respect copyright. The authors of MNIST aren't really explicit about any terms of use, so please read the website to make sure you want to download the dataset.
""" ,
[ " http://yann.lecun.com/exdb/mnist/train-images-idx3-ubyte.gz " , ) 
```

My mentors are [Lyndon White](http://white.ucc.asn.au/) and [Chris Rackauckas](http://chrisrackauckas.com/). I'll be posting updates about my work on this blog every weekend. Looking forward to a great summer ahead!