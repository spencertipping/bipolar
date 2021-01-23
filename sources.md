# Finding reliable sources
Wikipedia is great but doesn't have everything. I often end up consulting other websites like [Drugs.com](https://drugs.com) for supplemental information.

I've found [MediaBiasFactCheck.com](https://mediabiasfactcheck.com) to be pretty reliable for determining whether a source is accurate. I occasionally think they may be a little off, for example with [PsychologyToday](https://mediabiasfactcheck.com/psychology-today), which I wonder about sometimes. But overall I think their assessment of sources is pretty accurate and I tend to trust them. I also think it's worth reading [their wikipedia page](https://en.wikipedia.org/wiki/Media_Bias/Fact_Check) for context.

If you know of a better fact-checking strategy, I'd like to hear about it. This is something I haven't thought about as much as I probably should.


## The replication crisis and why I largely ignore it
You've probably heard about [the replication crisis](https://en.wikipedia.org/wiki/Replication_crisis) affecting social sciences and medical studies. I don't consider this to be a reason to discount science or medicine because alternatives are much worse. It's more about being proactively aware of potential conflicts of interest in study design and trying to understand the mechanisms behind effects that have been observed to see if it passes a sanity check.

I also don't want to understate how serious the replication crisis is for reliability purposes. Numbers vary, but Wikipedia currently describes [reproducibility in medicine](https://en.wikipedia.org/wiki/Replication_crisis#In_medicine) this way (emphasis mine):

> Out of 49 medical studies from 1990–2003 with more than 1000 citations, 45 claimed that the studied therapy was effective. Out of these studies, 16% were contradicted by subsequent studies, 16% had found stronger effects than did subsequent studies, 44% were replicated, and 24% remained largely unchallenged. The US Food and Drug Administration in 1977–1990 found flaws in 10–20% of medical studies. In a paper published in 2012, Glenn Begley, a biotech consultant working at Amgen, and Lee Ellis, at the University of Texas, found that only 11% of 53 pre-clinical cancer studies could be replicated. **The irreproducible studies had a number of features in common, including that studies were not performed by investigators blinded to the experimental versus the control arms, there was a failure to repeat experiments, a lack of positive and negative controls, failure to show all the data, inappropriate use of statistical tests and use of reagents that were not appropriately validated.**

At its core, this is really bad -- but a most of it doesn't apply uniformly (hence the emphasis).

A nontrivial amount of the controversy involves cancer treatments, whose conflict-of-interest profile is pretty different from psychiatric medicine -- especially supplement-based. But it's worth looking out for studies that have questionable features.

For example, I'll go through how I would evaluate [this study on gotu kola and acoustic startle response](https://pubmed.ncbi.nlm.nih.gov/11106141/), which I found after drafting the [strategy section](strategy.md):

+ Conflicts of interest
  + Gotu kola is unregulated, so there's no regulatory incentive to conclude efficacy (good)
  + Gotu kola is a traditional herb that isn't patented, so supply chains have no artificial price inflation (good)
  + Gotu kola isn't the leading product for any company I know of, so I don't think it's going to figure into anyone's sales strategy in an outsized way (good)
  + Traditional medicines are often debunked by studies, so I doubt any researcher is going to tip the scales in favor (good)
  + The sample size is tiny, N = 40, which suggests there wasn't a lot of money that went into it (probably good)
+ Study structure
  + Double-blind (good)
  + Placebo-controlled (good)
  + Concrete hypothesis about receptor bindings up front (good), but some studies have been rewritten after the fact to look this way -- that's part of the replication crisis
  + Prior evidence with mice (good; mice are basically people so this study is pretty redundant)
  + Not-huge sample size (meh)
+ Supporting evidence
  + [CKK receptors](https://en.wikipedia.org/wiki/Cholecystokinin) do in fact relate to anxiety (good)
  + [Wikipedia](https://en.wikipedia.org/wiki/Centella_asiatica) doesn't mention any mechanism of action (meh, but pretty standard for traditional medicines)
+ Reporting
  + "Significantly" without any quantity or p-value attached (bad -- although I suspect/hope the full text has numbers)
  + Measurement methodology is hinted at but not described in detail (meh, although I assume the full text addresses this)
  + Onset and duration are included (good, so I can try it myself)
  + Dosage is included (good, so I can try it)

This is barely a methodology on my part because I'm just justifying stuff after the fact. But it's roughly the set of things I'd look for if I wanted to figure out whether a study was reliable.
