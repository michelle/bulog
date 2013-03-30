---
layout: post
title: 21 nested callbacks
---

About 21 months ago, before I even knew what a callback was, I
built my first webpage. In honor of its 21 nested callbacks, I think it's about
time I finally take a second look at it.

At the time I had a perhaps cliche habit of doodling in my
notebook during humanities classes and family road trips. One particular
summer road trip yielded a collection of triangles that I thought looked pretty
cool. I decided that a worthy mid-summer endeavour would be to reproduce it
digitally. I also thought that would make me extremely cool on Tumblr.

I began by asking CS major friends if they could point me in the right
direction. The canned responses I received can be summarized as
**"Google it."** Subtext: "If you can't figure it out from there, you're
incompetent."

<img src="/images/triangles.png" width="260"><img src="/images/triangles2.png" width="260">

"I'm trying to make a triangle on my webpage...but Google doesn't seem to
give me any good results."

"No, Google 'CSS triangle.' See? It's simple."

"Sorry...what does CSS have to do with triangles?"

The chat logs usually come to an abrupt end at this point, or "CSS is simply how
you style your HTML."

*(I gathered from these exchanges that programmers have a perpetual competition
to see who can claim the most things as 'simple.')*

I left each conversation feeling extraordinarily incompetent.
Nevertheless I discovered how to make a triangle shape with a `div` (what's
that stand for?) and a few lines of CSS and found a few sites that had cool
color-changing effects that I could replicate for my triangle art.

I'm sure you're curious now what I could've possibly conjured up.

Well, here's a glimpse of the HTML:
{% highlight html %}
<div id="row1">
  <div class="btri"></div>
  <div class="tri"></div>
  <div class="tri"></div>
  <div class="tri"></div>
  <div class="emp"></div>
  <div class="tri"></div>
  <div class="tri"></div>
</div>
<div id="row2">
  <div class="tri"></div>
  <div class="tri"></div>
  <div class="tri"></div>
  <div class="tri"></div>
  <div class="tri"></div>

  ...
{% endhighlight %}

I am sad to report that this goes on for another **165** lines and that the
accompanying JavaScript is just as geometric--spoiler: *it's a parallelogram*.

I learned that there was this thing (library?) called jQuery and that I could
use this 'API' thing called 'animate' to change my triangles' various properties
gradually. I found that if I called `$('#something').animate({ 'opacity': '0' })`
once, it would make one triangle disappear. In my head it felt logical
that if I wanted my 20 rows of triangles to disappear one by one, I had to write
that same line 20 times.

I also 'imported' jQuery by copying and pasting the contents of the library to the
top of my JavaScript file. I had seen it in a separate file on others' webpages,
but I decided to keep all my JavaScript in one file for no particularly good
reason.

If I wanted to lie to myself, I could say that I chose the most optimal way to
code: in the *hard* fashion.
{% highlight javascript %}
$(".disappear").click(function(){
  $("#row20").animate({ "opacity": "0" },
    100,
    function(){$("#row19").animate({ "opacity": "0" },
      100,
      function(){$("#row18").animate({ "opacity": "0" },
        100,
        function(){$("#row17").animate({ "opacity": "0" },
          100,
          function(){$("#row16").animate({ "opacity": "0" },
            100,
            function(){$("#row15").animate({ "opacity": "0" },
              100,
              function(){$("#row14").animate({ "opacity": "0" },
                100,
                function(){$("#row13").animate({ "opacity": "0" },
                  100,
                  function(){$("#row12").animate({ "opacity": "0" },
                    100,
                    function(){$("#row11").animate({ "opacity": "0" },
                      100,
                      function(){$("#row10").animate({ "opacity": "0" },
                        100,
                        function(){$("#row9").animate({ "opacity": "0" },
                          100,
                          function(){$("#row8").animate({ "opacity": "0" },
                            100,
                            function(){$("#row7").animate({ "opacity": "0" },
                              100,
                              function(){$("#row6").animate({ "opacity": "0" },
                                100,
                                function(){$("#row5").animate({ "opacity": "0" },
                                  100,
                                  function(){$("#row4").animate({ "opacity": "0" },
                                    100,
                                    function(){$("#row3").animate({ "opacity": "0" },
                                      100,
                                      function(){$("#row2").animate({ "opacity": "0" },
                                        100,
                                        function(){$("#row1").animate({ "opacity": "0" },
                                          100)})})})})})})})})})})})})})})})})})})})
{% endhighlight %}

You can see the full source
[here](/assets/da.js) and the final product
[here](/assets/divart.html).

*(I even went through the trouble of indenting each callback properly, a
nontrivial feat in Windows Notepad.)*

Note that the Javascript ends with a flourish:
`)})})})})})})})})})})})})})})})})})})})`. At the time I was just glad that my
triangles were disappearing and reappearing as intended. The code itself was
like a magnificient ASCII waterfall or those Incan irrigation systems I often
saw in AP Spanish. It worked, and nothing I read on Google told me that things
were actually terribly wrong and that any programmer who read my code would
never let me nor my progeny near the web again.

By the first time a real software engineer took a look at my triangles code, I
had already read enough of SICP to realize that my code was something ghastly
and terrible. "But any beginner would make the same mistake, right?" I probed,
embarrassed.

"No, no programmer would do something like this." He was not sarcastic. I wanted to
switch back into Molecular and Cellular Biology right then. But then he added,
"No one would end up with code like this because they simply would not have had
the patience."

Whether or not he meant the second part, I felt a bit better about the whole
thing.

Regardless, at the time I buried my triangles in shame. As the days and months
passed, however, they have gradually become more of a silly icebreaker. "Hey,
you just spent 2 hours debugging a whitespace issue in your CoffeeScript? Take a
look at the time I spent a day writing 21 nested callbacks and 200 identical
lines of HTML." It usually generates some self-deprecating amusement.

I've realized that with each piece of code I've written since my triangles, I've
only gotten better at "Googling it," debugging, and being generally competent
about miscellaneous programming topics--and it's all because I saw each and
every silly project through.

I took the time last week to do a quick rewrite of my triangles. You can find it
[here](/assets/triangles.html), boasting responsiveness and all that dynamic
generation stuff I wasn't into back in the day (of course, I had to trade out
the obvious optimality of my previous implementation). I kept true to the
original spirit of using `div`s for my triangles and jQuery for animations.

Now that I am leaving the safe, tree-hugging walls of Berkeley for the real
world (and hopefully laying my past crimes against code to rest), I hope to
leave behind between one and three corners of the Triangles Legacy for budding
tinkerers and self-conscious makers.

**Programming is hard.** Don't ever feel bad because you aren't as good at 'just
googling it' as the person next to you. Don't ever let hackathon snobs talk you
out of creating the next Twitter for cats or Yelp for public washrooms. Even the
dumbest ideas (like trying to make animated polygons disappear and reappear)
will help you improve as a programmer. Learning to program is largely about
learning to learn--and the best way to learn is to *do*.

At the end of the day, being a competent programmar isn't about how many
hackathons you win or how many novel ideas you can come up with--it's about
execution, attention to detail, and relentless dedication and passion for
building and breaking.

And if you ever feel self-conscious about your code, I'll allow a laugh at my
expense at Triangles' 21 nested callbacks.


## Some links
- [The authentic, original beast.](http://hazelcough.zxq.net/divart.html)
- [The new triangles.](/assets/triangles.html)
- [Mirror of the original triangles.](/assets/divart.html)
- [Github repository.](https://github.com/michellebu/triangles)
- Edit: [HackerNews post.](https://news.ycombinator.com/item?id=5447287)
