title:	How To


# Telegram How To...

Telegram sites are rendered using [Hoisted](http://hoisted.org) to convert
the HTML, XML, and Markdown files into a bunch of HTML files
that make up a coherent whole web site.

These pages are here to answer questions and help you make the most of Telegram.

## Recipes

* [Change the page footer](/recipes/change_footer)
* [Change the template](/recipes/change_template)
* [Add a Twitter Feed](/recipes/add_twitter_feed)
* [Host a custom domain](/recipes/custom_domain)


## Screencasts

* [Telegram and Dropbox](/intro_db)
* [Telegram and GitHub](/intro_gh)
* [Migrate to Telegram from Posterous](/migrate_posterous)


## Core Concepts

There are a series of core concepts in the way Hoisted/Telegram works:

* [Site Body](/site_body) The collection of documents that make up the site
* [Extra Info](/extra_info) is data contained in a document, but it's not
  displayed to the user (although Extra Info can change the way a page
  is displayed.)  Extra Info may also be called Metadata or Properties.
* [Templates](/templates) Templates define how a site looks… the stuff that goes
  on every page like menus, links to the CSS style and such.  Hoisted and
  Telegram allow templates to be included in the site body or external to
  the site body.
* [Snippets](/snippets) HTML pages are made up of [DOM](http://en.wikipedia.org/wiki/Document_Object_Model)
  which is manipulated and re-written based on program rules.  The rules for re-writing DOM elements
  based on data external to the page are called snippets.  Snippets include rewriting the `<title>` 
  tag to insert the title of a page or writing out menu items.
* [CSS Transforms](/transforms) Rules for transforming DOM elements based on selecting the elements
  based on a subset of [CSS Selectors](http://www.w3.org/TR/CSS2/selector.html) and then
  modifying the DOM elements.
  
This site is hosted in a GitHub [Repository](https://github.com/telegr-am/howto).  We
encourage you to [fork](https://help.github.com/articles/fork-a-repo) this repository,
enhance the documentation and create a [pull request](https://help.github.com/articles/using-pull-requests/)
with the enhanced documentation.


