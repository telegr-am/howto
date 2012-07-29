## Snippets

Snippets execute computer code that rewrites the DOM elements
in a section of the page (or in some cases on the who page.)

Snippets are invoked via the `data-lift` attribute on an HTML
element.  For example:

    <div data-lift="ignore">This div will not be displayed</div>
    
Parameters can be passed to a snippet using URL syntax:

    <div data-lift="twitter?user=dpp&rpp=6"></div>

Which will invoke the Twitter snippet and insert a Twitter feed for user `app`
onto the page with the 6 more recent Twitter posts.

-----------------

Available snippets:

<div data-lift="htag-list?depth=1">
    <div data-htag="root"><big><big>➥</big></big> <a href="#">Item</a></div>
</div>

-------------

# `blog.simple` -- Display blog posts to fixed template

Just display the most recent 15 blog posts in a fixed template.  For example:

    <div data-lift="blog.simple"></div>

-----------------

# `blog.posts` -- Display blog posts

Take all the pages on the site marked as blog posts and
bind the information about them into the places in the template.

For example:

    <ul data-lift="blog.posts?max=15">
        <li data-post="item">
            <h2><a data-post="link" href="#">Blog Post</a></h2>
        	<h4><span data-post="date">2012/12/14</span></h4>
        	<div data-post="shortcontent">Post Content goes here</div>
        	<div data-post="more"><a href="#">Read More...</a></div>
        </li>
    </ul>

#### Parameter: `max` -- number of posts

The maximum number of blog posts to display.  If omitted, all blog posts
are listed.

#### Bind: `data-post="item"` -- the DOM to bind a post to

The DOM element that each post will be bound to.  For each blog post,
an instance of this DOM will be generated.

#### Bind: `data-post="link"` -- the DOM put the link information in

The `href` attribute of this element will be set to the link to the blog post
and the body of this element will be set to the title of the blog post.

#### Bind: `data-post="date"` -- the date of the blog post

The date of the blog post will be put in the body of this element

#### Bind: `data-post="shortcontent"` -- the DOM put the link information in

The short content (about 700 characters) will be placed in the body of this element.

#### Bind: `data-post="more"` -- the DOM put the link information in

If the short content was truncated, the DOM node with the `data-post="more"`
attribute will be displayed.  Any `<a>` tag inside the `data-post="more"`
DOM node will have its `href` attribute set to a link to the blog post.

-----------------

# `twitter` -- Insert a Twitter feed into the page

Insert a Twitter feed onto the page.

For example:

    <div lift-data="twitter?user=dpp></div>
    
#### Parameter: `user` -- The ID of the Twitter user

The ID of the Twitter user for the feed.  If not provided, will default
to "_telegram".

#### Parameter: `rpp` -- number of posts

Number of items to show in the feed.  Default = 4.

#### Parameter: `interval` -- Update interval

How frequently to update the feed, in milliseconds.  Default = 30000.


#### Parameter: `height` -- The height of the control on the page

The height of the control on the page.  Default = 300.

#### Parameter: `shell-background` -- Background color for display shell

Background color for the display shell.  Default `#bfbfbf`


#### Parameter: `shell-color` -- Color of the display shell

The color of the display shell.  Default `#000000`

#### Parameter: `tweets-background` -- Background color for Tweets

The background color for Tweets.  Default `#ffffff`

#### Parameter: `tweets-color` -- Color for Tweets

The text color for Tweets.  Default `#000000`

-----------------


# `search` -- Insert a search box

Insert a Google search box that will search just this site:

    <form data-lift="search" style="float: right"></form>
    
-----------------

# `if` -- Conditionally include DOM element

Test an attribute and display the DOM if the attribute or extra info exists and is `true`.

To test if an attribute exists and it `true`:

    <div data-lift="if?toTest=foobar">
      Yes, foobar is defined!
    </div>
    
To test is Extra Info exists (the value is defined, does not test the value):

    <div data-lift="if?extra=author">
      The page has an author: <span data-lift="page_info?name=author">Author name here</span>
    </div>

To test is Extra Info exists and the value is true:

    <div data-lift="if?extra_true=has_blog">
      <div data-lift="blog.simple"></div>
    </div>

To test is Extra Info exists and the value equals another String:

    <div data-lift="if?extra_eq=author&value=david+pollak">
      A blog post by David Pollak, yay!
    </div>

 
    

-----------------

# `move_top` -- Rearrange the top of the page

Sometimes you want stuff in a part of the page template, but
it's part of the main page and you want to re-write the page such
that stuff at the top of your content page is moved to a part of the template.

For example, if your template has a `page_header` `<div>` like:

    <div class="page-header" id="page_header">
	  <!-- if you've got a header, put it here -->
    </div>

And the top of your content looks like:

    <div id="left_side">
    <div class="hero-unit">
    	<h1><a href="https://twitter.com/dpp">David Pollak</a>'s blog... <small>and such.</small></h1>
    	Lots of DPP's thoughts here...
    </div>
    …
    </div>


Or:

    <div id="left_side">
    <h1>This is my page, dude</h1>
    <p>Stuff</p>
    </div>

Then `move_top` will rewrite as such:

    <div class="content" data-lift="move_top?from=left_side&to=page_header">
      <div class="page-header" id="page_header">
	    <!-- if you've got a header, put it here -->
      </div>
    
      <div id="left_side">
        <h1>This is my page, dude</h1>
        <p>Stuff</p>
      </div>
    </div>

