# Getting Started with Quip Live Apps in Vue

This is a guide for creating [Quip Live Apps](https://salesforce.quip.com/about/live-apps) using [Vue](https://vuejs.org/).  The Quip documentation recommends using [React](https://reactjs.org/) and provides additional support for it -- for example, the React Javascript libraries are automatically imported into your application and some Quip-specific UI components are provided.

## Caveats

Becaue Quip Live Apps were not designed with Vue in mind, there is no official support.  This document will guide you through the process of modifying the necessary files and example files are located in the `files` directory.

Some other things to keep in mind:

* When creating a React appication, the React libraries are not added to your app.ele bundle because Quip will automatically provide them.  Vue libraries are not provided, so they will be added to the bundle.  This can increase the size of the application by 200KB.

* Only Vue Single File Components (SFC) are supported.  The Vue templating system uses methods which break [Content Security Policy (CSP)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP) and will not run as a Live App.  SFCs are compiled at build time and will not break CSP.

* `webpack.config.js` has been customized.  It uses the default Quip configuration and then modifies it to support Vue.  If Quip makes changes to the default configuration, the custom configuration may need to be updated.

* With everything in Single File Components, `app.css` is not used (and is not in the manifest.)  If an external stylesheet is needed, the manifest may need to be updated.

* There are two known CSP issues with the default configuration.  They have been alleviated with some configuration and build changes.

## Create a new Quip project

Because this guide modifies the default configuration, you should start by installing and running `create-quip-app`

```
npm install -g create-quip-app
create-quip-app <directory>
cd <directory>
```

This will create a starter project and install a number of dependencies.

## Add Vue dependencies to the project



vue
vue-loader
vue-style-loader
vue-template-compiler

## Modify the Webpack configuration

## Modify the build script

> CSP stuff

perl
NODE_ENV=production webpack; perl -pi -e 's/Function\\(\"return this\"\\)\\(\\)/window/g' app/dist/app.js; create-quip-app pack ./app

sed
sed -i '' 's/Function(\"return this\")()/window/g' app/dist/app.js

