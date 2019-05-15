---
layout: page
title: Meta
subtitle: This page is just here to keep track with all of the QoL things I've been adding to the site.
permalink: /meta/
---

## Known Issues.

* I need a better recipe system.
* TODO make a "Making of" post.


## Updates

### 5/15/2019

Added support for image galleries. New setup for images and videos using Bootstrap cards.

### 5/2/2019
Wow Bootstrap is awesome, I noticed the internals of this theme I have uses bootstrap for everything.
Still learning, but several things can be improved by learning about bootstrap.

* Videos now fixed on mobile.
* Better solution to the spoilers using bootstrap. This is awesome!

```
<button data-toggle="collapse" data-target="#hide-me">Hidden</button>

<div id="hide-me" class="collapse">
Boo
</div>
```

<button data-toggle="collapse" data-target="#hide-me">Hidden</button>

<div id="hide-me" class="collapse">
Boo
</div>

### 5/1/2019
Two weeks after starting this blog I finally had the foresight to add this page and document everything so far.
Just in case anyone wants to learn how to do something or the steps I took to create this...

### 4/28/2019
Disqus comment counts on main page works, very annoying and confusion attributed to the way the theme was setup.

Again more confusion on the baseurl _config.yml variable and now Search is working again.

### 4/27/2019
Fix image captions via 3 commits see this [stackoverflow](https://stackoverflow.com/questions/19331362/using-an-image-caption-in-markdown-jekyll) post.

[CSS](https://github.com/TricksterGuy/TricksterGuy.github.io/commit/cb77fa3f84b94e70f1d572b23110869f4970a758)
[Using figure/figcaption](https://github.com/TricksterGuy/TricksterGuy.github.io/commit/cb77fa3f84b94e70f1d572b23110869f4970a758)
[Image inliner for markdown](https://github.com/TricksterGuy/TricksterGuy.github.io/commit/dbd2d7d3f4133fbeb49315200d015b4ea13d6a5e)

### 4/23/2019
Bleh separated out projects from the main blog, I'll probably subdivide more as time passes.

First attempt at comment count icons on posts.

### 4/20/2019
Switched theme to [hcz-jekyll-blog](https://github.com/codeasashu/hcz-jekyll-blog) after looking at several themes.
Merged code with jekyll-now, did a recolor. Still some parts of this template I don't like seems a bit bloated in terms of code.
I spent the entire day theming and making stuff look actually presentable.

With this setup adding projects is a lot nicer, and a lot of cool stuff right out the box more geared towards a programmer's blog.

Just about the only thing I kept from jekyll-now was the icons at the bottom. And added steam account details.

### 4/19/2019
Added spoilers via the summary/details html constructs ugh was difficult see [picross puzzle exporter](https://github.com/TricksterGuy/TricksterGuy.github.io/blob/master/_posts/2019-4-16-project-picross-exporter.md)

Essentially the html code is quite weird to me.  You need that markdown=span part otherwise the markdown renderer will treat the inner contents as html or something.

```
<details><summary markdown="span">Title</summary>
Content
</details
```

Like this

<details><summary markdown="span">Click</summary>
Boo
</details>

### 4/18/2019
Added tagging and tag cloud via [this tutorial](http://longqian.me/2017/02/09/github-jekyll-tag/), playing around with stuff, adding projects.

### 4/17/2019
First version. I could have easily gotten this done quick with help from web dev clubs at Tech, but opted for toiling at it loses meaning otherwise.
 I used a template repo, there's plenty out there. The one I used was [jekyll-now](https://github.com/barryclark/jekyll-now).

Jekyll now is a pretty great starting point, comes with commenting via disqus and google analytics, setup was a breeze.

I had known just a little HTML/CSS enough to the point where I can hack things together or just google for answers, not a big web/front end person.
