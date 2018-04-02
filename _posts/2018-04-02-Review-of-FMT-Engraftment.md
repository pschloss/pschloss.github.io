---
layout: post
title: "Pre-print Review of 'Microbial Engraftment and Efficacy of FMT for C. difficile Patients With and Without IBD'"
author: "PD Schloss"
date: "April 2, 2018"
comments: false
---

My research group reviewed the preprint by [Hirten and colleagues](https://www.biorxiv.org/content/early/2018/02/18/267492) as part of our journal club and prepared this collaborative review. None of us have been asked to provide a review of the manuscript for a journal and we do not know its status [^1].

This preprint aims to describe the outcomes of fecal microbiota transplant (FMT) as a treatment for recurrent Clostridium difficile infection (CDI) in patients with and without IBD. The authors have a specific focus on whether IBD patients receiving FMTs are more or less likely to respond to, or have complications arising from, the procedure as a treatment for recurrent CDI. Overall, we think the longitudinal clinical component of the study was particularly well-suited to address the questions laid forth by the investigators, however, the subsequent analysis and grammatical errors within the paper made it difficult to both follow the narrative and reach the same conclusions. As an example, while engraftment of microbial communities following FMT was stated as one of the secondary outcomes the authors were interested in, the data presented aren't sufficient for making any conclusions regarding colonization of donor-derived microbes. Likewise, there are several instances of missing information such as adequate background and justification in the introduction, experimental details in the materials and methods, and the requisite information to interpret the plots in the figure legends. We believe that while the research is worthwhile, the aforementioned issues significantly hinder any conclusions made in the manuscript and need to be addressed.

General comments:

1. In the study, they find that "23 out of 118 (19.5%) patients with follow up at 2 months and 31 out of 83 (37.3%) patients with follow up at 6 months suffered from recurrent CDI after the initial FMT." These failure rates make us wonder if the FMTs can even be considered successful. Given these high failure rates, we wonder how meaningful the results of this study are. The low rates are addressed briefly in the discussion by saying "Many studies exclude subjects with severe CDI, a known predictor of CDI recurrence, which may explain the lower success rate of FMT observed in our cohort compared to others." This explanation, however, is somewhat contradicted when discussing predictors of short term relapse (failed FMT) which included "severe CDI" suggesting that other studies must have also included severe cases in their cohorts. Some clarity regarding these points would greatly appreciated.

2. Although "microbiome engraftment" is a critical concept in this paper, it is never specifically defined or discussed in the context of current literature. Likewise, while engraftment is listed as a secondary outcome, they did not define what a successful engraftment would actually look like. The authors should expand upon the meaning of the phrase and they should also review CDI FMT literature, framing this study in terms of what has been seen previously.

3. Throughout the manuscript, FMT is being used to refer to materials used for the transplant while it really means the process. For example, "FMT was obtained from healthy donors..." should be "Material for FMT was obtained...." This needs to be corrected in several instances.

4. The Methods section needs additional details on how 16S rRNA gene sequences were processed. Additionally, specific details regarding software (parameters used, version, etc.) are absent but are required for proper interpretation of the analysis pipeline. The details that are provided in the Supplemental Material are inadequate and they really should be in the main body of the paper given their importance to the overall story.

5. The last section within the results where the functional analysis of the patient microbiomes is described doesn't warrant its own subsection. The information contained is too broad and disjointed as it's presented and either needs to be expanded on, included elsewhere, or removed altogether. While interesting, it doesn't appear to contribute anything to the main narrative as defined by the primary and secondary outcomes laid out in the introduction.

6. The figure legends were missing almost all information required to interpret the plots and, in some cases, the labels provided were even in the wrong order. Specific methodological and statistical methods need to be stated for each panel or groups of panels.

7. The manuscript needs thorough editing for language and grammar. There are multiple places where it is unclear what pronouns refer to, mixtures of tenses, and confusing sentence structure.

8. For the microbiome analysis, the study included a 9 vs. 9 study design but there isn't any indication whether that would be sufficient to detect the effects of interest. Power calculations need to be provided indicating what effect sizes the study design would allow the investigators to detect for their primary research questions.

9. If the authors used phylogenetic methods, how did they get OTUs for the Random Forest approach? If they generated OTUs, then why not also analyze OTU-based metrics of alpha and beta-diversity. The reference-based UniFrac methods that the authors likely used are strongly biased by what is in the database and are known to have numerous problems relative to de novo clustering methods.

10. Comparison of the microbiota over time should be done with paired tests using each subject as their own control.

11. In the text relating to Figure 2A, the authors use "bacterial alpha diversity", but the y-axis of the figure says "phylogenetic diversity" while an identical plot in Figure 2C uses "alpha diversity" for the y-axis. In addition to this, the y-axes in these plots should start at zero, not 5 or 2.5. The same is true for Figure 3A.

Further Questions:

12. Did the 18 people subjected to the microbiome analyses have a difference in recurrence rates?

13. What percent of the IBD patients went into remission?

14. Was there a relationship between donor and the requirement for escalation of medication (IBDe) vs. the stable group (IBDs)?

Specific Comments (P = page, p = paragraph):

15. P4p2: "reducing bacterial diversity and the abundance of Bacteroidetes and Firmicutes phyla"

16. P4p2: The authors reference an "aberrant microbiome with a donor-like microbiome," however, the supporting data are mixed and don't present a clear conclusion. The aberrant microbiota are supplemented with microbiota from a donor, but it doesn't consistently take on the structure of the donor.

17. P4p2: When stating, "frequent use of concomitant immunosuppressive agents" we assumed that this is in reference to IBD and not CDI treatment, but the writing could be made clearer.

---

<br>

[^1]: I do not know the current status of this manuscript and have not been invited to review it for a journal. I have posted a copy of this review at [bioRxiv](https://www.biorxiv.org/content/early/2018/02/18/267492#comment-3835746060). Please post any comments there.
