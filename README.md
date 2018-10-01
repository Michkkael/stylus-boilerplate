# Stylus boilerplate

:muscle: A Stylus boilerplate for building strong CSS architecture for your app.

## Getting started :v:

* Copy this repository into your project. It will add `fonts` and `styles` folders.

```bash
$ cd {PATH_TO_FOLDER}
$ git archive --format=tar --remote git@bitbucket.org:majdigital/stylus-boilerplate.git HEAD | tar -xk -
```

* Install dependencies:

```bash
$ npm install -S normalize-styl rupture
```

### For a vue.js project

TODO: make the doc :smile:

### For a Nuxt project

* Install dev dependencies:

```bash
$ npm install -D stylus stylus-loader
```

* Add this to `nuxt.config.js`:

```js
/*
** Global CSS
*/
css: ['~/assets/styles/global.styl'],
```

## Usage :wrench:

### Import and use self-hosted fonts

You can easily import fonts to your project by doing the following:

* Go to [transfonter.org](https://transfonter.org/), generate the font for the web (woff + woff2 is enought), and download the pack
* Add the font folder to `./fonts`
* In `./styles/variables/fonts.styl`, create a variable with the font-family value + fallback. (e.g.: `$montserrat: 'Montserrat', sans-serif;`)
* In `./styles/global.styl`, import the font using the mixin font-face (e.g.: `font-face('Montserrat', '../fonts/montserrat/Montserrat-Regular', 400, normal, woff2 woff);`)

> :warning: You can't use the variable here because it contains the fallback (`sans-serif`, `serif`, etc.).

* You can use your font with the variable (e.g.: `font-family: $montserrat;`)

> :bulb: Don't forget to import the `./styles/variables/fonts` if you want to use your variable in a component style.

### Global

You can add any global style in here.

### Variables

Contains all variables (colors, fonts, dimensions, breakpoints, etc.).

#### Usage example

```stylus
// Don't forget to import the variable file if you want to use it
@import '{PATH_TO_VARIABLES}/fonts';
@import '{PATH_TO_VARIABLES}/colors';

.element
  font-family $my-font
  color $my-color
```

### Objects

Contains all objects oriented css. As with any object-based coding method, the purpose of OOCSS is to encourage code reuse and, ultimately, faster and more efficient stylesheets that are easier to add to and maintain. Add any style you think is reusable throughout the project.

> :warning: All objects have to be included in `global.styl` to make sure they are usable as class attribute in HTML.

> :bulb: All objects are prefixed by `-o-` (object).

#### Default objects

| Name       | Description                     |
| ---------- | ------------------------------- |
| layout     | style for the layout of the app |
| typography | typographic style of the app    |

#### Usage example

```html
<main class="-o-container">
  <div class="-o-size-s">
    <h1 class="-o-title-1">Title</h1>
    <p class="-o-text-featured">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
      tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim
      veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
      commodo consequat. Duis aute irure dolor in reprehenderit in voluptate
      velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint
      occaecat cupidatat non proident, sunt in culpa qui officia deserunt
      mollit anim id est laborum.
    </p>
  </div>
</main>
```

### Utilities

Contains all css utilities like easing functions, helpers, mixins. Anything that can help you to build your site style.

#### Default objects

| Name       | Description                                        |
| ---------- | -------------------------------------------------- |
| animations | CSS animations                                     |
| easings    | Standard easings as CSS cubic-bezier               |
| helpers    | Some helpers (e.g.: remove style of a list `<ul>`) |
| mixins     | Some mixins (e.g.: make triangles in CSS)          |

> :bulb: See comments in files for usage :smile:.

### Plugins

Contains all CSS/Stylus plugins.

#### Default plugins

| Name                                                          | Description                                      |
| ------------------------------------------------------------- | ------------------------------------------------ |
| [normalize.styl](https://github.com/bymathias/normalize.styl) | Reset and standardize CSS style for all browsers |
| [rupture](https://github.com/jescalan/rupture)                | Simple media queries in stylus                   |
