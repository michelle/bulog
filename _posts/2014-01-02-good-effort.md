---
layout: post
title: Good effort, 2013
---

I wanted CSS clouds for <a href="http://happinessjar.com">Happiness Jar</a>. I
wanted them to do all this fancy parallax scrolling stuff and be dynamically
generated and all that.

If I could only do some simple maths and calculate the
intersection of each circle with a midline given a range of radii and a
configurable width/height limit and fill in spaces that I detect given a circle
is too small and too high up from the midline, I could generate brilliant clouds
that would look good even as squares in IE...and then I could open source it and
everyone will have pretty parallax clouds and maybe, just maybe I'll hit 200
Github followers before the new year!

I ended up hardcoding them:

{% highlight html %}
<div class="snow front">
  <div class="clump">
    <div class="one"></div>
    <div class="two"></div>
    <div class="three"></div>
    <div class="four"></div>
    <div class="five"></div>
    ...
    ...
  </div>
</div>
{% endhighlight %}

Sorry folks, I only innovate on the second Friday of every month.

(Though it's a bit reminiscent of the HTML from <a
href="http://blog.michellebu.com/2013/03/21-nested-callbacks/">this</a>. Perhaps
I've found my style.)
