PeaksAndValleys
===

[![Build Status](https://travis-ci.org/jbn/PeaksAndValleys.jl.svg?branch=master)](https://travis-ci.org/jbn/PeaksAndValleys.jl)
[![PeaksAndValleys](http://pkg.julialang.org/badges/PeaksAndValleys_0.3.svg)](http://pkg.julialang.org/?pkg=PeaksAndValleys&ver=release)
[![PeaksAndValleys](http://pkg.julialang.org/badges/PeaksAndValleys_0.4.svg)](http://pkg.julialang.org/?pkg=PeaksAndValleys&ver=nightly)
[![Coverage Status](https://coveralls.io/repos/jbn/PeaksAndValleys/badge.svg?branch=master&service=github)](https://coveralls.io/github/jbn/PeaksAndValleys?branch=master)
[![Build status](https://ci.appveyor.com/api/projects/status/097d6yxplrk8etp7?svg=true)](https://ci.appveyor.com/project/jbn/PeaksAndValleys-jl)


**This package imputes pivot points (i.e. peaks and valleys) from a sequence.**

Imputation is useful for up-trend and down-trend segmentation. However, a word 
of caution -- this is a very naive approach to regime switching 
(see: [this notebook for a bayesian approach](http://nbviewer.ipython.org/github/CamDavidsonPilon/Probabilistic-Programming-and-Bayesian-Methods-for-Hackers/blob/master/Chapter2_MorePyMC/Chapter2.ipynb)). 
Nevertheless, people tend to recognize peaks and valleys readily. So, it is 
useful for understanding human behavior given some time-series observations. 

###### Porting Notes

I really like Julia's attempts to maximize interoperability, rather than engage 
in language wars. Why reinvent the wheel, right? However, for this library, I 
chose to 
[port my existing Python package](https://github.com/jbn/ZigZag/) 
rather than reuse it.

The code for peak-valley segmentation is naturally loop-based. It resists 
vectorization, at least if you want readable code. (I'd love for someone 
to show me a good refutation!) For any heavy-usage, the Python version 
required numba. Whereas, the Julia version takes advantage of Julia's inherent 
strengths. 

Still, I must admit -- the translation was remarkably simple. It was almost 
thought-free.