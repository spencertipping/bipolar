# Open source bipolar disorder
Some updates as of September 2024:

1. This repo is no longer factually true, e.g. my medications have since changed. Allergies and immune activity played a big role in my problems, both of which have since been addressed by moving to California.
2. The perspective behind this repo was true when I wrote it, but I've changed since and wouldn't write it this way today. I'm thinking about writing another one, more retrospective in nature and from a more grounded point of view.
3. I'm keeping the repo preserved as it was written because it accurately captures the frame of mind I was in when I began realizing what sanity was (against the backdrop of insanity).
4. **GPT4o is great at this stuff.** Medical exploration, physiology, everything. I use it all the time now.
5. D-ribose has been great for recovery post-illness.

Maybe more updates later, but I think they'll be in the form of a new repo focused on the "life rebuild" problem that comes after 20 years of impaired decision-making. This repo is probably EOL, frozen in its current off-kilter state. Seems like a fitting end for the project.


## Original intro section
A pretty candid account of my experience with bipolar disorder: figuring out that it was a thing, managing it quasi-medically, reinterpreting past events with new context, and finding ways to socialize what mental illness is about and how to work with it. I sometimes generalize from my own experience in this writeup, and you should understand that to be speculation on my part. This story ends well.

I was on the fence about writing it up this way. You can see this especially in older revisions, but I'm still conflicted about parts of my own bipolar disorder despite knowing about it since 2019 and successfully medicating since late 2020. I'm also not used to putting my personal life on the internet as much as this repo does. There's a big difference between "[here's a cool project made from recycled garbage](https://github.com/spencertipping/www/blob/master/desk.md)" and "[here's the garbage I gave my wife and my coworkers for years and still regret](early-signs.md)". Those mistakes are worth owning but that doesn't make them easy to revisit; I sucked then, so why do I expect not to suck now or in the future? (And is medication the only reason? If so, what does that say about having integrity?)

Beyond catharsis, I decided to publish my experience because there aren't many people who have taken the DIY route on mental health. Given how often bipolar leads to medical noncompliance (which is dangerous from a substance abuse and suicide-management perspective), I want to document the thought process behind developing a self-medication strategy focused on OTC substances, and with the goal of long-term neuroprotection and high function in the immediate. I think this should be survival knowledge for anyone who may become medically noncompliant.

So let me know what you think about all this. I hope it's useful.

+ [Notes about the making of this project](making-of.md)

**Work in progress:** this is a challenging project because I'm experimenting with different ways to socialize something that isn't often talked about. It's important to me to finish writing it all up, but I have to step back a lot to keep the scope contained and attend to other projects (closed-source, hence the lack of other visible Github stuff). So for now this repo is an uneven collection of notes whose quality leaves a lot to be desired. It will get better, though. If you have suggestions I'd love to hear them.


## I'm not a doctor
And nothing here is medical advice. I'm documenting my thoughts here for informational purposes.


## Top-line issues
**If you are using alcohol as a medication:** I did this too, it's very dangerous, and there are safer and more fun alternatives that don't result in hangovers or long-term brain damage. [I have a whole page about this.](alcohol-substitution.md)

**If you're using heroin as medication:** I haven't done this, but there is evidence that links heroin dependence to MTHFR/CBS enzyme impairments and elevated homocysteine ([source](https://www.omicsonline.org/open-access-pdfs/methylene-tetra-hydrofolate-reductase-c677t-gene-polymorphism-in-heroin-dependence-2155-6105-1000226.pdf)), both of which can be addressed with over-the-counter methylfolate and methylated B12. I have the MTHFR C677T mutation and it caused substantial depression+anxiety before I started taking activated folate. See the methylation section on the [neurotransmitters page](neurotransmitters.md) for an explanation of why this happens.

**If you're mentally unstable and need lithium, but want precise control over the dosing and supply chain:** you can get low-dose lithium supplements over the counter from high-quality suppliers. If you ever consider suicide, suffer from severe OCD, or want to improve focus+stability, I highly recommend trying lithium microdosing (I do 40mg/day; many people would probably benefit from 5-10mg/day). I have a [section on this on the neurotransmitters page](neurotransmitters.md#Lithium-trace-mineral-for-neurotransmitter-regulation) that goes through some studies and explains why it's perfectly safe to take lithium in these quantities.

**TODO:** add a section about top-line physiological stressors like homocysteine, the enzymes that regulate them, and things you can do to modify them


## The diagnosis problem
Bipolar is notoriously difficult to diagnose, on average requiring between five and ten years. It's often misdiagnosed as depression, I assume because people don't go to a psychiatrist for being too productive. Misdiagnosis ends up creating a bunch of other problems when it happens: antidepressants can cause mania to a larger degree than would otherwise occur (then followed by worse depression, etc).

To Joyce's credit, she suspected I had bipolar for a few years before we figured it out. I never fit the official symptom list that well, though. I suspect the diagnostic criteria are intentionally extreme to avoid false positives.

+ [Early signs that something was amiss](early-signs.md)
+ [Git, open source, and the fateful FFT](git-fft.md)


## Identifying with mental illness
_Oh shit, I have a mental illness. How much is real anymore? If my brain is broken, what can I assume?_

Turns out, quite a lot. All but the most extreme states of bipolar are confined to affective disruption, not altered reality. So feeling things that don't make sense in context, but they're still within the range of things most people would feel in certain situations. Concrete, conscious thought was pretty stable, if sometimes motivated by deranged frames of mind.

Bipolar is often described in terms of depressive, hypomanic, and manic states. Joyce found a summary chart from [bipolaruk.org](https://www.bipolaruk.org) that we've found helpful:

![the mood scale](https://www.bipolaruk.org/GetImage.aspx?IDMF=9e569223-c9dc-495b-b615-bb10837b15a8&w=453&h=640&src=mc)

...and having been through most of this, I've found some YouTube clips from _The Office_ and James Bond that cover 0-9:

+ [Bipolar in _The Office_ and James Bond clips](bond-scott.md)
+ [Same clips with more detailed commentary](heavy/deepdive.md)
+ [Young Mania Rating Scale](https://dcf.psychiatry.ufl.edu/files/2011/05/Young-Mania-Rating-Scale-Measure-with-background.pdf)


## Enzymes and neurotransmitters
As an engineer, I wasn't going to be living in a defective body without trying to fix stuff. Broken hardware is just an opportunity to figure out how it works and make it work better than it was designed to.

(By the way, I write this up like it was deliberate, linear process where I knew what I was doing. It wasn't. Joyce and I fumbled our way through all of this.)

The first step was to stop trying to commit suicide so much. The biggest problem there was alcoholism:

+ [Getting over alcoholism with OTC alternatives](alcohol-substitution.md)

Once that was sorted out I could make better progress on the cognitive end -- and there's a lot to that. Joyce had done some of the research into the MTHFR enzyme already; we knew I had the C677T variant from my 23AndMe profile. I started digging into neurotransmitters in general, encountering a wide variety of enzymes and cofactors. Here's a summary of that process, as well as some thoughts about sourcing and reliability:

+ [Neurotransmitters, enzymes, and cofactors](neurotransmitters.md)
+ [Sources and research](sources.md)


## Medication for the win
I understood bipolar to have neurodegenerative properties if left untreated, which was a forcing move to medicate. Then the question became, do I outsource to prescription meds and psychiatry or try a DIY approach? As someone who just cut a 4x4' hole in my living room floor to install a subterranean datacenter, I obviously opted for DIY. Here's my thought process:

+ [Why I'm DIYing psychiatric care](diy-medicine.md)
+ [OTC psychoactive supplements, pharmacokinetics, and DIY quality control](supplements.md)
+ [My current medical strategy](strategy.md)


## The new hybrid
Turning me into a neurotypical person is probably beyond medical capability, but beyond that I'm not sure it would be valuable. My goal wasn't to erase bipolar, but to mitigate the problems it produced.

Not everyone will want to or be able to see it this way. It helps a lot that I can discuss mental health pretty openly with my coworkers ([Seeq](https://seeq.com) has been excellent across the board), so if I'm having an off-day I can say that and it isn't a big deal. The tech industry in general is willing to trade predictability for out-of-the-box thinking, which is a good fit for me. True to form, my consulting role with Seeq has converged to a mixture of weird off-timeline projects and fun debugging adventures. It's pretty awesome.

Since medicating I can reliably appreciate why I'm married with kids; there seems to be new/better hardware support for stable relationships. I still don't get jealousy or nepotism, but those seem like bugs not features. Individualism all the way.

Maybe the best part of post-medication life is that I can now execute long-term projects, one of which is a software company Joyce and I are starting together. She's also working through mental illness of her own, so we're taking a leisurely pace. That's also something that wasn't possible before.

A few other notable changes:

+ I perceive small positive things with much more fidelity: a sunny breeze, birds, that kind of thing. Elevated homocysteine had made all of this go away. I had forgotten how much I missed it.
+ I'm in a good mood basically every day -- like 95% of the time. I wake up and can count on feeling level and productive. And it's not depressed-productive, it's nearly-hypomanic-productive. Compared to before it's unreal.
+ I used to consider suicide every week or two; now I haven't thought about it in over a year.
+ I can write balanced prose now. Everything before wound up being a polemic by the time I was motivated enough to publish it, but now there's like nuance and stuff.
+ I don't have self-destructive habits like alcoholism, and I don't miss them. Upregulating GABA was better done by addressing nutritional deficiencies.
+ Because I'm biohacking all the time, I can modify stuff. On days when I do consulting work I increase tryptophan and decrease choline to be more sociable. Working solo is the opposite; I want to be more driven and intense.
+ I am never anxious anymore unless I've got a virus/infection/bug, which isn't very often. This is awesome.

I'm also collecting a very detailed profile of quantification data to monitor for further optimization down the line. I have a repo I'm going to publish soon that explains that project in the context of behavior and addiction management; I'll link it here when it's ready. Stay tuned.


## Appendix for scratch: random reading
Things I thought were interesting but haven't integrated into the writeup yet.

**TODO:** link these where they belong, or maybe start/keep a random-reading section if it makes sense

+ [Bipolar disorder and immune dysfunction](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5704151/)
+ [Potentiation strategies for treatment-resistant depression](https://pubmed.ncbi.nlm.nih.gov/16307616/)
  + [Lithium augmentation of antidepressants](https://pubmed.ncbi.nlm.nih.gov/9635546/)
  + [Thyroid augmentation of antidepressants](https://pubmed.ncbi.nlm.nih.gov/9635545/)
+ [Neuropharmacology](https://en.wikipedia.org/wiki/Neuropharmacology)
  + [Neuropsychopharmacology](https://en.wikipedia.org/wiki/Neuropsychopharmacology)
+ [Memory consolidation](https://en.wikipedia.org/wiki/Memory_consolidation)
  + [Hippocampus](https://en.wikipedia.org/wiki/Hippocampus)
  + [Long-term potentiation](https://en.wikipedia.org/wiki/Long-term_potentiation)
  + [Long-term depression](https://en.wikipedia.org/wiki/Long-term_depression)
  + [Long-term potentiation in bipolar II](https://pubmed.ncbi.nlm.nih.gov/29795193/)
  + [Impaired synaptic plasticity in bipolar II](https://pubmed.ncbi.nlm.nih.gov/22036034/)
