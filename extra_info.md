## Extra Info

Pages contain content, but they also contain Extra Information
about the content.  Extra Information includes stuff like the
title of the page, name and menu information for the page,
the path to render the page out to, etc.

Extra Info can be defined as follows:

#### Markdown 

In Markdown documents, Extra Info can appear at the top of the page:

    title: I like wombats
    menu: Wombats

    This is a page about wombats… but the extra info above will not
    appear on the page

Markdown documents can also use Refs for extra info.  The advantage to using
refs is that if you're using an editor with preview, the extra info will
not appear.  

One thing to note here. If you omit the trailing /, you may find the extra info starts appearing on your page. Play it safe, and always include the trailing / if your using the ref style.

Here's an example:

    [title: I like wombats]:/ 
    [menu: Wombats]: /

    This is a page about wombats… but the extra info above will not
    appear on the page

#### HTML 

In HTML documents, Extra Info can appear at the top of the page:

    title: I like wombats
    menu: Wombats

    <h1>Wombats</h1>
    
    <p>Wombats are creatures that are much maligned in computer documentation.</div>

#### XML 

In XML documents, Extra Info appears in `<tag>` elements:

    <cms path="/community" serve="true" type="html" locale="en_US" host="liftweb.net">
      <tag name="name" value="community"/>
      <tag name="menu" value="Community"/>
      <tag name="order" value="5"/>
      <content>
        <h1>Wombats</h1>
        
        <p>Wombats are creatures that are much maligned in computer documentation.</div>

#### Word and RTF

In Word and RTF documents, Extra Info is stored as document properties.

-----------------

Available Extra Info:

<div data-lift="htag-list?depth=2">
    <div data-htag="root"><big><big>➥</big></big> <a href="#">Item</a></div>
</div>

-----------------
# Global/Site Related Extra Info

## `global-locale` `-- Override the locale` ##

By default, Telegram uses the locale defined in the user profile for parsing and formatting
dates and other locale-related stuff.

You can set the locale for the site by putting the following Extra Info into a file on your site:

    global-locale: en_US

