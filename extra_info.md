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
not appear.  Here's an example:

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

<div data-lift="htag-list?depth=1">
    <div data-htag="root"><big><big>➥</big></big> <a href="#">Item</a></div>
</div>

-----------------


# `default_template`

Marks the current page as the default template to use -- FIXME

-----------------

# `template`

The template to use for the page.  `default` is the default template except for
blog posts which default to the `post` template. -- FIXME

-----------------

# `path`

The path to save the resulting file into.  -- FIME

-----------------

# `serve` 

`false` if you do not want the page served.  -- FIXME

-----------------

# `valid_from`

The date that the page is valid from.  The page will not be rendered
before the `valid_from` date.  If the `valid_from` date is in the future,
Telegram will schedule a rendering of the site within 15 minutes after the
`valid_from` value.

For example:

    valid_from: 2012-07-19 16:30

The page will not be displayed/rendered until 4:30PM on July 19, 2012.  The time zone
is based on the time zone of the user who owns the site.

-----------------

# `valid_to`

The date that the page is valid until.  The page will not be rendered
after the `valid_to` date.  If the `valid_to` date is in the future,
Telegram will schedule a rendering of the site within 15 minutes after the
`valid_to` value.

For example:

    valid_to: 2012-08-19 16:30

The page will be displayed/rendered until 4:30PM on August 19, 2012.  The time zone
is based on the time zone of the user who owns the site.

-----------------

# `title`
  
  
The title of the page.  --FIXME  Prepend  

-----------------

# `menu`

The menu name of the page -- FIXME


# `order`

The menu order -- FIXME

  
# `menu-locgroup`

The menu location group -- FIXME

# `menu-icon`

The menu icon CSS -- FIXME

# `menu-icon-placement`

The menu icon placement -- FIXME

-----------------  

# `site_link`

The global URL of the site -- FIXME

-----------------

# `type`

The type of the page -- FIXME

-----------------

# `template_url`

The URL of the Git repository that has the template for this site.  Global param.  -- FIXME

-----------------


# `site_title`

The title of the site.  Global.  -- FIXME

-----------------

# `post`

Is the page a blog post?  If so:

    post: true
    
Also, if the page is located in the `_posts` directory, it will be considered
a blog post. -- FIXME

-----------------

# `event`

Is the page an event?  FIXME

-----------------

# `category`

What's the category of the page? -- FIXME

-----------------

# `layout`

What layout do we use? -- FIXME

-----------------

# `date`

The date of the blog post. -- FIXME

-----------------

# `blog_root`

The site-wide root for all blog posts. -- FIXME

-----------------

# `has_blog`

Does the site have blog posts? -- FIXME

-----------------

# `tag`

Tags for a page:

    tag: {foo, bar, baz}

FIXME

-----------------

# `site_author`

The site wide name of the authors of blog posts. Used for RSS feed generation.  FIXME


# `author`

The author of a blog post for RSS feed purposes.  FIXME

-----------------

# `redirect`

Used for faux-pages that are menu items.  The page is not actually rendered,
but it does have a menu item that points to an external site:

    redirect: http://github.com/lift/framework
    name: source
    menu: Source
    order: 8
    
    <div>Nothing to see here</div>



-----------------

# `alias`

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

# `no_synthetic_rss_file`

A site-wide Extra Info parameter.  By default, if there are any pages
marked as blog posts, Telegram will generate a synthetic `rss.xml` file
and insert `<link type="application/rss+xml" rel="alternate" href="/rss.xml">`
in the `<head>` of every page.

By setting:

    no_synthetic_rss_file: true

The synthetic RSS feed will not be generated.

-----------------

# `h_tags`

A list of all `<h*>` tags found at the top level of the content of the page. -- FIXME


# `h_tag_level`

For a single `<h*>` tag, what's the level? -- FIXME


# `h_tag_id`

For a single `<h*>` tag, what's the id? -- FIXME


# `h_tag_body`

For a single `<h*>` tag, what's the body? -- FIXME

