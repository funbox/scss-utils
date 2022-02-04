# @funboxteam/scss-utils

This is a set of SCSS mixins we use widely in our projects.

[По-русски](./README.ru.md)

## Rationale

Our projects require a lot of styling, and amount of projects is also great. To share knowledge
and prevent copy-pasting, we decided to move the most used SCSS helpers into a separate library.

## Installation

```shell
npm install --save-dev --save-exact @funboxteam/scss-utils
```

## Library contents

- **[button-style-reset](./button-style-reset.scss)** — local reset of a button tag styles;
- **[placeholder](./placeholder.scss)** — vendor-prefixed pseudo-elements for a placeholder of a text field;
- **[text-cut](./text-cut.scss)** — single-line text cut with ellipsis;
- **[multiline-text-cut](./multiline-text-cut.scss)** — multi-line text cut with ellipsis;
- **[visually-hidden](./visually-hidden.scss)** — hide an element visually, still allowing assistive technologies to access it;
- **[get-unicode-string](./get-unicode-string.scss)** — a function to get Unicode sequence. It is applied as a workaround when a value of a `content` property automatically converts to an unreadable Unicode symbol. The solution comes from the comment to a [GitHub issue](https://github.com/sass/sass/issues/659#issuecomment-64819075).

## Usage

### Direct usage

Import a helper in an SCSS-file in which required mixin should be used:

```scss
@import '../../../node_modules/@funboxteam/scss-utils/visually-hidden';
```

*Use a short version with the tilde operator if your build tool supports it:*

```scss
@import '~@funboxteam/scss-utils/visually-hidden';
```

Include a mixin as needed:

```scss
.button__text {
  @include visually-hidden;
}
```

### Usage via [scss-imports-loader](https://github.com/funbox/scss-imports-loader)

Most of our projects use `scss-imports-loader` with a configuration file located in `config/scss-imports.js`.

Import a helper in the `config/scss-imports.js`:

```js
module.exports = [
  // ...
  'node_modules/@funboxteam/scss-utils/placeholder',
  'node_modules/@funboxteam/scss-utils/visually-hidden',
  'node_modules/@funboxteam/scss-utils/button-style-reset',
  'node_modules/@funboxteam/scss-utils/multiline-text-cut',
  // ...
];
```

Include a mixin as needed:

```scss
.button__text {
  @include visually-hidden;
}
```

## Examples

Example of **get-unicode-string** usage:

```scss
.list__item {
  &::before {
    content: get-unicode-string('2022'); // Browser will display the symbol "•"
  }
}
```

[![Sponsored by FunBox](https://funbox.ru/badges/sponsored_by_funbox_centered.svg)](https://funbox.ru)
