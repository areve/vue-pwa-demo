# vue-pwa-demo

> A experimental Progressive Web App using Vue.

## Steps to create this site

### Setup https host
Setup github pages hosted site, PWA's need valid https to work correctly.

See the [Demo](https://areve.github.io/vue-pwa-demo/dist/index.html)

### Start with the vue pwa template

*vscode, git, node, yarn and vue-cli are already installed*

* To initialize the project run `vue init pwa`
* Start the dev site `yarn dev`
* Remove styles and virtually all content from `Hello.vue` and `App.vue`.
* Add a link to [Picnic CSS](https://picnicss.com/) stylesheet, to make the plain html look slightly less plain until it is time to style it properly.
`*.conf.js`
  * add `<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/picnic/6.5.0/plugins.min.css">` to `index.html`
  * in `webpack.prod.conf.js` add `publicPath: '/vue-pwa-demo/dist',`
  * remove `/dist/` from `.gitignore`
  * test that `yarn build` creates files in `dist`
  * run `npm install -g serve` to get a server then serve the built site with `serve dist`




## Build Setup

``` bash
# install dependencies
yarn

# serve with hot reload at localhost:8080
yarn dev

# build for production with minification
yarn build

# build for production and view the bundle analyzer report
yarn build --report
```

