# Open source bipolar disorder
**Work in progress**

Early 2019 Joyce and I figured out that I have bipolar disorder -- and probably have for most of my adult life. That was a surprise and it kicked off a bunch of research and reflection, not all of which was straightforward.

I've wanted to write about it ever since the diagnosis, but it's not an easy topic for me to address. The biggest obstacle isn't that I'm unwilling to talk about it; that's actually very easy for me. The hard part is maintaining enough emotional composure to discuss it without sounding like a lunatic. I spend most of my time being an engineer, which means (1) I'm not a great writer; and (2) I usually write about emotionally un-demanding things.

So this whole project is, in that sense, outside my comfort zone. Sorry in advance for the uneven quality.

As for why it exists, it's for the same reasons I write open-source software. Whenever I solve a hard problem and learn something, I want to publish the solution so others have more to work with. Different people will solve similar problems in different ways, but if more of those ways are explained then the world is easier to navigate.

Given that, **this writeup is intentionally subjective.** Even when I don't phrase things that way, that's how I intend it. My main goal is to describe my experience, reasoning process, and how I relate to it all in hindsight -- and to preserve as much detail as I can. Not everyone with bipolar disorder will see things the same way, nor will many of my decisions make sense for other people. Like any open-source project, I welcome feedback. You can email me or file a github issue; I'll respond to both.

This writeup also covers some hard topics, plumbing the depths of depression and that sort of thing. I've tried to indicate ahead of time when you'll encounter these sections so you can skip over them, and where possible I've tried to provide lighter alternatives to make up any missing context. I don't think they're bad sections or poorly written, but I think they aren't for everyone. If you read this writeup repeatedly and never touch some sections, I think that's appropriate; it's what I had in mind when writing it.

(If you clone the project locally, hard topics are in `heavy/`; everything else should be easy reading.)


## Quick links for people with immediate problems
This section covers some quick, focused subproblems of bipolar and substance abuse. Most of the repo takes a broader perspective, but these pages are different in that they focus on very specific problems and solutions I either arrived at, or wished I had found.

I'm including it here because bipolar is a dangerous condition to face with a lack of information. I don't think I have authoritative, medically-correct answers; but I do have answers I believe are better than the bipolar status quo. To be fair, that's not a high bar.

+ [How I used safer alternatives to help get past alcoholism](alcohol-substitution.md)
+ [Emailing my employer: messages I couldn't write when impaired](emails.md)
+ **TODO**


## Part 1: the structure and implications of bipolar
Behold, the [bipolar UK mood scale](https://www.bipolaruk.org/FAQs/mood-scale):

![the scale](https://www.bipolaruk.org/GetImage.aspx?IDMF=9e569223-c9dc-495b-b615-bb10837b15a8&w=453&h=640&src=mc)

As it says, this chart isn't authoritative, but Joyce and I have used it conversationally since she found it. The item descriptions reflect my experience, which range from 1-8 and occasionally 0 and 9. I can't comment on 10 because although I've had moments where I wasn't very coherent, I never lost touch with concrete reality.

I went through Youtube and collected some clips that, in my opinion, describe the atmosphere of each affective state:

+ [The quick version, starring Michael Scott and James Bond](bond-scott.md)
+ [The deep dive, same clips with commentary](heavy/deepdive.md)

Most of these moods occur in real-life situations, maybe with the exception of the highest and lowest extremes. Bipolar differs in that moods aren't tied to context anymore. So I'll be 7 or 8 for a month for no reason, then crash to 1-4 for the next two months. This creates two operational problems:

1. Most of the world, especially at work, expects people to exist between 4 and 6, maybe 7 occasionally.
2. Extremes like 0-1 and 8-9 don't work well for life in general; it's hard to maintain self-sufficiency, and high-end rational thought is pretty much impossible.

I've summarized some detailed issues in topic-specific pages:

+ [Bipolar in projects: consistency vs genius](consistency.md)
+ [Synthetic empathy: tolerance vs understanding](synthetic-empathy.md)
+ [Bipolar at work](heavy/bipolar-work.md)
+ [Bipolar in marriage](heavy/bipolar-marriage.md)


## Part 2: DIY medical practice for the win (probably)


+ [Sources and reliability](sources.md)
+ [Thought process around being my own psychiatrist](diy-medicine.md)
+ [OTC supplements and DIY quality control](supplements.md)


## Part 3: solving the problem
+ [Neurotransmitters and metabolism](neurotransmitters.md): things that go to 11

**TODO:** reflow these sections into the above structure

+ [Part 3: defining the requirements](requirements.md)
+ [Part 6: strategy and results](strategy.md)
