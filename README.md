# vue-pwa-demo

> A experimental Progressive Web App using Vue.

## Steps to create this site

### Setup https host
Setup github pages hosted site, PWA's need valid https to work correctly.

See the [Demo](https://areve.github.io/vue-pwa-demo/dist/index.html) or get the [source](https://github.com/areve/vue-pwa-demo) 

### Start with the vue pwa template

*vscode, git, node, yarn and vue-cli are already installed*

* To initialize the project run `vue init pwa`
* Start the dev site `yarn dev`
* Remove styles and virtually all content from `Hello.vue` and `App.vue`.
* Add a link to [Picnic CSS](https://picnicss.com/) stylesheet, to make the plain html look slightly less plain until it is time to style it properly.
`*.conf.js`
  * add `<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/picnic/6.5.0/plugins.min.css">` to `index.html`
  * add `<meta name="description" content="...some description...">` to `index.html`
  * in `webpack.prod.conf.js` add `publicPath: '/vue-pwa-demo/dist',`
  * remove `/dist/` from `.gitignore`
  * test that `yarn build` creates files in `dist` to update the dist folder at any time run this
  * run `npm install -g serve` to get a server then serve the built site with `serve dist`
  * update the path in `manifest.json`  `"start_url": "/vue-pwa-demo/dist/index.html",` and similarly for the icons.
  * move `index.html` to `src/index.html` and update the references in `*.conf.js`
  * push to git and see if the demo site is working

### Testing the PWA app

* in chrome browse to the [Demo](https://areve.github.io/vue-pwa-demo/dist/index.html).
* F12 to open tools, open Network tab
* Ctrl+F5 check for 404 errors
* open the Audit tab, check for any warnings, it is not too hard to get 100 for everything.

### Add more pages to the app

* get `yarn dev` is running
* rename `Hello.vue` to `Home.vue` and find its references and update them too.
* copy `Home.vue` to `Notes.vue`, add routes and links in the header, add somestyles.
* on `Notes.vue` add a hardcoded list of notes in html.
* add some styles for the note.
* make the notes render from an array using `v-for`
* add a button to add a new note
* add a remove button to each note
* add input and textarea
* add edit and done buttons to notes
* add save to localStorage
* add icons with font-awesome
* `yarn build` and push to github

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

