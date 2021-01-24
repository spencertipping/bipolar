# Open source bipolar disorder
**Work in progress**

Early 2019 Joyce and I figured out that I have bipolar disorder -- and probably have for most of my adult life. That was a surprise and it kicked off a bunch of research and reflection, not all of which was straightforward.

I've wanted to write about it ever since the diagnosis, but it's not an easy topic for me to address. The biggest obstacle isn't that I'm unwilling to talk about it; that's actually very easy for me. The hard part is maintaining enough emotional composure to discuss it without sounding like a lunatic. I spend most of my time being an engineer, which means (1) I'm not a great writer; and (2) I usually write about emotionally un-demanding things.

So this whole project is, in that sense, outside my comfort zone. Sorry in advance for the uneven quality.

As for why it exists, it's for the same reasons I write open-source software. Whenever I solve a hard problem, I want to publish the solution so others have more to work with. Like software, it isn't about finding _the_ solution, it's about finding _my_ solution -- which may be similar to others' or it may be completely different. The goal isn't necessarily to solve everyone's problems, it's to prove that similar problems are solvable and explain the process.

**This writeup is intentionally subjective.** Even when I don't phrase things that way, that's how I intend it. My main goal is to describe my experience, reasoning process, and how I relate to it all in hindsight -- and to preserve as much detail as I can. Not everyone with bipolar disorder will see things the same way, nor will many of my decisions make sense for other people. Like any open-source project, I welcome feedback. You can email me or file a github issue; I'll respond to both.

This writeup also covers some hard topics, plumbing the depths of depression and that sort of thing. I've tried to indicate ahead of time when you'll encounter these sections so you can skip over them, and where possible I've tried to provide lighter alternatives to make up any missing context. I don't think they're bad sections or poorly written -- given the topic it's some of my most balanced engineering prose -- but I think they'll be hard to read and they certainly aren't for everyone. If you read this writeup repeatedly and never touch some sections, I think that's appropriate; it's what I had in mind when writing it.

(If you clone the project locally, hard topics are in `heavy/`; everything else should be easy reading.)


## Quick links for people with immediate problems
**TODO:** revisit this

Open-source projects often have some short algorithm that solves a lot of unrelated problems. I ran across things like this when working around my bipolar disorder, and have dedicated pages for some of them so you don't have to encounter them by chance in the full writeup:

+ [How I used safer alternatives to help get past alcoholism](alcohol-substitution.md)
+ **TODO:** the "don't die" project of self-directed lectures to prevent suicide
+ **TODO:** the "email my manager" problem


## Part 1: what bipolar is, and why it's a problem
Behold, the [bipolar UK mood scale](https://www.bipolaruk.org/FAQs/mood-scale):

![the scale](https://www.bipolaruk.org/GetImage.aspx?IDMF=9e569223-c9dc-495b-b615-bb10837b15a8&w=453&h=640&src=mc)

I don't know if this is authoritative or not, but Joyce found it and we've used it colloquially ever since. The item descriptions reflect my experience (if you take out hallucinations, I've run the full scale).

**FIXME:** the above is a lie

It's normal for people to experience different moods in context; for example, you take a risk, it pans out, and that's exciting -- you're at a 7 or maybe an 8 for a while. This makes sense and it isn't considered pathological.

Bipolar differs in that moods don't reflect context. You're a 2 or an 8 for no reason at all, and that's just your mood for the day or for the week.

**TODO:** fix continuity/focus in this section

+ [The mood scale from the inside](heavy/inside.md) -- this is the full-detail version of what each mood state looks like; it's rough and you can skip it
+ [Michael Scott and James Bond re-enact the mood scale](bond-scott.md) -- a summary of the one above, but way lighter


## Part 2: DIY medical practice for the win (probably)
I've decided to be my own psychiatrist and use OTC stuff to fix myself. This works surprisingly well _for me,_ much better than I expected it would. I'm not 100% neurotypical, but I don't think I want to be. I don't venture into problem-states and am productive and happy >95% of the time -- which is amazing given that I started around 15-20%.

I believe my outcomes would be measurably worse if I delegated this problem to a professional psychiatrist. Not all psychiatrists I'm sure, but a typical one chosen at random. I could be completely wrong in this judgment.

Anyway, here's the background for this approach:

+ [Sources and reliability](sources.md)
+ [Thought process around being my own psychiatrist](diy-medicine.md)
+ [OTC supplements and DIY quality control](supplements.md)


## Part 3: solving the problem
+ [Neurotransmitters and metabolism](neurotransmitters.md): independent variables for drug users

**TODO:** reflow these sections into the above structure

+ [Part 3: defining the requirements](requirements.md)
+ [Part 6: strategy and results](strategy.md)
+ [Part 7: postmortem and future changes](postmortem.md)
