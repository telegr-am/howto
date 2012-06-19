## Welcome to Telegram June 9, 2012

Wow!

So, there was a confluence of events:

* Posterous got bought by Twitter and it seems like there's not
  going to be a lot of work done on Posterous and it might even
  get shut down.  I needed to find a new blog hosting site.
* I was working on [Visi](http://visi.io) and
  [Dean Wampler](http://twitter.com/#!/deanwampler) suggested that 
  Visi documents should be literate and be written in Markdown.  I
  started researching Markdown… and I fell in love with Markdown.
* [Jordan West](https://twitter.com/#!/_jrwest) turned me on to
  [Jekyll](http://jekyllbootstrap.com/) and [Octopress](http://octopress.org/).
  Then I discovered the likes of [Calepin](http://calepin.co/) and
  [Scriptogr.am](http://scriptogr.am/).  All of these offer variations
  of "save to content repository and publish a blog" theme.
* I hit a mental roadblock while developing Visi's type system.
* I needed a "win" to help me get my Visi mojo back.

With all those factors and with the [Hoisted](http://hoisted.org)
system that I built for generating the [Lift](http://liftweb.net)
web site, I figured I could put together a simple blogging system
out of GitHub.

Then I started thinking some more (always a dangerous thing).

### David thinks about CMS

The whole Content Management System thing is broken.

For a while, CMS was [Interwoven](http://interwoven.com/)… basically
version control and a web back end.

Then came the likes of [Wordpress](http://wordpress.org) and 
[Drupal](http://drupal.org/) where the content management was done via
a web interface.  The storage was in MySQL and the stuff was published to
the web via PHP.

It was necessary to dynamically create pages before all the excellent
JavaScript stuff was available, but these days, half of the pages you
see have content fetched from other services after the page is delivered
to the browser… think about Twitter feeds and Google maps and the like.

### Bunking with [StackMob](http://stackmob.com)

I rent my office from the folks at [StackMob](http://stackmob.com) and 
they are amazing.  They have some awesome Html5 backend tools that allow
adding dynamic, interactive features to static Html5 sites.  It's amazing stuff.

So, it's possible to build really amazing web sites that are served as
static Html5 pages and backed by the likes of Twitter and StackMob, etc.

### Better content repositories

[GitHub](http://github.com) changed my life. It's simply the best way
to store and manage all forms of content.  It's wicked powerful.  There
are tons of nice workflow tools like pull requests and such.  For
medium to large teams of tech-savvy folks, Git and GitHub are the
best way to manage content… assets.

[Dropbox](http://dropbox.com) is a great way for an individual or
small team.  Dropbox is drop-dead simple for managing files (content
assets) across multiple machines.

Oh… and Git and Dropbox stuff travels on your device with you… so
you can edit stuff on an airplane or anywhere else.
And on any device like the iPad with [Writing Kit](http://getwritingkit.com/).

So, Content Management Systems no longer have to be content repositories…
that job is better done by GitHub or Dropbox.

Given that static is the new dynamic and content repositories
are handled… what's left for CMS?

### What's left for CMS

There are two things that are left for CMS systems to focus on:

* Ease of use
* Beautiful, Simple, Powerful Templates

Telegram is about those two things.

Using Markdown, it's easy for people to write HTML content.  They
write it, save it, and it gets published.  [Sean Heywood](http://about.me/seanheywood)
has a bunch of excellent thoughts on ease of use and
on messaging about ease of use.  We've got some work to do
on auto-generated templates, video tutorials, and other
ways to help people build simple web sites, complex web sites,
blogs, etc.

Beautiful templates are doable.  [Joy Reyes](http://www.joyreyes.com/ver5/)
did the design for Telegram and is working on a bunch of other templates.
But anyone can build a template for a Telegram site.  Just put it in a
public Git repository like the
[default template](https://github.com/telegr-am/template-base).

Simple… this is a work-in-progress.  [Hoisted](http://hoisted.org) is the
mechanism that weaves pages together.  As of today (June 9, 2012), Hoisted
barely gets the job done.  But there's lots of stuff I have in mind
to make it easy to perform common tasks like saving a file in the
"events" folder and have the events show up on every page, in order.
But at the end of the day, I'm going to be working with users to
figure out the common tasks for different classes of sites and make
it darned simple for someone to write a text file, save it and have
it show up in the right places on the web site.

Powerful means getting the kinds of things done that users
want to get done.  Learning about those things and making the
path to those things short and easy to understand.

The nice thing about Hoisted is it's open source and working with the
community (well, building a community and then working with it) to
improve Hoisted and creating plugins to Hoisted to allow for manipulation
of all kinds of content.

### What about serving those pages?

Serving static pages is super-easy with [Nginx](http://nginx.org/en/) and
[AWS](http://aws.amazon.com/).  Between those two systems, static content
can be served at inconceivably large scales in geographically disparate
locations.  That's an easy one.

### Show me the money

Lots of web businesses have "challenging" business models.

Some sites (like Posterous) have a "give it away for free and we'll
figure out how to make money" approach.

Other sites, like [GoDaddy](http://www.godaddy.com/hosting/website-builder.aspx)
have junky pricing, but at least they make money.

So, where's the middle-ground… pricing that reflects use levels,
offering no-cost entry-level use, but for larger sites (asset-size combined
with bandwidth), there's a cost.  Plus, if there's special needs (high
availability, geographic location, etc.), there's additional costs.

What I came up with is an account that starts with a certain balance (e.g., $25) and
money gets added to the account each month (e.g., $1).  But Telegram charges for
storage and bandwidth (stuff that costs us money.)  For small sites, there's no
net cost.  For sites that have traffic spikes, there's no cost.  For larger
sites, there'll be monthly charges.

More importantly, the pricing is fair.  It means that you don't have to shell out
$5/mo or some-such just in case you have a volume spike.

### Please use Telegram and give us feedback

So, today's launch-day for Telegram.  It's the beginning of a long
path to build something cool and redefine how people build and publish
web sites.

Please give Telegram a spin, give us some feedback.

If you want to create a template, fork [the default template](https://github.com/telegr-am/template-base) and let us know about it.

If you want to enhance [Hoisted](https://github.com/hoisted/hoisted), send us a pull request.

Looking forward to a lot of fun with Telegram!

Thanks!

-- David Pollak

-----------

PS -- One of the secret little plots for Telegram is to put Markdown
in the hands of lots and lots of people.  Visi models are written in Markdown.
Telegram is a way to put Markdown into the hands of lots and lots of people.
As Visi becomes useable, it's a simple way to integrate Visi into Telegram.

PPS -- Many of the pieces of Telegram are open source.  You're not locked into
Telegram.  Everything we're doing with Telegram, you can do yourself with
Hoisted.  So, you own your files, you can render them into HTML via Hoisted
the same way Telegram does.  The value in Telegram is that we're doing
all integration.  The value is the integrated whole, not the individual pieces.

[title: Hello World]: /
[category: Business]: /
[date: 2012/06/09]: /
[tags: {welcome}]: /
