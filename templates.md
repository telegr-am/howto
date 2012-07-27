# Templates

Telegram automatically surrounds pages with a template if the page does not contain
the correct HTML structure.  So, if a page has `<html>` and `<body>` tags,
Telegram figures the page is the way you want it and will not add any template
information.  So, the following page will be served as-is:

```
<html>
  <head><title>Hi</title></head>
  <body>I'm pretty plain!</body>
</html>
```

But, Telegram will surround the following page with a template:


    <p>I'm pretty plain!</p>


## Choosing a template

By default, Telegram looks for a template in the file `/templates-hidden/default.html`.
You can specify the name of the template to use with the `template` Extra Info:

    template: post
    
That will tell Telegram to use the `/templates-hidden/post.html` template for the page.

## Where do the templates come from?

If the `template_url` extra info is specified, Telegram tries to [`git clone`](http://gitref.org/creating/)
the URL specified.  For example:

    template_url: https://github.com/telegr-am/template-green.git

Once the repository is cloned, Telegram adds each file in the repository to your site, unless you've
already got a file by that name in your site.

The Git URL must be a public Git repository.

## What happens by default?

If there's no `template_url` Extra Info and there's no `/templates-hidden/default.html` file,
Telegram clones the [default template](https://github.com/telegr-am/template-base).


# You can publish your own templates

If you want to publish Telegram templates, just put up a public Git repository
with the template information in it.  GitHub provides costless hosting for
public repositories.

# Available templates

### Green

    template_url: https://github.com/telegr-am/template-green.git

![Green](https://github.com/telegr-am/template-green/raw/master/_site_image.jpg)

### Blue

    template_url: https://github.com/telegr-am/template-blue.git

![Blue](https://github.com/telegr-am/template-blue/raw/master/_site_image.jpg)

