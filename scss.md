---
title: SCSS Utilities
---

The documentation below describes the SCSS mixins, functions, and variables
provided by the `@***********` module.

## Mixins

### `elevation($depth: number)`

Apply an elevation appearance of a specified depth.

Parameters:

- `$depth` (number)

### `focus-ring()`

Adds a focus ring style to an element.

### `font($style-name: *, $size: *)`

Apply a typography style.

Parameters:

- `$style-name` (\*): Name of semantic style

- `$size` (\*): Size variant of the style

### `font-size($style-name: *, $size: *)`

Apply `font-size` consistent with a defined typography style.

Parameters:

- `$style-name` (\*): Name of semantic style

- `$size` (\*): Size variant of the style

### `line-height($style-name: *, $size: *)`

Apply `line-height` consistent with defined typography style.

Parameters:

- `$style-name` (\*): Name of semantic style

- `$size` (\*): Size variant of the style

### `not-visually-disabled()`

Wraps content in a "not visually disabled" selector.

### `scrollbar()`

Provide custom scroll-bars, when supported.

### `semantic-brand-color($style: string)`

Creates a brand style variant on an existing component or element.

Parameters:

- `$style` (string): The name of the brand style to apply.

### `semantic-intent-color($style: string)`

Creates a intent style variant on an existing component or element.

Parameters:

- `$style` (string): The name of the intent style to apply.

If the intent does not exist, the primary brand color will be applied.

### `set-semantic-colors($color: *)`

Sets semantic color for _all_ levels. Use with caution.
The color passed into this mixin is not a semantic color name,
but an actual CSS value. All semantic color levels will be set to
the same value.

Parameters:

- `$color` (\*): Color value assigned to each level.

### `typography($style-name: *, $size: *)`

**⚠️ Deprecated:** This mixin is not used in `atx-style-engine`. Please use the `font()` mixin instead.

Apply a typography style.

Parameters:

- `$style-name` (\*)

- `$size` (\*)

### `use-focus-ring()`

Alias of `focus-ring()`.

### `use-semantic-colors($type: string, $default-style: string)`

Prepares an existing component or element to use semantic styles.
Must be called before the `semantic-style()` mixin (see below).

Parameters:

- `$type` (string): "brand" or "intent"

- `$default-style` (string): The default style to apply if no semantic style is specified.

### `visually-disabled()`

Wraps content in a Visually Disabled selector.

---

## Functions

### `gradient($gradientTokenName: *)`

Returns a linear gradient based on a token name.

Parameters:

- `$gradientTokenName` (\*): Name of the gradient defined in the token set. i.e. "background-light-1"

### `selectors-list($items: list, $selector-template: string, $placeholder: string)`

Returns a list of selectors based on a provided template

Parameters:

- `$items` (list): list of values

- `$selector-template` (string): Selector template.

- `$placeholder` (string): The string to replace in the
  `$selector-template`.

If a `$placeholder` is not provided, it is expected that the
`$selector-template` will include the string "$item".

### `selectorsList()`

Alias of selectors-list

### `str-replace($string: String, $search: String, $replace: String)`

Replace `$search` with `$replace` in `$string`.

Parameters:

- `$string` (String): Initial string

- `$search` (String): Substring to replace

- `$replace` (String): ('') - New value

### `token($tokens-map: map, $name: string, $format: string)`

**⚠️ Deprecated:** Use CSS custom properties directly, i.e. `var(--atx-token-name)`.

Render a design token in a given format prior to compilation.
Note: When used with the ATX Style Engine, your `$tokens-map` will
be provided in the global scope as both `$t`and `$tokens`.

Parameters:

- `$tokens-map` (map): Tokens list in `map` format

- `$name` (string): Kebab-cased name of the token, excluding the prefix.

- `$format` (string): Variable rendering format. **deprecated** for new engine.
  Accepted values: `css` | `scss`.
  Default: `css`

### `unit($value: *, $unit: *)`

Render a value properly suffixed with a unit type.
Use in situations when string interpolation doesn't work as needed.
Example: `unit(1.25, px)` > 1.25px

Parameters:

- `$value` (\*): Any numeric value, e.g. `1.25`

- `$unit` (\*): Name of a unit, e.g. `px`

### `use-token()`

Alias of the `token()` function.

---

## Variables

### `$default-token-format`

We placed the token module within internal/ so that modules within
the library can still access the token module without having to

### `$tokens`

While the `$tokens` map is passed into the `token()` function as `$t` or
`$tokens` when the function is used in third-party code, the internal
modules of this library must have access to the same $tokens map.
This is the purpose for the variable below.
