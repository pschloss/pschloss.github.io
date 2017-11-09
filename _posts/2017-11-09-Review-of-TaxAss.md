---
layout: post
title: "Pre-print Review of TaxAss Manuscript"
author: "PD Schloss"
date: "November 9, 2017"
comments: false
---

The [preprint by Robin Rowher and colleagues ](https://www.biorxiv.org/content/early/2017/11/05/214288) seeks to develop a workflow that complements methods for classifying 16S rRNA gene sequences with greater precision than is found in the Wang naive Bayesian classifier [^1]. This is an issue that many people have raised with me. A lack of classification for a sequence can be blamed on inadequacies of the taxa represented in the database, lack of taxonomic data (e.g. at the species level) within the database, and the selection of the region within the 16S rRNA gene to classify. This paper seems primarily concerned with the first problem by supplementing ecosystem-specific sequences and touches on the second problem by adding finer taxonomic information for the ecosystem-specific sequences. I felt like the authors were a bit conflicted over what they wanted this manuscript to be. Is it a description/announcement of a new method, TaxAss? Is it a validation study? Is it a benchmarking study? Overall, it is a description of a new method that is being used by the authors and others. However, I feel like it needs some help to improve the description as there are points in the manuscript that are not clear. Furthermore, I felt that the validation and benchmarking could use some help to quantify the need for the method and to demonstrate that the method overcomes that problem.


General comments...
1. As described in Figure 1, sequences that fall below an empirically determined threshold when compared to an ecosystem-specific database are classified using a comprehensive database and those that are above the threshold are classified against the ecosystem-specific database. Perhaps it's because I'm familiar with people using blastn to classify sequences, as I read the manuscript, it was not clear whether the sequences in the two arms were then classified using the Wang method or blastn. Reading through the source code, it looks like blastn is only used to split the dataset and once split, the data are classified using the Wang method. Perhaps this could be clarified in the text.

2. It is not clear how the FreshTrain database was developed or how it is curated to add finer taxonomic names to the sequences. The authors have done this for the readers who are interested in fresh water bacteria, but what steps should someone interested in gut microbiota take to recreate the database to classify their data? More importantly, how did the authors decide on their taxonomic levels of lineage, clade, and tribe? Why not follow the phylogenetic approach used by the greengenes developers for defining family, genus, and species for environmental sequences?

3. I am also not clear why the authors did not want to pool FreshTrain with one of the comprehensive databases. A simple `cat` command would pool the two files producing a file that could then be used as a single reference. The downside of this would be that they would need to add the same level of taxonomic detail that is in the FreshTrain database to the greengenes database. Also, a downside of the greengenes database is that the core reference appears to be moth balled going forward while RDP and SILVA are still actively being developed.

4. One motivation that the authors state for the method is the issue of "forcing". I would call these "false positives", but I get their point. The authors raise this issue numerous times. Yet I was unable to find a citation that quantifies forcing and the authors do not appear to measure the amount of forcing in their data. Perhaps this is what they were getting at in Figure 3? If that is the case, then I am a bit troubled because they are accepting the FreshTrain data as the ground truth, when it has not been validated yet. I could also imagine that even with FreshTrain, there might be forcing if a taxonomic name is set for the full length sequence, but two variable region sequences are identical even though their parent sequences have different taxonomies. More importantly, the source code indicates that the authors are using any confidence score with out applying a filter. The suggested confidence score is 80%, not 0%. I don't think that the problem with classifications from the Wang method is forcing, rather, it's that the classifications don't go deep enough. Something may classify as a Bacillus with 20% confidence and so researchers should work their way up the taxonomy until the classification is above 80%, which might be Firmicutes. In offline conversations with the authors, they reassured me that they are applying an 80% threshold in separate scripts. It would probably be worth adding that they are using 80% as a threshold in the Methods seciton.

5. Related to this point, at L122 the authors state that "In a large database an OTU dissimilar to any reference sequences will not be classified repeatably as any one taxon, resulting in a low bootstrap confidence." This is correct, but is a bit misleading. I would suggest saying "...repeatedly as any one genus, resulting in a low bootstrap confidence and reclassification at a higher taxonomic level where there is sufficient bootstrap confidence". I am concerned that the results and the discussion of forcing are based on not using a confidence threshold rather than the default 80% threshold.

6. To measure forcing, I would like to see the authors run the greengenes and FreshTrain databases back through the classifier using a leave-one-out testing procedure and quantify how many times the incorrect classification is given, when using the 80% (or even the 0%) threshold. Again, I suspect the results would indicate that the problem isn't one of forcing, but of "holding back". To be clear, this isn't necessarily a problem with the Wang method, but the databases. Addressing this point is where I think the authors could really do the field a service. It would be a really helpful contribution to show the percentage of forcing (false positives) and holding back (false negatives?) in a leave-one-out scheme and on a real dataset when classifying with (1) each of the comprehensive databases, (2) using TaxAss with the comprehensive databases and FreshTrain, (3) merging the comprehensive databases with FreshTrain and running them through the Wang classifier.

7. I am not sure what the authors mean by "maintaining richness" as they use it in the manuscript. Could the problem they are trying to address be described better? Also, I would ask whether they know what the *true* richness is and if not, why they think that one value of richness is better than another. Perhaps this corresponds to what I might call "underclassifciation" or "false negatives".

L25 - why not include the RDP reference database in this list?

L49 - "Course" should be "Coarse"


---

<br>

[^1]: I have posted a copy of this review at [bioRxiv](https://www.biorxiv.org/content/early/2017/11/05/214288#comment-3607815202). Please post any comments there.