To:

    <div class="content">
      <div class="page-header" id="page_header">
	    <h1>This is my page, dude</h1>
      </div>
    
      <div id="left_side">
        <p>Stuff</p>
      </div>
    </div>

`move_top` looks at the first Element in the `from` DOM element
and if it's a header tag (e.g., `<h1>`, `<h2>`, etc.) or it
has the CSS class `page-header` or `hero-unit`,
it will be removed from the `from` DOM and inserted into the `to`
DOM.

-----------------

# `head` -- Move the block to the `<head>` second of the page

Put additional markup in the `<head>` section of the HTML markup.

Useful to include external resources such as style sheets.

For example:

     <link data-lift="head" rel="stylesheet" href="/css/custom-theme/jquery-ui-1.8.16.custom.css" type="text/css">

-----------------

# `tail` -- Move the block to the bottom of the page

Put additional markup at the end of the `<body>` section of the HTML markup.

Useful to put scripts on the bottom of the page so the page loads faster.

For example:

    <script data-lift="tail" type="text/javascript">
      alert("The page is loaded");
    </script>

-----------------


# `disqus` -- insert a Disqus forum

Inserts a [Disqus](http://disqus.com/) forum on the page.

#### Parameter: `shortname` -- the name of the forum

For example, in the `/templates-hidden/post_include.html` add the line:

    <span data-lift="xform" data-css="#after-content *">
      <span data-lift="disqus?shortname=dppblog"></span>
    </span>

The outer `xform` puts the inner span under the blog post on your page.  The
inner `disqus` inserts the correct JavaScript on the page to show the
Disqus comments for that page.

    
#  `disqus.count` -- number of posts for each link

For each link to a blog post, list the number of comments near the link.

#### Parameter: `shortname` -- the name of the forum

For example, in the `/index.md` file, include the line:
    
    <span data-lift="disqus.count?shortname=dppblog"></span>

    
-----------------

# `google.map` -- Insert a Google Map

Insert a Google Map on the page at the location of the snippet.

For example:

    My office is located at:
    
    <div data-lift="google.map" data-address="541 8th St, San Francisco, CA">
    </div>
    
#### Parameter: `width` -- the width of the display box

#### Parameter: `height` -- the height of the display box

#### Attribute: `data-address` -- the address to map

<div data-lift="google.map" data-address="541 8th St, San Francisco, CA">
</div>

----------------

# `htag-list` or `htag_list` -- List all the H-tags on the page



", "render") -> Full(BaseSnippets.hTags),

-----------------

# `bootstraputil.headcomment` -- Insert a comment for Bootstrap

[Twitter Bootstrap](http://twitter.github.com/bootstrap/) requires
some special comments on the page to work nicely with Internet
Explorer.  Insert the special comment into the `<head>` section of the page

-----------------

# `bootstraputil.bodycomment` -- Insert a comment for Bootstrap

[Twitter Bootstrap](http://twitter.github.com/bootstrap/) requires
some special comments on the page to work nicely with Internet
Explorer.  Insert the special comment into the `<body>` section of the page

-----------------

# `title` -- Set the title of the page to the contents of the DOM node

Compute the text of the 

    <div data-lift="title">Post :: <div data-lift="menu.title">something</div></div>

Becomes:

    <title>Post :: Playing with Telegram</title>
    
And gets placed in the `<head>` section of the HTML page.



-----------------

# `ignore` -- Ignore the block

Do not include the HTML in the rendered output.  For example:

    <div data-lift="ignore">
      I will not be included in the resulting page
    </div>

Useful for having a comment in the markup as part of a work-in-progress.

-----------------

# `site.name` -- Insert the site name

Compute the site name via the `site_title` [Extra Info](/extra_info)
and insert the value into the contents of the DOM node.  For example:

    <div data-lift="site.name" class="fruit_bat">Title Goes Here</div>

Becomes:

    <div class="fruit_bat">David's Blog</div>


-----------------

# `surround` Put a template around the DOM nodes

Surrounds the DOM elements with a template.  This snippet is
generally used to put "stuff" around the main part of the page.
The stuff includes menus, FIXME

-----------------

# `embed` Put a template inside the DOM nodes

Inserts a template into the current page -- FIXME

-----------------

# `a`

Link to a named page -- FIXME

-----------------

# `choose`

Choose one or more of the child nodes -- FIXME

-----------------

# `subs`

Choose pages of a particular type -- FIXME

-----------------

# `xmenu`

Generate Menus -- FIXME

-----------------

# `bind`

Generate an `id` `<div>` -- FIXME

-----------------

# `menu.title`

The title of the page -- FIXME

-----------------

# `menu.items`

A set of menu items -- FIXME

-----------------

# `group`

Find a group of pages by type -- FIXME

-----------------

# `google-analytics` or `google_analytics`

Insert the JavaScript for Google Analytics -- FIXME

-----------------

# `withparam`

Insert content into surrounding template -- FIXME

-----------------

# `archived_posts`

List all blog posts and bind to a template by date -- FIXME


-----------------

# `xform`

After the page is fully rendered, apply a CSS Transformation to the page -- FIXME

-----------------

# `page-info` or `page_info` or `pageinfo`

Insert values from Extra Info into the DOM
