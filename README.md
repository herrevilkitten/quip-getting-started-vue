# Getting Started with Quip Live Apps in Vue

## Create a new Quip project

create-quip-app

## Add Vue dependencies to the project

vue
vue-loader
vue-style-loader
vue-template-compiler

## Modify the build script

> CSP stuff

perl
NODE_ENV=production webpack; perl -pi -e 's/Function\\(\"return this\"\\)\\(\\)/window/g' app/dist/app.js; create-quip-app pack ./app

sed
sed -i '' 's/Function(\"return this\")()/window/g' app/dist/app.js
