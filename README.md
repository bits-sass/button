# Bits.sass button

Button component.

Read more about [Bits.sass toolkit](https://github.com/bits-sass/bits.sass).

## Installation

* __Bower:__ `bower install --save bits-sass-button`
* __Download:__ [zip](https://github.com/bits-sass/button/zipball/master), [tar.gz](https://github.com/bits-sass/button/tarball/master)
* __Git:__ `git clone https://github.com/bits-sass/button.git`

## Available SASS variables

* `bits-components-ns` - components namespace, defaults to 'bits-'

## Available classes

* `Button` - core button component
* `Button--full` - modifier class for full-width buttons
* `is-disabled` - for disabled-state button styles (themes)

N.B. You must also include the `disabled` attribute on `button` and `input`
elements. For `a` elements, you should remove the `href` attribute and prevent
JavaScript event handlers from firing.

## Usage

Like many Bits.sass components, `bits-sass-button` relies on a base component class that is
extended by any number of additional modifier classes.

```html
<a class="Button Button--full" href="[url]">Sign up</a>

<button class="Button is-disabled" type="submit">Submit</button>

<input class="Button is-pressed" type="submit" value="Submit">
```

## Theme HTML classes

The following modifier and state classes should be implemented by all themes.
This ensures that themes can hook into a shared set of HTML class names. You're
still free to create additional, custom modifier names if your theme requires
them.

* `Button--largest` (optional) - largest button size
* `Button--large` - large button size
* `Button--small` - small button size
* `Button--smallest` (optional) - smallest button size
* `Button--default` - default button style of your theme
* `is-disabled` - for disabled-state button styles
* `is-pressed` - for pressed-state button styles

N.B. You should try to avoid styling the core `Button` class directly.

## Theming

The `bits-sass-button` component is almost entirely structural. You can rely on a
theme or build your application-specific theme styles in your application-level
stylesheets. For example:

```scss
/**
 * theme/components/_button.scss
 */

/**
 * Modifier: default buttons
 */

.Button--default {
  border-color: #d9d9d9 #d9d9d9 #ccc;
  border-radius: 2px;
  color: #444;
  background-color: #eee;
}

.Button--default {
  &:hover,
  &:focus,
  &:active,
  &.is-pressed {
    border-color: #c6c6c6 #c6c6c6 #bbb;
    color: #222;
    box-shadow: 0 1px 2px rgba(0, 0, 0, 0.2);
    background-color: #f5f5f5;
  }
}

.Button--default:focus {
  border-color: #069;
  outline: 0;
}

.Button--default {
  &:active,
  &.is-pressed {
    box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.2);
    background-color: #ccc;
  }
}

/**
 * Modifier: large buttons
 */

.Button--large {
  font-size: 1.5em;
  padding: 0.75em 1.5em;
}
```

## Requirements

* Sass 3.2+

## Browser support

* Google Chrome (latest)
* Opera (latest)
* Firefox 4+
* Safari 5+
* Internet Explorer 8+