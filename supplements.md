# Supplements
**TODO**


## Third-party QA for supplements
Joyce and I subscribe to [Consumer Lab](https://www.consumerlab.com/), which tests supplements for impurities. I need to do more research about supplement safety, but I know regulations differ a lot between supplements and medications ([wikipedia](https://en.wikipedia.org/wiki/Regulation_of_food_and_dietary_supplements_by_the_U.S._Food_and_Drug_Administration)).

CL has alerted us to some interesting and worthwhile knowledge, for instance that cocoa products tend to be contaminated with cadmium (which is toxic and has a half-life of [6-38 years](https://www.atsdr.cdc.gov/csem/csem.asp?csem=6&po=9)). I consider third-party QA to be prerequisite due diligence for anything I plan to take in large amounts or over long periods of time.

**Note:** I don't know why we use CL over other options, or if there's a specific reason. I just know there are services like this that test stuff and that they're probably a good idea if you're buying less-regulated substances.


## Pharmacokinetics
I think it's important to consider the lifecycle of anything you consume, particularly concentrated substances like supplements or medications. [Pharmacokinetics](https://en.wikipedia.org/wiki/Pharmacokinetics) covers this in detail.

I tend to think about pharmacokinetics in terms of three questions:

1. **How is the substance broken down?** Does it produce toxic metabolites or accumulate in organs? Do its metabolites create downstream imbalances?
2. **What's the elimination rate?** Is it zero-order (no half life; alcohol) or first-order (half-life; almost everything else)? What's the area under the curve for a fixed dose of something?
3. **What happens if overdose occurs?** Is there a rate-limiting conversion enzyme?

For example, alcohol and theanine:

+ [Alcohol (pharmacokinetics)](https://en.wikipedia.org/wiki/Alcohol_(drug)#Pharmacokinetics)
  + ≥80% oral bioavailability
  + Elimination is zero-order, which produces a dose-quadratic total exposure
  + Overdose is highly dangerous, both due to dose-quadratic exposure and the lack of rate-limiting in the brain
  + [Alcohol dehydrogenase](https://en.wikipedia.org/wiki/Alcohol_dehydrogenase) in the liver: zero-order conversion to [acetaldehyde](https://en.wikipedia.org/wiki/Acetaldehyde), which is toxic and responsible for hangover symptoms
  + [Acetaldehyde dehydrogenase](https://en.wikipedia.org/wiki/Acetaldehyde_dehydrogenase) in the liver: conversion to [acetic acid](https://en.wikipedia.org/wiki/Acetic_acid), which is well-tolerated by the body
+ [Theanine (metabolism)](https://en.wikipedia.org/wiki/Theanine#Digestion_and_metabolism)
  + Elimination is first-order, which produces a total exposure of roughly `dose * log(dose)` -- half life is ~1hr
  + Overdose is not very dangerous; theanine has much lower affinity than glutamate for receptors
  + As a structural analog of glutamate and glutamine, it is hydrolyzed to L-glutamate and [ethylamine](https://en.wikipedia.org/wiki/Ethylamine) by the liver and small intestine, and is considered to be a glutamine donor


## Caffeinated beverages and xanthines
Not super relevant, but I've gotten some benefit from switching to yerba mate from coffee. Different beverages have different xanthine and antioxidant profiles that can change their metabolic impact to some degree.

+ [Xanthine](https://en.wikipedia.org/wiki/Xanthine)
  + [Theobromine](https://en.wikipedia.org/wiki/Theobromine), a metabolite of caffeine that doesn't cross the BBB
  + [Caffeine](https://en.wikipedia.org/wiki/Caffeine), theobromine plus one methyl group (crosses BBB)
  + [Theophylline](https://en.wikipedia.org/wiki/Theophylline)
+ Xanthine-laden stuff
  + [Coffee](https://en.wikipedia.org/wiki/Coffee), which contains caffeine but no other xanthines ([SO answer about this](https://coffee.stackexchange.com/questions/2872/theobromine-in-coffee))
  + [Green tea](https://en.wikipedia.org/wiki/Green_tea)
  + [Yerba mate](https://en.wikipedia.org/wiki/Mate_(drink)), my favorite kind of tea, and one that includes all three xanthines
  + [Cocoa](https://en.wikipedia.org/wiki/Cocoa_bean#Phytochemicals_and_research), which contains caffeine and theobromine
  + [Matcha](https://en.wikipedia.org/wiki/Matcha), a green tea that naturally contains [theanine](https://en.wikipedia.org/wiki/Theanine) (which I think everyone should be familiar with; see the NMDA section above and [here](alcohol-substitution.md))
  + **TODO:** black and oolong teas, although I don't have a lot of experience with them aside from pu'erh

My intuition is that xanthines, and really anything that increases basal metabolic rate, will cause the body to emit more ROS and therefore increase the need for antioxidants. I suspect it also increases required methylation throughput, which may be why caffeine raises homocysteine ([pubmed](https://pubmed.ncbi.nlm.nih.gov/12450889/)).
