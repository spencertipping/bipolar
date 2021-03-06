# Git and the FFT
**Warning:** this section contains math and Perl. If that isn't your thing, then I'm sorry. Perl is great.

Picking up from [early signs](early-signs.md), Joyce suspected I had bipolar. I was equally sure I did not. My moods varied day to day, not month to month that I knew of. And while I frequently woke up at 1-2am and worked a 16-hour day, that's just because I was awesome and loved my job. Gotta give my long-suffering managers something to appreciate.

But anyway, I needed to prove to Joyce once and for all that I was totally not crazy, so I did what any not-crazy person would do and downloaded my entire github history so I could run it through an FFT. Top frequency component should be 24 hours, guaranteed: I write code most mornings and almost never at night.

I don't think I have the original workflow I used for this, but I'll make a new one.


## Downloading a git profile
...is surprisingly easy.

```sh
# if you don't have ni yet but want to follow along
$ curl -sSL https://spencertipping.com/install-ni | bash

$ export API=https://api.github.com/users; \
  ni n10p'"$ENV{API}/spencertipping/repos?per_page=100&page=$_"' \
     \<p'/"full_name":\s*"([^"]+)"/g' > my-repos

$ xargs -I{} -P4 git clone --bare git://github.com/{} < my-repos
```

This should be most of my git activity. You could replace `spencertipping` with your github username to download your profile.


## Commit metadata list
Let's gather every repo's history into a single unified list of commits. `ni` makes this easy because I wrote it to make this easy.

```sh
$ ni . p'"git://$_"' \<ps/^gitcommit:/githistory:/r fA\< r/spencer/ \
       gu =z\>my-commits wcl
12822   # 12822 commits over 12 years: still got it
```

Each commit is a single TSV row:

```sh
$ ni my-commits r10 _
gitcommit://./.emacs.d.git:03a3d4d1680bf91530f405416b36a2a020eba338  Spencer Tipping:spencer@spencertipping.com  1347811386  Fixed submodules
gitcommit://./.emacs.d.git:0c745755377af5d7519fddb5a63ff41f50899ae7  Spencer Tipping:spencer@spencertipping.com  1344531772  Small chnges
gitcommit://./.emacs.d.git:18801587a221a0fc56d8784f3319634ebe942156  Spencer Tipping:spencer@spencertipping.com  1347664039  Wider frame by default, smooth scrolling, viper mode
gitcommit://./.emacs.d.git:1bababb69fd6169db78f714145383d2b3c0f8a54  Spencer Tipping:spencer@spencertipping.com  1347826715  Updating/fixing submodules
gitcommit://./.emacs.d.git:21a7c88c507d072190cddfff509e1d7ad14af490  Spencer Tipping:spencer@spencertipping.com  1347826744  Re-added popup-el
gitcommit://./.emacs.d.git:28b008888fa27a776655ffe53ae8aa96eeb0051a  Spencer Tipping:spencer@spencertipping.com  1346943614  Added external copy/paste functionality
gitcommit://./.emacs.d.git:3e657f6df397d77025923d9321ed6422db0ec87d  Spencer Tipping:spencer@spencertipping.com  1346946321  Added vi-style % binding from http://www.emacswiki.org/emacs/NavigatingParentheses
gitcommit://./.emacs.d.git:4159973c7256339f8a92cf93e43d458b41837b2e  Spencer Tipping:spencer@spencertipping.com  1365450178  Various local changes
gitcommit://./.emacs.d.git:444be68f0b663aae0c9818cecae4e94e086a55cf  Spencer Tipping:spencer@spencertipping.com  1344441441  Merged changes from evan
gitcommit://./.emacs.d.git:4da1fb6e0731aef0ff4ffe923e72ab9c39253139  Spencer Tipping:spencer@spencertipping.com  1347846014  Fix submodule remotes
```

In particular, we have a ni-readable path to the commit object, the author data (which I've already grepped to be me), the UNIX timestamp, and the commit message. These are stored in a gzipped TSV file `my-commits`.


## Summarizing by time
The simplest approach is to just reduce into two facet histograms: one by month of year and one by hour of day.

```sh
$ ni my-commits p'tep m => c' oc    # reduce by month
916     1
1301    2
1361    3
1074    4
1059    5
828     6
808     7
815     8
1235    9
1332    10
1151    11
942     12

$ ni my-commits p'tep H => c' oc    # reduce by hour of day (UTC)
569     0
460     1
502     2
462     3
352     4
285     5
161     6
161     7
170     8
217     9
332     10
453     11
674     12
976     13
961     14
874     15
729     16
819     17
741     18
644     19
598     20
531     21
575     22
576     23
```

Bear in mind that I'm UTC-6 or UTC-7, so what looks like 0600 is in fact nearly midnight. I don't usually code in the evenings, so that's what you're seeing between 0500Z and 0900Z.

Anyway, you'll notice that there's a surprising amount of consistency to the monthly table. The hourly table is pretty stable too, but that's to be expected: I've kept a reasonably stable bedtime even if I wake up early.


## Let's adjust for commit contents
Just making a commit isn't much work. Let's scale each commit by the number of unique diff lines of human-written code.

```sh
# TODO
```
