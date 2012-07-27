## How to change the footer

1. Open the `/templates-hidden/include.html` file with a text editor
2. Add the line:   
```
<span data-lift="xform" data-css="footer *">Stuff for the footer</span>
```
1. Save the file and publish your site

The  `/templates-hidden/include.html` file is included in every page via the
`default.html` and `post.html` template files.

The `data-lift="xform"` attribute says that this is a page transformation rule.

The `data-css="footer *"` attribute says, "find all the `<footer>` elements and
substitute this element into the body of the found elements".
