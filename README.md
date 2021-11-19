# Scoop.it topic embeds customization how-to

Documentation about how to customize scoop.it topic embeds

## Design principles

Scoop.it topic embed is designed to accomodate with your existing site style:
- `font-family` is never set: fonts are inherited from your website design
- all sizes are set in `rem` so they are relative to the font size of the root of page (including padding/margins)
- by default, no colors are set
- responsive by default
- no title tags are used (`h1`, `h2`...) to avoid design issue

## Advanced customization

The embed generator let you define a fair amount of customization, but it may be necessary to go further. This is done with classing CSS rules on well identified classes used by the embed.

Example:
```html
<style>
  /* white color for the text of the curator insight */
  .scp-embed-post-insight {
    color: white;
  }
  /* specific font family on titles (header & posts) */
  .scp-embed-header-title, .scp-embed-post-title {
    font-family: Roboto, Helvetica, sans-serif;
    font-weight: bold;
  }
  /* specific color on post meta */
  .scp-embed-post-meta, .scp-embed-post-meta a {
    color: #ddd;
  }
</style>
```

List of stable classes that can be used to change style of elements of the embed.

| class name                     | location                    |
| ------------------------------ | --------------------------- |
| `scp-embed-container`          | root div of the embed |
| `scp-embed-block`              | all "blocks" elements (posts, header, pagination buttons) |
| `scp-embed-header`             | root div of the embed header |
| `scp-embed-link`               | all links in the embed |
| `scp-embed-header-curatedBy`   | "curated by" section in the embed |
| `scp-embed-header-title`       | title of the header |
| `scp-embed-header-description` | description of the header |
| `scp-embed-powered-by`         | powered by scoop.it section |
| `scp-embed-post-container`     | post container |
| `scp-embed-post-title`         | post title |
| `scp-embed-post-meta`          | post meta (url & date) |
| `scp-embed-post-image`         | post image |
| `scp-embed-post-description`   | post description |
| `scp-embed-post-insight`       | post insight |
| `scp-embed-columns-container`  | div containing columns - _Responsive grid_ embed only |
| `scp-embed-column`            | column conraining posts - _Responsive grid_ embed only |

Here are some rules of thumb when a applying custom css to the embed:
- only classes prefixed by `scp-embed-` should be considered as stable
- thus, to change padding on posts, do not override `scp-p-4` which is used - as of this writing - to add a padding around elements: it may disappear in the future, but prefer adding rule on `scp-embed-post-container`
- sizes are relative to the `font-size` of the `html` element, if this size does not matches the overall design if the site, it will result in a very weird result. 
- spacing between elements is done with the use of `flex` container with `gap` css property.


## Known issues

Inserting the embed as a `flex` item may result in undefined behaviour (width may be larger than the page, responsiveness may not work properly)



