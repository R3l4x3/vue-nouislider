# vue-nouislider

<p align="center">
<a href="https://github.com/R3l4x3/vue-nouislider">
<img src="https://raw.githubusercontent.com/R3l4x3/vue-nouislider/master/Logo.png" width="160">
</a>
<br>
<a href="https://www.npmjs.com/package/vue-nouislider">
<img src="https://img.shields.io/npm/v/vue-nouislider.svg" alt="">
</a>
<a href="https://www.npmjs.com/package/vue-nouislider">
<img src="https://img.shields.io/npm/dm/vue-nouislider.svg" alt="">
</a>
<a href="https://vuejs.org/">
<img src="https://img.shields.io/badge/vue-2.x-brightgreen.svg" alt="">
</a>
</p>

>A [Vue.js](https://vuejs.org/) wrapper for [noUiSlider](https://refreshless.com/nouislider/)

## Table of contents

- [Installation](#installation)
- [Usage](#usage)
- [Example](#example)

# Installation

```
npm install --save vue-nouislider
```

## Default import

Install all the components:

```javascript
import Vue from 'vue'
import VueNouislider from 'vue-nouislider'

Vue.use(VueNouislider)
```

Use specific components:

```javascript
import Vue from 'vue'
import { Test } from 'vue-nouislider'

Vue.component('test', Test)
```

**⚠️ A css file is included when importing the package. You may have to setup your bundler to embed the css in your page.**

## Distribution import

Install all the components:

```javascript
import 'vue-nouislider/dist/vue-nouislider.css'
import VueNouislider from 'vue-nouislider/dist/vue-nouislider.common'

Vue.use(VueNouislider)
```

Use specific components:

```javascript
import 'vue-nouislider/dist/vue-nouislider.css'
import { Test } from 'vue-nouislider/dist/vue-nouislider.common'

Vue.component('test', Test)
```

**⚠️ You may have to setup your bundler to embed the css file in your page.**

## Browser

```html
<link rel="stylesheet" href="vue-nouislider/dist/vue-nouislider.css"/>

<script src="vue.js"></script>
<script src="vue-nouislider/dist/vue-nouislider.browser.js"></script>
```

The plugin should be auto-installed. If not, you can install it manually with the instructions below.

Install all the components:

```javascript
Vue.use(VueNouislider)
```

Use specific components:

```javascript
Vue.component('test', VueNouislider.Test)
```

## Source import

Install all the components:

```javascript
import Vue from 'vue'
import VueNouislider from 'vue-nouislider/src'

Vue.use(VueNouislider)
```

Use specific components:

```javascript
import Vue from 'vue'
import { Test } from 'vue-nouislider/src'

Vue.component('test', Test)
```

**⚠️ You need to configure your bundler to compile `.vue` files.** More info [in the official documentation](https://vuejs.org/v2/guide/single-file-components.html).

# Usage

> TODO

# Example

> TODO

---

# Plugin Development

## Installation

The first time you create or clone your plugin, you need to install the default dependencies:

```
npm install
```

## Watch and compile

This will run webpack in watching mode and output the compiled files in the `dist` folder.

```
npm run dev
```

## Use it in another project

While developping, you can follow the install instructions of your plugin and link it into the project that uses it.

In the plugin folder:

```
npm link
```

In the other project folder:

```
npm link vue-nouislider
```

This will install it in the dependencies as a symlink, so that it gets any modifications made to the plugin.

## Publish to npm

You may have to login to npm before, with `npm adduser`. The plugin will be built in production mode before getting published on npm.

```
npm publish
```

## Manual build

This will build the plugin into the `dist` folder in production mode.

```
npm run build
```

---

## License

[MIT](http://opensource.org/licenses/MIT)
