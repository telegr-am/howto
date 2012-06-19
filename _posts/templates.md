# Telegram Blog

## Telegram "extra info" and Templates, June 11, 2012

Each Telegram page may contain extra info.  Extra info is information about
either the page or the whole Telegram site, but it is not displayed on the page.

You can define extra info by placing colon-separated values at the top of
the page.  For example:

    title: My Fun Page
    date: 2012/08/14
    
    # This is my page
    
    Blah blah blah 

You can separate the extra info with an optional line of dashes:

    ----------
    title: My Fun Page
    date: 2012/08/14
    ----------
    
    # This is my page
    
    blah blah blah
    
You can also include the extra info as Markdown references.  This format makes
the page look prettier in Markdown preview mode:

    # This is my page
    
    [title=My Fun Page]: /
    
    blah blah blah
    
    [date: 2012/08/14]: /
   
Telegram (based on [Hoisted](http://hoisted.org)) currently supports the following
extra info:

* `template_url`: The template to use to render the site.  This value
  is the public URL of a Git directory that houses the template.  For example:   
  `template_url: https://github.com/telegr-am/template-base.git`   
  Which points the base Telegram template.  You can point Telegram to your
  template by hosting your template in a public [GitHub](http://github.com)
  repository.  You can fork the default template.  This extra info is global
  to the whole site.
* `path`: The place to put the current file.  For example:   
  `path: /my_info/about`   
* `serve`: Should the current file be placed on the web site?  For example:   
  `serve: false`
* `valid_from`: The date the the file is valid from.  Before the date,
  the page will not be served.  For example:   
  `valid_from: 2012/06/20`
* `valid_to`: The date the the file is valid to.  After the date,
  the page will not be served.  For example:   
  `valid_to: 2012/06/28 14:45`
* `title`: The title of the page.  For example:   
  `title: David's wicked cool stuff!`
* `menu`: The entry in the menu for this page (if this is not
  specified, the filename will be used):   
  `menu: Special Sauce`
* `order`: The order of the page in the menu (sorted by number so
  having a gap in the numbers lets you insert a menu entry between others):   
  `order: 200`
* `site_title`: The name of your site (this is global to the whole site, so
  you only have tp put it in one file):   
  `site_title: Dpp's amazing stuff`
* `post`: Is this a blog post (it will be treated specially… also files in the
  `_posts` directory are automatically considered blog posts):   
  `post: true`
* `event`: Is the page an event (events are treated specially… also, files in the
  `_events` directory are automatically considered events):   
  `event: true`
* `blog_root`: The root directory where all blog posts will be output:   
  `blog_root: /blog`

You can create your own template by forking `https://github.com/telegr-am/template-base`
and then changing the template and pointing your Telegram site to your new
public Git repository with the `template_url` directive.  The file that defines
the template is `/templates-hidden/default.html`.  Just edit that file.  It contains
Lift snippet invocations (which I will document in a few days).

Hope this gets you started.

Rock and roll!

-- David

[title: Templates and Extra Info]: /
[category: Tech]: /
[date: 2012/06/11]: /
[tags: {templates, tech}]: /