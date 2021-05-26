# Git and the FFT
**Warning:** this section contains math and Perl. If that isn't your thing, then I'm sorry. Perl is great.

Picking up from [early signs](early-signs.md), Joyce suspected I had bipolar. I was equally sure I did not. My moods varied day to day, not month to month that I knew of. And while I frequently woke up at 1-2am and worked a 16-hour day, that's just because I was awesome and loved my job. Gotta give my long-suffering managers something to appreciate.

But anyway, I needed to prove to Joyce once and for all that I was totally not crazy, so I did what any not-crazy person would do and downloaded my entire github history so I could run it through an FFT. Top frequency component should be 24 hours, guaranteed: I write code most mornings and almost never at night.

(Spoiler alert: I obviously found something far more sinister that led me to conclude I was mentally ill. Full exposition below!)

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
$ ni my-commits p'tep m => c' ocp'r F_, "." x int(a/40)'  # reduce by month
916     1       ......................
1301    2       ................................
1361    3       ..................................
1074    4       ..........................
1059    5       ..........................
828     6       ....................
808     7       ....................
815     8       ....................
1235    9       ..............................
1332    10      .................................
1151    11      ............................
942     12      .......................

$ ni my-commits p'tep H => c' ocp'r F_, "." x int(a/20)'  # reduce by hour
569     0       ............................
460     1       .......................
502     2       .........................
462     3       .......................
352     4       .................
285     5       ..............
161     6       ........
161     7       ........
170     8       ........
217     9       ..........
332     10      ................
453     11      ......................
674     12      .................................
976     13      ................................................
961     14      ................................................
874     15      ...........................................
729     16      ....................................
819     17      ........................................
741     18      .....................................
644     19      ................................
598     20      .............................
531     21      ..........................
575     22      ............................
576     23      ............................
```

Bear in mind that I'm UTC-6 or UTC-7, so what looks like 0600 is in fact nearly midnight. I don't usually code in the evenings, so that's what you're seeing between 0500Z and 0900Z.

Anyway, you'll notice that there's a surprising amount of consistency to the monthly table. The hourly table is pretty stable too, but that's to be expected: I've kept a reasonably stable bedtime even if I wake up early.

Also, if I committed code at, say, 11pm, odds are that I woke up at 11pm and started my day, not that I stayed up that late.


## About those early mornings
I didn't tend to log on early, write a few lines of code, and go about my day. If I was getting up at 11pm or 2am, it's because I was in _maximum shipit mode_ -- hyper-focused and usually issuing the first commit only after at least an hour of work (as opposed to later in the day, when I'd commit more often but less content each).

Tying this all back to neurotransmitters, the real indicator is seasonal shifts in daily schedule. Let's plot that out:

```sh
$ ni my-commits p'r tep Hm => c' oABcfBCA XfB. \
     Wn0 ^i[_ jan feb mar apr may jun jul aug sep oct nov dec] _

_   jan  feb  mar  apr  may  jun  jul  aug  sep  oct  nov  dec
0   36   72   56   34   55   24   33   32   60   56   59   52
1   26   48   60   32   35   30   34   21   36   36   53   49
2   36   58   56   27   48   30   35   26   47   61   31   47
3   19   74   52   22   43   34   26   31   37   31   50   43
4   33   69   24   9    28   8    15   25   50   31   40   20
5   17   62   14   9    39   4    13   8    35   23   38   23
6   11   21   6    7    31   12   17   12   12   5    14   13
7   4    11   11   21   32   12   16   11   14   14   4    11
8   11   9    12   20   26   12   6    20   14   23   9    8
9   5    9    29   33   21   21   19   23   13   15   13   16
10  21   20   24   36   24   38   21   32   35   37   19   25
11  46   27   44   55   24   49   22   26   35   66   40   19
12  49   55   59   80   23   37   46   39   50   118  71   47
13  83   85   111  89   45   51   44   52   117  120  96   83
14  64   93   112  103  65   61   62   66   74   105  86   70
15  72   81   88   68   78   64   51   62   70   57   94   89
16  64   57   89   62   46   58   43   49   70   62   75   54
17  66   69   87   83   78   65   58   66   80   69   41   57
18  38   70   80   67   67   52   67   31   78   82   57   52
19  49   64   80   66   40   46   37   35   67   65   58   37
20  39   63   75   33   54   48   52   25   79   54   58   18
21  36   69   58   35   54   21   30   33   51   71   39   34
22  58   57   57   45   55   22   33   59   38   71   51   29
23  33   58   77   38   48   29   28   31   73   60   55   46
```

...and there it is: a pronounced increase in commits at 0600-0700 local time in March/April and Sept/Oct, almost three times as high as July.

This pattern doesn't always indicate a mental disorder, but I don't have any lifestyle habits that would explain it otherwise. I don't set an alarm to wake up in the morning, for example. If I'm awake at 4am with tons of ideas, that's neurochemical, not deliberate.

So that's the story: hoisted by my own frequency analysis.

(In the original I had used an FFT. It was less descriptive in that it showed the highest frequency at 6 months but didn't break it down by month. That alone was convincing, and I later broke it down to realize that my early mornings happened when the weather changed during the spring/fall. I decided to skip the FFT for this iteration because it's easier to see what's going on with the 2D histogram above.)


## Appendix: how the original FFT analysis worked
First, we roll up commits by hour -- and not just hour of day; this is actually hour-since-epoch. Then we can count these up, shift the offset to zero, and FFT the frequency distribution.

We need to figure out exactly how many hours we're representing so we know what the components divide.

```sh
$ ni my-commits pc/3600 ,qor1 +[my-commits pc/3600 ,qor+1]
337133
448627      # we span a total of 111494 hours, which is 4645.5833 days

# top frequency components between 0.5 and 400 days
$ ni my-commits pc/3600 ,qo,0cp'r b, 0, a' Xp'a // 0' \
     N'x = abs(fft.fft(x.T)).T' Wn p'r 4645.5833/a . " days", b' r-1 \
     rp'within 0.5, 400, a' x O _

4192.7750285849   0.999695136647299 days
3667.94058717278  0.999265067756507 days
2273.6972143173   0.998835368737906 days
1614.72525715765  136.634802941176 days
1381.04463256697  145.174478125 days
1281.9201796485   1.00012557588805 days
1251.48119018401  113.306909756098 days
1251.32951792833  178.676280769231 days
1239.44680502605  140.775251515152 days
1210.09932465431  16.710731294964 days
1197.79903942432  185.823332 days
1188.52496828908  160.192527586207 days
1133.18057261218  0.500008965665698 days
1076.31747004068  105.581438636364 days
1072.86184919921  1.00055638595736 days
1065.51384606261  22.5513752427184 days
1053.32518318295  67.3272942028986 days
1051.13781493932  42.6200302752294 days
1045.85462490075  69.3370641791045 days
1040.94932885456  96.7829854166667 days
1037.95211857808  331.827378571429 days
1011.75413106334  1.00098756733463 days
...
```

I think daily has edged out 178-day because I haven't filtered commits by volume, and I've written a decent amount of code since being medicated, which has ironed out my schedule by a lot. When we ran the analysis the first time around, the mid-year stuff like 136 and 178 was slightly higher than 24-hour.
