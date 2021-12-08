# Scoop.it newsletter subscribe embed widgets customization how-to

Documentation about how to customize scoop.it newsletter subscribe embed widgets

## Design principles

Scoop.it embed is designed to accomodate with your existing site style:
- `font-family` is never set: fonts are inherited from your website design
- all sizes are set in `rem` so they are relative to the font size of the root of page (including padding/margins)
- by default, we use scoop.it colors (either standars colord or colors of your Scoop.it space)
- no title tags are used (`h1`, `h2`...) to avoid design issue
- links (close & submit) are html `button`

## Advanced customization

List of stable classes that can be used to change style of elements of the embed.

| class name                     | restricted to  | location                    |
| ------------------------------ | -------------- | --------------------------- |
| `scp-subscribe-inline-content`   | inline widget  | root container of the inline widget 
| `scp-subscribe-inline-title`     | inline widget  | title of the inline widget 
| `scp-subscribe-overlay`          | popup widget   | root container of the popup widget: sets the overlay up
| `scp-subscribe-popup`            | popup widget   | popup root
| `scp-subscribe-popup-title`      | popup widget   | popup title
| `scp-subscribe-popup-content`    | popup widget   | popup content
| `scp-subscribe-subtitle`         |                | subtitle
| `scp-subscribe-description`      |                | description
| `scp-subscribe-form-field-container` |            | container of field (contains both the label & the input)
| `scp-subscribe-label`            |                | label of fields
| `scp-subscribe-email`            |                | email input field
| `scp-subscribe-agreement`        |                | agreement checkbox input field
| `scp-subscribe-error`            |                | validation error
| `scp-subscribe-button`           |                | subscribe button
| `scp-subscribe-button-submitting` |               | subscribe button while subscribing (added to `scp-subscribe-button`)
| `scp-subscribe-footer`           |                | footer

Here are some rules of thumb when a applying custom css to the embed:
- only classes prefixed by `scp-subscribe-` should be considered as stable
- sizes are relative to the `font-size` of the `html` element, if this size does not matches the overall design if the site, it will result in a very weird result. 
- spacing between elements is mostly done with the use of `flex` container with `gap` css property.

## Example

Change the color of the popup title, put this anywhere in the page where the popup is rendered:

```html
<style>
    .scp-subscribe-popup-title {
        background-color: #eee !important;
        color: black !important;
    }
</style>
```

Change the color of the submit button
```html
<style>
   .scp-subscribe-button {
       background-color: white !important;
       color: black !important;
       border: 1px solid black !important;
   }
   .scp-subscribe-button:hover {
       background-color: #eee !important;
   }
</style>

```