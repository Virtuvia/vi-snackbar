[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/virtuvia/vi-snackbar)

##&lt;vi-snackbar&gt;##

Material Design: [Snackbars](https://www.google.com/design/spec/components/snackbars-toasts.html)

Use the `snackbar-dismiss` attribute on interactive controls to close the snackbar
in a similar fashion to `dialog-confirm` or `dialog-dismiss`.

Example w/ manual control:

```html
    <vi-snackbar id="mySnackbar">Save successful!</vi-snackbar>
    
    ...

    save: function () {
        ...
        this.$.mySnackbar.active = true;
        this.async(() => {
            this.$.mySnackbar.active = false;
        }, 4000);
    }
```

Example w/ dismiss:

```html
    <vi-snackbar id="mySnackbar" active="{{_saveError}}">
        <span>There was an error during save</span>
        <paper-button snackbar-dismiss>Dismiss</paper-button>
    </vi-snackbar>

    ...

    save: function () {
        ...
        this._saveError = true;
    }
```

### Styling

The following custom properties and mixins are available for styling:

Custom property | Description | Default
----------------|-------------|----------
`--vi-snackbar-active`      | Mixin applied to the snackbar when active | `{}`
`--vi-snackbar-active-two-line` | Mixin applied to snackbar when active in two-line mode  | `--primary-color`
