[title: Lots of new Telegram Features]: /

## Telegram grew a ton of new features

I was on vacation in Europe for the last few weeks, but I still got some coding it.

Specifically, I moved the [Hoisted](http://hoisted.org) templating stuff into the
new Hoisted modules that render static HTML.  This means that menu generation works
and being able to grab an arbitrary set of pages (e.g., announcements or quotes)
and list the pages and links to the pages.  Lots of examples can be found in the
[Lift CMS](https://github.com/lift/cms_site) repository.  Note that the templates
can be in any combination of XML, HTML, and Markdown.

Telegram also has extensive GitHub integration including:

* Repositories are cloned/pulled using a per-repository [Deploy Key](https://help.github.com/articles/managing-deploy-keys) that Telegram generates and manages.  This is the fast and efficient way of syncing the repositories with Telegram.
* When you push to your repository, GitHub executes a [Service Hook](https://help.github.com/articles/post-receive-hooks) that notifies Telegram about the updated repository.  Once Telegram gets the service hook call, it pulls and re-renders your site.  That means that each time you push to GitHub, your site is automatically re-rendered.

I've added a bunch of other stuff to the GitHub support (like lazily calling GitHub to retrieve your
repository list) to improve the overall quality of Telegram when working with GitHub.

Enjoy!

David
