[title: RSS Feeds and More]: /

## Lots of new stuff in Telegram this week!

[Telegram](https://telegr.am) continues to mature and get new features.

### RSS Atom files

Telegram automatically creates an `/rss.xml` [RSS Atom file](http://en.wikipedia.org/wiki/Atom_%28standard%29) if there are blog posts.
This can be disabled with the `no_synthetic_rss_file: true` extra info.
If the Atom file, a link `<link type="application/rss+xml" rel="alternate" href="/rss.xml">` is
automatically inserted into each page.

### Right hand column

There's lots of stuff you can do to modify the flow of the page.  The following
code in `templates-hidden/include.html` creates 2 columns and puts a Twitter feed in
the right hand column:

    <div>
        <!-- change the footer to put different message in it -->
        <span data-lift="xform" data-css="footer *">(c) 2010-2012 David Pollak</span>
        
        <!-- add a 'row' class to the element with id 'main_content_place' -->
        <span data-lift="xform" data-css="#main_content_place [class+]">row</span>
        
        <!-- make the left side column a 'span10' -->
        <span data-lift="xform" data-css="#left_side [class+]">span10</span>
        
        <!-- and make the right column a 'span6' -->
        <span data-lift="xform" data-css="#right_side [class+]">span6</span>
        
        <!-- insert the following div in the right column -->
    	<div data-lift="xform" data-css="#right_side *+">
    	    <!-- the div includes a twitter feed -->
    		<span data-lift="twitter?user=dpp">
    	</div>
    </div>
    
### Search box

The following code will insert a site-specific Google search box onto any page:

    <form data-lift=search></form>
    
By default, the templates include a search box in the upper-right.

### All sites listed

The [Sites](https://telegr.am/sites) page now lists all the domains hosted on Telegram
including the custom domains.

### Custom domains

Telegram supports custom domains.  To use the custom domain feature, enter a domain
name into the "optional domain name" field when creating or editing a site.
Domains may not be root domains (e.g., [goodstuff.im](http://goodstuff.im))
but must be subdomains (e.g., [blog.goodstuff.im](http://blog.goodstuff.im)).
 
Next, go to your DNS provider and create a [CNAME](http://en.wikipedia.org/wiki/CNAME_record) record 
pointing to [cname.telegr.am](http://cname.telegr.am).  Your site
will be served by Telegram.

### Enjoy

Please enjoy the new Telegram features and please use the Feedback tabs
to leave feedback or ask us questions.

Rock and roll!!

