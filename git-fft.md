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
$ ni . p'"git://$_"' \<ps/^gitcommit:/githistory:/r fA\<
```
