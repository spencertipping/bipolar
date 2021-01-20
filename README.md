# Open source bipolar disorder
Early 2019 Joyce and I figured out that I have bipolar disorder -- and probably have for most of my adult life. That was a surprise and it kicked off a bunch of research and reflection, not all of which was straightforward. I'm writing this up as the thing I wished had existed as I was trying to figure it all out.

I've wanted to open-source the thought process around this problem for some time, but writing about it has been difficult. I feel like I spend a lot of time discovering that I have unresolved issues with some subtopic, usually after my writing devolves into an unconstructive polemic. This is probably the tenth iteration.

...so I'm not writing this from a place of authority or even competence. It's just experimental outcomes and my interpretations of those results.

With that said, though, DIY psychiatry has been a lot more fun and effective than I thought it would be so let's get right into it. Fair warning: I started off in pretty rough shape but it's all uphill from there.

+ [Part 1: defining the requirements](#part-1-defining-the-requirements)
+ [Part 2: designing a solution](#part-2-designing-a-solution)
+ [Part 3: strategy and results](#part-3-strategy-and-results)
+ [Part 4: postmortem and future changes](#part-4-postmortem-and-future-changes)


## Quick but important aside for alcohol users
I used to rely on alcohol to medicate anxiety. This is a terrible strategy that causes brain damage and increases suicide risk.

**If this is you, [I have a whole page](alcohol-substitution.md) with some (in my opinion) much healthier and more effective alternatives that reduce OCD, may be neuroprotective, and mitigate suicide risk.** There are many safe OTC supplements that are shown to reduce addictive behavior, repair certain types of alcohol-induced brain damage, and provide comparable anxiolytic effects. I highly recommend reading about some of them before accepting alcohol as a solution to any problems or using it recreationally. [Go here!](alcohol-substitution.md)


## Part 0: background reading on neurotransmitters and metabolism
Here's a short list of Wikipedia and pubmed articles I found to be most helpful when designing a treatment strategy for my bipolar symptoms. Again, not authoritative or complete, just some starting points I used to figure things out.

+ [Methylation](https://en.wikipedia.org/wiki/Methylation), relevant for reducing oxidative stress if you have an MTHFR mutation (I have C677T; 23AndMe can tell you what you are)
  + [MTHFR enzyme](https://en.wikipedia.org/wiki/Methylenetetrahydrofolate_reductase)
  + [Homocysteine](https://en.wikipedia.org/wiki/Homocysteine), most importantly the [methionine cycle](https://en.wikipedia.org/wiki/Homocysteine#/media/File:MTHFR_metabolism.svg)
  + [Hyperhomocysteinemia](https://en.wikipedia.org/wiki/Hyperhomocysteinemia), the reason I was anxious and miserable -- ([pubmed on Hcy and alcohol](https://pubmed.ncbi.nlm.nih.gov/10905999/), [pubmed on Hcy and coffee/caffeine](https://pubmed.ncbi.nlm.nih.gov/12450889/))
+ [Lithium](https://en.wikipedia.org/wiki/Lithium_(medication))
  + [Texas study suggesting that lithium is a trace nutrient](https://pubmed.ncbi.nlm.nih.gov/1699579/)
  + [Japanese study associating trace lithium with lower suicide risk](https://pubmed.ncbi.nlm.nih.gov/19407280/)
  + [Lithium aspartate](https://en.wikipedia.org/wiki/Lithium_aspartate) -- I've taken 40mg/day for 15 months and have substantially improved stability with no side effects (see below sections for more discussion)
+ [NMDA receptor](https://en.wikipedia.org/wiki/NMDA_receptor)
  + [Excitotoxicity](https://en.wikipedia.org/wiki/Excitotoxicity), particularly due to [glutamate](https://en.wikipedia.org/wiki/Glutamate_(neurotransmitter))
  + [GABA](https://en.wikipedia.org/wiki/Gamma-Aminobutyric_acid), the NMDA inhibitor people upregulate with alcohol and benzodiazepines
  + [GABA receptor agonist](https://en.wikipedia.org/wiki/GABA_receptor_agonist)
  + [GABA-A receptor positive allosteric modulator](https://en.wikipedia.org/wiki/GABAA_receptor_positive_allosteric_modulator)
  + [GABA-B receptor](https://en.wikipedia.org/wiki/GABAB_receptor)
+ [Neurotransmitters](https://en.wikipedia.org/wiki/Neurotransmitter)
  + [Monoamines](https://en.wikipedia.org/wiki/Monoamine_neurotransmitter)
    + [Dopamine](https://en.wikipedia.org/wiki/Dopamine)
      + [Phenylalanine](https://en.wikipedia.org/wiki/Phenylalanine), essential amino acid
      + [Tyrosine](https://en.wikipedia.org/wiki/Tyrosine), nonessential amino acid derived from phenylalanine
      + [Tyrosine hydroxylase](https://en.wikipedia.org/wiki/Tyrosine_hydroxylase): tyrosine -> [L-DOPA](https://en.wikipedia.org/wiki/L-DOPA)
      + [AADC](https://en.wikipedia.org/wiki/Aromatic_L-amino_acid_decarboxylase): L-DOPA -> dopamine
      + [Dopamine beta-hydroxylase](https://en.wikipedia.org/wiki/Dopamine_beta-hydroxylase): dopamine -> norepinephrine
      + [NDRIs](https://en.wikipedia.org/wiki/Norepinephrine%E2%80%93dopamine_reuptake_inhibitor), e.g. methylphenidate (Ritalin), bupropion (Wellbutrin), and amphetamine
    + [Phenethylamine](https://en.wikipedia.org/wiki/Phenethylamine), endogeneous amphetamine-like chemicals
    + [Serotonin](https://en.wikipedia.org/wiki/Serotonin)
      + [Tryptophan](https://en.wikipedia.org/wiki/Tryptophan)
      + [Tryptophan hydroxylase](https://en.wikipedia.org/wiki/Tryptophan_hydroxylase): tryptophan -> [5-HTP](https://en.wikipedia.org/wiki/5-Hydroxytryptophan)
      + [AADC](https://en.wikipedia.org/wiki/Aromatic_L-amino_acid_decarboxylase): 5-HTP -> serotonin (same as for dopamine)
  + [Monoamine oxidases](https://en.wikipedia.org/wiki/Monoamine_oxidase)
    + [MAO-B](https://en.wikipedia.org/wiki/Monoamine_oxidase_B), the enzyme that deactivates dopamine and phenethylamine
    + [Monoamine oxidase inhibitor](https://en.wikipedia.org/wiki/Monoamine_oxidase_inhibitor), antidepressants that deactivate MAO enzymes
    + [St John's Wort](https://en.wikipedia.org/wiki/Hypericum_perforatum), which may or may not be a MAOI ([this article cites some studies I haven't looked at](https://www.apsf.org/article/st-johns-wort-charge-refuted-by-herbalist/); I thought it inhibited dopamine beta-hydroxylase but maybe that's wrong)
  + **TODO**


## Part 1: defining the requirements
In practice this was a lot more incremental and scattered than I'm describing here, but that's just because I didn't know what I was doing nor what was possible. Here's the cleaned-up view in hindsight.


### The problem: mental symptoms I wanted to fix
1. I would routinely start a project, have tons of energy for a couple of weeks, then crash hard and lose interest in almost everything. As time went on, I'd get these bursts less frequently and became less productive.
2. I was increasingly anxious about nothing in particular. It got to the point where I often wanted to leave my life behind and start over, I guess to get rid of something I assumed was causing my stress.
3. I was suicidal most days and often medicated with alcohol, which didn't really address the problem and likely made it worse over time. It was very difficult to hold down a full-time job in this state.
4. I was generally neither productive nor smart. I hadn't written anything worthwhile in a couple of years, nor did I have any plans to. I hadn't given up, but didn't see a way forward.
5. Many times in the spring (usually mid to late April) I would become dissociated and want to leave my job, life, etc. In 2020 my plan was to become homeless and live under a bridge; that sounded awesome because nobody would expect anything from me. In prior years I had left jobs or incompetently attempted suicide.


### Constraints for a treatment strategy
I'll describe this from two perspectives because I think it's important to understand how it looks.

**Before pursuing treatment:** medical intervention just looked bad. The emphasis tended to be on stability, which I assumed would focus on preventing mania (true), so I expected to lose the highs I used to get things done and be largely unproductive/unmotivated. This was consistent with accounts I had seen online. Further, people complained about side effects ranging from weight gain to kidney failure. My mom had been misprescribed SSRIs for depression, probably caused by borderline or bipolar disorder, and both mentally and physically degraded over the span of about ten years before committing suicide in 2011.

**After pursuing treatment:** my space of concerns isn't different, and I'm glad I'm not taking anyone else's word for these things. I have a lot of control over how I function, which is really all I wanted. Rather than trying to mitigate positive symptoms, I focus on thinking better: without any intervention my brain wasn't getting what it needed; I frequently ran low on dopamine, my metabolism was underperforming due to MTHFR, and my depressive crashes and anxiety were a symptom of oxidative stress. Bipolar wasn't a thing to be fixed, it was a sign that my body and mind weren't working correctly. I take medications (really supplements) to think better, feel better, and be more capable.

With that in mind, I wanted a treatment plan that met my needs, which were:

1. No adverse physiological side effects (including boring ones like weight gain)
2. No long-term neurodegeneration
3. No loss of mental function, especially for cognitively challenging R+D work
4. No controlled substances: robust supply chains for everything, whether or not I have health insurance or a primary care practitioner (I currently have neither)
5. Graceful fallbacks in case I need to change things down the line


### Quick meta-commentary about treatment methodology
I strongly believe that people considering different treatment strategies should (1) understand the process as a form of enhancement rather than mitigation, (2) prioritize quality of life above almost all else, and (3) have some fallback treatment strategies in mind -- bipolar has an abysmal medical compliance rate (numbers vary, but are commonly reported between 30% and 70% after two years).<sup>[2000 study](https://www.researchgate.net/publication/12340472_Clinical_Factors_Associated_With_Treatment_Noncompliance_in_Euthymic_Bipolar_Patients)</sup>

More controversially, I also believe people need better recreational alternatives to dangerous drugs like alcohol and, in certain cases, caffeine. I don't have numbers to quantify this, but I commonly see bipolar associated with substance abuse as a form of self-medication. Alcohol in particular is profoundly dangerous in conjunction with mental illness because it can impair methylation and deplete lithium, magnesium, and B-vitamins -- all of which are required to maintain normal brain function.


## Part 2: implementing a solution



1. Lithium, magnesium, and B-vitamin deficiency caused by alcoholism and chronic stress
2. Folate deficiency caused by MTHFR C677T mutation and possibly light skin tone (I think melanin blocks folate oxidation from sunlight)
3. Antioxidant deficiency caused by excessive caffeine use and alcoholism
4. Chronic dopamine deficiency, possibly from excessive caffeine use and oxidative stress
5. Maybe thyroid deficiency, I'm not sure


### Current medication routine
I've been on this since about May/June 2020, so eight months as of this writing. The results have been fantastic. I'm alert, focused, consistently motivated, and low-anxiety almost all the time -- none of which I thought I would ever be able to achieve.

I've broadly classified these things by functional category, not by how they work physiologically. More details on this in below sections.

+ Morning
  + Neurotransmitter regulation
    + 20mg lithium as lithium aspartate
    + 96mg magnesium via 1333mg magnesium threonate
  + Anxiolytics
    + 500mg theanine
    + 600mg ashwagandha
  + Stimulants
    + 10g tyrosine
    + 12-18g yerba mate tea
    + 6g ginkgo biloba + 6g bacopa monnieri + 6g gotu kola + 6g mint + 1g ginger root tea
  + Methylation and antioxidant support
    + 15mg-20mg methylfolate
    + 2.5mg methyl-B12
    + 2400mg long-release NAC
    + 1500mg vitamin C
    + 400mg riboflavin
  + General stuff
    + 225mcg iodine as potassium iodide
    + 10-20g collagen peptides
+ Evening
  + 20mg lithium aspartate
  + 3g taurine (as magnesium taurate)
  + 1000mg tryptophan peptides
  + B-vitamin complex
  + Vitamin E
  + 1000mg theanine
+ Weekly
  + Selenium

**NOTE:** I suspect some of my dosages are above what's necessary. I've gotten great results, but I haven't tuned any of this for efficiency yet and it's a bit of a work in progress. If you know of things I should improve, please let me know.

I also consistently eat eggs and fish for breakfast, usually four eggs and 4-6oz of tuna or salmon. The choline isn't a problem, although eggs and fish keep me awake and I can't supplement alpha-GPC, citicholine, or ALA without getting really depressed.

I still have minor mood and energy cycling throughout the year, but nothing like before. Sometimes I'll try to course-correct; here are some of the options I'll use (usually a subset, not all of them):

+ If I've been sick or feel really bad (uncommon):
  + 10g glutamine (excitotoxicity risk)
  + 5-10-20mg DHEA (steroid-related risks)
+ If I'm depressed or sluggish (uncommon, maybe 1-3 days/quarter)
  + more ginkgo+bacopa tea
  + +5-10mg methylfolate
  + +48mg magnesium threonate
  + +5g tyrosine
+ If I'm anxious or jittery (more common, maybe 7-10 days/quarter)
  + Decrease tyrosine and collagen
  + +500-1000mg theanine as needed
  + +600mg ashwagandha
  + +3-5g taurine (without magnesium)
  + +500mg tryptophan peptides
  + +5-10mg methylfolate
  + +2.5mg methyl-B12
