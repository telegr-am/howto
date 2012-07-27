## How to add a Twitter feed

1. Open the `/templates-hidden/include.html` file with a text editor
2. Add the lines:   

        <span data-lift="xform" data-css="#main_content_place [class+]">row</span>
        <span data-lift="xform" data-css="#left_side [class+]">span10</span>
        <span data-lift="xform" data-css="#right_side [class+]">span6</span>
        <div data-lift="xform" data-css="#right_side *+">
        	<span data-lift="twitter?user=dpp">
        </div>

1. Save the file and publish your site

The  `/templates-hidden/include.html` file is included in every page via the
`default.html` and `post.html` template files.

The `data-lift="xform"` attribute says that this is a page transformation rule snippet.

The `data-css="#main_content_place [class+]"` attribute says, "find the element with
the `main_content_place` id and
add the `row` class to the element's CSS classes".  The next two lines add
`span10` and `span6` classes to the left and right `<div>` elements.  The
effect based on the [Twitter Bootstrap](http://twitter.github.com/bootstrap/)
CSS rules is to create a row with two columns, the left and right side columns.

The `#right_side *+` transform appends the elements to the child elements of
the right-side column.

The `data-lift="twitter?user=dpp"` snippet inserts a Twitter feed into
the element.

There's more information on [snippets](/snippets).