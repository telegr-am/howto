## How to blog using Telegram

Telegram is a nifty way for you to blog based on files
in your Dropbox or hosted on GitHub.  This means you
can blog from anywhere on any device.  Simple.

If you put a file in the `_posts` directory, the file will be considered
a blog post.

You can add extra info to the page to define information about the post:

    [title: How to blog]: /
    [category: Tech]: /
    [date: 2012/06/20]: /
    [tags: {blog, tech}]: /

Where:

* `title` is the title of the post.
* `category` is the category of the post (Telegram
   will have support for display of posts by category soon). 
* `date` is the date of the post.  If the date is in the future, the post will not be displayed
  until the site is refreshed on or after the date (there will be a feature in Telegram soon
  to auto-generate sites if they have a date in the future).
* `tags` are a set of tags associated with the post.  There will be a way to group posts
  by tag real soon now(™).

You can list blog posts by including the following HTML on any page:

    <ul class="posts" style="list-style: none" data-lift="blog.posts?max=15">
        <li data-post="item"><h2><a data-post="link" href="#">Blog Post</a></h2>
        	<h4 style="padding-left: 8px;"><span data-post="date">2012/12/14</span></h4>
        	<div style="padding-left: 15px;" data-post="shortcontent">Post Content goes here</div>
    	    <div data-post="more"><a href="#">Read More...</a></div>
            <hr>
        </li>
    </ul>

Where:

* `data-lift="blog.posts?max=15"` invokes a snippet that transforms the DOM elements contained
  inside the `<ul>` based on the existing blog posts.  There will be one `<li>` element for
  each blog post.  The `max` parameter specifies the maximum number of blog posts to list.
* `data-post="item"` -- this element will be repeated for each blog post.
* `data-post="link"` -- the `href` attribute of this item will be set to the blog post and the
  body of the element will be set to the title of the blog post.
* `data-post="date"` -- the date of the post.
* `data-post="content"` -- the whole content of the post (not advised if you have long posts).
* `data-post="shortcontent"` -- the first 700 characters of the post.
* `data-post="more"` -- if the post was truncated this element (and its sub-elements) will be displayed
  and the `href` attribute of the `<a>` tag will be set to a link to the post.
  
## Tranforming every page (like putting your own footer on the page)
  
On a separate note, you can apply a transformation to every page on your site.  After
Telegram renders the page, but before it writes the HTML, Telegram does a final set of
page transformations.  If you are using a Telegram template, put a files named `include.html`
in the `templates-hidden` directory.  This file will be included in every page on
your site.

Within the file, you can include snippets, for example:

    <div>
    	<span data-lift="xform" data-css="footer *">This is my blog (c) 2012 by me</span>
    </div>

The page must be a single HTML element, so the outer `<div>` is discarded.

The `<span>` contains a snippet invocation.  The `xform` snippet takes the value
of the `data-css` attribute and treats it as a [CSS Selector Transform](http://simply.liftweb.net/index-7.10.html).  The element itself (the `<span>` element) will be substituted for all
matching HTML elements.  In this case, the `<span>` element is placed inside all `<footer>` tags.
The result is that the footer on every page is set to `<span>This is my blog (c) 2012 by me</span>`.



[title: How to blog]: /
[category: Tech]: /
[date: 2012/06/20]: /
[tags: {blog, tech}]: /