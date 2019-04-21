# Getting Started with Quip Live Apps in Vue

## Create a new Quip project

create-quip-app

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

## Caveats

* `webpack.config.js` has been customized.  It uses the default Quip configuration and then modifies it somewhat.  This means that if Quip changes the defaults, this file may need to be updated.

* With everything in Single File Components, `app.css` is not used (and is not in the manifest.)  If an external stylesheet is needed, the manifest may need to be updated.

* I have only put in support for LESS processing, because it was already listed in `package-lock.json`.  Adding SASS (or other processors) shouldn't be that difficult.

* You may run into CSP errors when loading the Live App inside of Quip.  I've done my best to clean up the problems.