The valid locales are based on the locales in the [Java Locale class](http://docs.oracle.com/javase/7/docs/api/java/util/Locale.html).

## `global-timezone` `-- Override the time zone` ##

By default, Telegram uses the time zone defined in the user profile for parsing and formatting
dates and other time-related stuff.

You can set the time zone for the site by putting the following Extra Info into a file on your site:

    global-timezone: EST

The valid time zones can be found in the [Joda Time library](http://joda-time.sourceforge.net/timezones.html).

## `date-format`

A global extra info that defines the way to format dates for display on Telegram site.
Dates will have the time zone of the site owner and the locale of the site owner.  For
example:

    date-format: dd MMMM, yy


More information on how to define the date format can be found in the [Joda Time](http://joda-time.sourceforge.net/apidocs/org/joda/time/format/DateTimeFormat.html)
documentation.



## `site_link`

The global URL of the site -- FIXME

-----------------

## `template_url`

The URL of the Git repository that has the template for this site.  Global param.  -- FIXME

-----------------


## `site_title`

The title of the site.  Global.  -- FIXME

## `blog_root`

The site-wide root for all blog posts. -- FIXME


-----------------


## `no_synthetic_rss_file`

A site-wide Extra Info parameter.  By default, if there are any pages
marked as blog posts, Telegram will generate a synthetic `rss.xml` file
and insert `<link type="application/rss+xml" rel="alternate" href="/rss.xml">`
in the `<head>` of every page.

By setting:

    no_synthetic_rss_file: true

The synthetic RSS feed will not be generated.

## `rss_url` -- Support for Feedburner and other URL aggregation services ##

A site-wide Extra Info parameter. By default, the `<link>` generated for the RSS feed looks like:

    <link type="application/rss+xml" rel="alternate" href="/rss.xml">

But if you're using Feedburner or some other service, you want to change the `href` attribute
in the `<link>` tag. Use:

    rss_url: http://feeds.feedburner.com/dppsblog

And the RSS `<link>` will be written:

    <link type="application/rss+xml" rel="alternate" href="http://feeds.feedburner.com/dppsblog">


-----------------


#  Page Extra Info

## `default_template`

Marks the current page as the default template to use -- FIXME

-----------------

## `template`

The template to use for the page.  `default` is the default template except for
blog posts which default to the `post` template. -- FIXME

-----------------

## `path`

The path to save the resulting file into.  -- FIME

-----------------

## `serve` 

`false` if you do not want the page served.  -- FIXME

-----------------

## `valid_from`

The date that the page is valid from.  The page will not be rendered
before the `valid_from` date.  If the `valid_from` date is in the future,
Telegram will schedule a rendering of the site within 15 minutes after the
`valid_from` value.

For example:

    valid_from: 2012-07-19 16:30

The page will not be displayed/rendered until 4:30PM on July 19, 2012.  The time zone
is based on the time zone of the user who owns the site.

-----------------

## `valid_to`

The date that the page is valid until.  The page will not be rendered
after the `valid_to` date.  If the `valid_to` date is in the future,
Telegram will schedule a rendering of the site within 15 minutes after the
`valid_to` value.

For example:

    valid_to: 2012-08-19 16:30

The page will be displayed/rendered until 4:30PM on August 19, 2012.  The time zone
is based on the time zone of the user who owns the site.

-----------------

## `show-if` `hide-if`

Conditionally show or hide the page based on other extra info values.  For example,
show the "Blog Archive" page if there are blog posts:

    show-if: has_blog


-----------------------------


## `title`
  
  
The title of the page. This is what will appear in the titlebar/tab of the user's browser. --FIXME  


-----------------

## `menu`

For a page, this is the description that appears in the menu. If not provided, the menu item will appear as the page name with '-'s removed, and each word capitalized.
 

## `order`

A number to determine the order of pages in the menu. Higher numbers appear to the left of lower numbers. If two items have the same number, they are sorted alphabetically.

  
## `menu-locgroup`

The menu location group -- FIXME

## `menu-icon`

The menu icon CSS -- FIXME

## `menu-icon-placement`

The menu icon placement -- FIXME

-----------------
## `type`

The type of the page -- FIXME


## `post`

Is the page a blog post?  If so:

    post: true
    
Also, if the page is located in the `_posts` directory, it will be considered
a blog post. -- FIXME

-----------------

## `event`

Is the page an event?  FIXME

-----------------

## `article`

Is the page an article?  FIXME


-----------------

## `category`

What's the category of the page? -- FIXME

-----------------

## `layout`

What layout do we use? -- FIXME

-----------------

## `date`

The date of the blog post. -- FIXME

-----------------

## `has_blog`

Does the site have blog posts? -- FIXME

-----------------

## `tag`

Tags for a page:

    tag: {foo, bar, baz}

FIXME

-----------------

## `site_author`

The site wide name of the authors of blog posts. Used for RSS feed generation.  FIXME


## `author`

The author of a blog post for RSS feed purposes.  FIXME

-----------------

## `redirect`

Used for faux-pages that are menu items.  The page is not actually rendered,
but it does have a menu item that points to an external site:

    redirect: http://github.com/lift/framework
    name: source
    menu: Source
    order: 8
    
    <div>Nothing to see here</div>



-----------------

## `alias`

Create aliases to this page.  Useful if you're migrating your blog from another service
to Telegram:

    title: My Blog Post
    alias: /posts/my_blog_post.html
    alias: /posts/my_blog_post
    path: /my_post
    date: 2012-07-20
    
    Here's my blog post

On Telegram, the blog post will have the URL `/my_post`, but the page will also be 
served for requests to `/posts/my_blog_post.html` and `/posts/my_blog_post`.

-----------------


## `h_tags`

A list of all `<h*>` tags found at the top level of the content of the page. -- FIXME


## `h_tag_level`

For a single `<h*>` tag, what's the level? -- FIXME


## `h_tag_id`

For a single `<h*>` tag, what's the id? -- FIXME


## `h_tag_body`

For a single `<h*>` tag, what's the body? -- FIXME


Here's an example of creating a table of contents that will only show the top-level header items. The content in the div with a data-htag="root" attribute is the code that will render for each item. Telegram will replace the &lt;a href="#"&gt;Item&lt;/a&gt; with a link to the header item, and it's text.

<pre>
	&lt;div data-lift="htag-list?depth=1"&gt;
    	&lt;div data-htag="root"&gt;&lt;big&gt;&lt;big&gt;➥&lt;/big&gt;&lt;/big&gt; &lt;a href="#"&gt;Item&lt;&lt;/a&gt;&lt;/div&gt;
	&lt;/div&gt;
</pre>
