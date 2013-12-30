---
title: Rebooting Blog with Middleman
date: 2013-12-30 14:17 UTC
tags:
---

OK, it seems working.

I used to blog in Japanese but recently decided to go with English so that my non-Japanese friends can read my writing. Actually there is little drawback to do that as most of my Japanese friends can read English.

At first I thought I can continue using [Octopress](http://octopress.org/) as my blogging tool.
Then I heard [Middleman](http://middlemanapp.com/) could be better. So let's give it a try. 
My first impression: This is better, maybe?

Some points here.

## Pros (1): Active development

Middleman is [under active development](https://github.com/middleman/middleman/commits/master) and [released constantly](http://rubygems.org/gems/middleman).
This kind of vitality is a signal of good project. 

It isn't fair to say that Octopress is an inactive project when you see its [commit rate](https://github.com/imathis/octopress/commits/master),
but its release cycle is barely predictable and it's even hard to understand the versioning.

See there is a branch called [3.0-stable](https://github.com/middleman/middleman/commits/3.0-stable) but
its last commit happened more than half a year ago and current master stays on 2.x or something. Pretty confusing.

[The documentation](http://octopress.org/docs/setup/) seems recommending forking from the master.
I prefer to rely on something a bit more stable, even though I kinda agree that it's a hacker way to be on the latest master.

## Pros (2): Flexibility

Although I haven't taken deeper look, the architecture of Middleman looks more flexible and modular than ones of Octopress and Jekyll.

One strong signal of the modularity is [existing set of extensions](https://github.com/middleman). There are not only "official" extensions
hosted under [github.com/middleman](https://github.com/middleman), but are also unofficial, third-party extensions like 
[middleman-s3_sync](https://github.com/fredjean/middleman-s3_sync) which I'm using.
This implies that Middleman's extensibility. I don't see same level of ecosystem around Octopress nor Jekyll.

I can't explain the reasoning of this difference clearly. However it seems like Middleman is modeled after Ruby web frameworks like Rails and [Rack](https://github.com/rack/rack) - 
Its [config.rb](http://middlemanapp.com/advanced/configuration/) has a block-driven DSL that resembles style of these frameworks. Probably this kind of design philosophy helps here.

## Pros (3): Generate not Fork

Middleman generates the site stub via `middleman init` command. Octopress requires user to fork its repository as a stub. This might be more about taste, but I prefer Middleman's clear separation between tool and content. It'll be easier to update the tool version. In Octopress, sometimes I need to resolve conficts when I upgrade the tool (by `git pull`-ing upstream.) 

## Cons (1): Lack of (Visual) Design

Let's change the turn.

Octopress comes with well-designed template.
Many people actually use it as is, but it is customizable as well.
The customization is relatively easy thanks for its well written SASS-based stylesheet in which you can just modify a few variables.
I did it before ([1](http://tale.wkb.ug/), [2](http://steps.dodgson.org/)) and that was fun.

Middleman and its blog extension don't have any default theme. You have to make it for yourself.
I'm doing it, and I believe my SASS skill is horrible. Fortunately, blogs don't need any sophisticated styling
if you keep the site simple. We can live with it.

Also, I confess that I learned some stylesheet tips from Octopress :-)

## Cons (2): Lack of Features

Octopress has many built-in blogging modules like social buttons, comments, Twitter integration and so on.
Middleman has few, even though there are certain number of extensions.
On the other hand, I disabled most of these modules on my Octopress blogs. 
I used one or two so had to redo them for Middleman - It took just about an hour. Not bad.

One non-trivial feature I need is code syntax coloring. 
Fortunately, [middleman-syntax](https://github.com/middleman/middleman-syntax) does it for me.

```ruby
def hello
  p 'Hello, World!' # With colors!!
end
```

## Extensibility vs. Rich built-ins

So here is a bottom-line: 
Octopress has rich built-in design and features but is weak on extensibility.
Middleman provides no visual and is bare-bone in terms of the default feature set but it is extensible and has many extensions. You can choose whichever you want.

Personally speaking, I like both. Octopress told me the beauty of static site generator as a easy-starter.
It's time to go beyond that though - With Middleman, I can now pick only what I want, that is bare minimum and thus doable.

Anyway.

Talking about tools is always fun, but real fun of blogging should come from elsewhere rather than underlying tool.
Let's do it ... Well, do it next time.
