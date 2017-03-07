---
layout: post
title: "Preprint Review: 'Cohesion: A method for quantifying the connectivity of microbial communities'"
author: "PD Schloss"
date: "March 7, 2017"
comments: false
---

The [preprint](http://biorxiv.org/content/early/2017/02/28/112391) from Herren and McMahon describes a new metric - cohesion - to describe the overall connectedness within a community using temporal data. I was excited to see this preprint because I am familiar with McMahon's long history of developing rich time series data for microbial communities in Wisconsin lakes. I also have a lot of my own time series data from humans and mice where we struggle to incorporate time into the analysis to understand the interactions between bacterial populations.

A significant struggle in analyzing time course community data is the ability to synthesize observations for large numbers of taxa over time. Many of the existing methods people use attempt to adapt methods from cross sectional studies. For example, a study may sample a large number of lakes, people, soils, etc and characterize their microbial communities. They'll then calculate correlations across those samples based on the relative abundance of the populations. Alternatively, they'll used presence/absence data to generate co-occurrence matrices. The problem with these studies is that the next step is to often infer something about the interactions between the populations - even if the populations would never possibly co-occur. Herren and McMahon's efforts to study the connectedness of individual populations and their cohesion is very welcome because it has the potential to get us closer to describing the actual interactions between populations.

To briefly summarize the approach, the method starts by calculating the Pearson correlation between all pairs of populations across time and then discounts the correlation that would be expected if all interactions were random. This is important because of the compositional nature of the data and the effects of different population sizes. Next, the method calculates the average positive and negative corrected correlation for each population. These become the positive and negative connectedness values for each population. Finally the positive and negative cohesion values for each community is calculated by determining the sum of the product of the connectedness value and the relative abundance for that population.

The following are general critiques and questions, which I appreciate may be beyond the scope of the current manuscript (note, I am not a reviewer for the manuscript at a journal):

1. To develop the cohesion metric for a community, the authors sum over all of the populations in the community. This raised three questions for me. First, independent of the relative abundances in each sample, is the *number* of positive and negative connections for each population relevant? It might be worthwhile exploring which populations have more positive/negative connections than others. What does that distribution look like? Second, does the connectedness metric value itself have any value? What are the populations that are highly connected with other populations. Finally, the method generates a cohesion value for each time point. If I think of Lake Mendota as a community that was sampled over time, it would be interesting to know whether it has been more cohesive than Lake Monona over the 19 years of sampling. Thinking of my own work, I would be interested in knowing whether mice that are more susceptible to C. difficile colonization are less cohesive than those that are resistant. Again, this would require a composite score, not individual scores for each time point.

2. Continuing on my self-serving thread, I wonder how sensitive the method is to the time interval between samples and the number of samples. In my experiments I may have 20 daily samples from a mouse - is this sufficient? What if we miss a day - how will having a jump between points affect the metrics? As the authors state, the Lake Mendota dataset has 293 samples collected over 19 years (e.g. 1.3 samples/month). This is a very unique dataset that is unlikely to be repeated elsewhere. What if we were to get more frequent samples? What if they were more spaced out? What if we only had a year's worth of data? It would be interesting to see the authors describe how their cohesion values change when they subset the dataset to simulate more realistic sampling schemes.

3. A significant challenge in developing these types of metrics is not knowing what the true value of the metric is in nature. I appreciate Herren and McMahon's effort to validate the metrics by comparing their results to count data and to explaining the variation in Bray-Curtis distances. The manuscript reads almost like they want their method to recapitulate what is seen with those distances. But we already have Bray-Curtis distances, if that's the goal, then why do we need the cohesion metric? It would be interesting to see the authors simulate data from communities with varying levels of cohesion and abundance to see that the method gets back the expected cohesion value. Perhaps it would be possible to generate an ODE-based model to generate the data instead of variance/covariance data. There is one simulation described at the end of the Results (L300); however, it is unclear whether the lack of a meaningful R-squared value was the expected result or not.

4. Throughout the manuscript, the authors make use of parametric statistics such as Pearson's correlation coefficients and the arithmetic mean. Given that relative abundance data are generally not normally distributed and are likely zero-inflated, I wonder why the authors made these choices. I would encourage the authors to instead use Spearman correlation coefficients and median values. Related to this point, a concern with using these correlation coefficients is the problem of double zeros where two populations may be absent from the same communities. These will appear to be more correlated with each other than they really are, which is why we don't use these metrics for community comparison - we use things like Bray-Curtis. I wonder whether subtracting the null model counteracts the problem of double zeroes.

5. The authors translate their count data into relative abundance data before calculating their correlation and Bray-Curtis values. I wonder if the authors subsampled or rarefied their data to a common number of individuals. Both of these metrics are sensitive to uneven sampling. Even if the counts are converted to relative abundances, this would not remove the effects. For example, if one sample has 1000 individuals and another has 100, the limit of detection on the first would be 10-fold higher than the second. There may be populations that represent 0.5% of both communities that would not be seen in the second. If they haven't already, I would encourage the authors to subsample their dataset to a common number of individuals.

6. The "Description of datasets" section of the Methods describes the various datasets in general terms, but what is the nature of the data? How were the phytoplankton counted? How many individuals were sampled from each sample?

7. It would be great to have the code that was used made publicly available on GitHub

8. The authors present the material in a format that I have not previously seen in the microbial ecology literature (i.e. ISMEJ where this appears to be destined for review). The authors flip back and forth between presenting a different stage of the algorithm and validating that step. I think this is a bit more aligned with how one would present the material in a talk than in a paper. I've seen similar methods development described before where there might be a methods section on algorithm development and then the results section would test the assumptions and performance of the algorithm. I'm curious to see whether this structure persists through the editorial process.