# @funboxteam/scss-utils

This is a set of SCSS mixins we use widely in our projects.

## Library contents

- **button-style-reset** — local reset of a button tag styles;
- **placeholder** — vendor-prefixed pseudo-elements for a placeholder of a text field;
- **text-cut** — single-line text cut with ellipsis;
- **multiline-text-cut** — multi-line text cut with ellipsis;
- **visually-hidden** — hide an element visually, still allowing assistive technologies to access it.

## Installation

```
npm install --save-dev --save-exact @funboxteam/scss-utils
```

## Usage

### Direct usage

- Import a helper in an SCSS-file in which required mixin should be used:

```
@import '../../../node_modules/@funboxteam/scss-utils/visually-hidden';
```

*Use a short version with the tilde operator if your build tool supports it:*

```
@import '~@funboxteam/scss-utils/visually-hidden';
```

- Include a mixin as needed:

```
.button__text {
  @include visually-hidden;
}
```

### Usage via [scss-imports-loader](https://github.com/funbox/scss-imports-loader)

Most of our projects use `scss-imports-loader` with a configuration file located in `config/scss-imports.js`.

- Import a helper in the `config/scss-imports.js`:

```
  'node_modules/@funboxteam/scss-utils/placeholder',
  'node_modules/@funboxteam/scss-utils/visually-hidden',
  'node_modules/@funboxteam/scss-utils/button-style-reset',
  'node_modules/@funboxteam/scss-utils/multiline-text-cut',
```

- Include a mixin as needed:

```
.button__text {
  @include visually-hidden;
}
```
