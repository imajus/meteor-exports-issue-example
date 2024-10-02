## Overview

An example Meteor project with reproduction of the [issue](https://github.com/meteor/meteor/discussions/11727) with Meteor handling of NPM "export" field. 

Run locally:

```
meteor npm i
meteor
```

Expected: Application server starts normally.

But actually it throws an error which prevents it from starting:

```
packages/core-runtime.js:189                  
            throw error;
            ^

Error: Cannot find module "/node_modules/@insurgent/export-map-test/simple.js". Try installing the npm package or make sure it is not a devDependency.
    at Module.useNode (packages/modules-runtime.js:740:11)
    at module (packages/modules.js:212:8)
    at fileEvaluate (packages/modules-runtime.js:335:7)
    at Module.require (packages/modules-runtime.js:237:14)
    at Module.mod.require (/home/denis/.meteor/packages/modules/.0.20.1.1vnw0bc.ypx9++os+web.browser+web.browser.legacy+web.cordova/npm/node_modules/@meteorjs/reify/lib/runtime/index.js:30:33)
    at Module.moduleLink [as link] (/home/denis/.meteor/packages/modules/.0.20.1.1vnw0bc.ypx9++os+web.browser+web.browser.legacy+web.cordova/npm/node_modules/@meteorjs/reify/lib/runtime/index.js:104:22)
    at module.wrapAsync.self (main.js:1:8)
    at Module.wrapAsync (/home/denis/.meteor/packages/modules/.0.20.1.1vnw0bc.ypx9++os+web.browser+web.browser.legacy+web.cordova/npm/node_modules/@meteorjs/reify/lib/runtime/index.js:251:8)
    at module (/home/denis/Workspaces/meteor/meteor-exports-issue-example/.meteor/local/build/programs/server/app/app.js:31:9)
    at fileEvaluate (packages/modules-runtime.js:335:7)
    at Module.require (packages/modules-runtime.js:237:14)
    at Module.mod.require (/home/denis/.meteor/packages/modules/.0.20.1.1vnw0bc.ypx9++os+web.browser+web.browser.legacy+web.cordova/npm/node_modules/@meteorjs/reify/lib/runtime/index.js:30:33)
    at Object.require (packages/modules-runtime.js:257:21)
    at evaluateNextModule (packages/core-runtime.js:167:26)
    at runEagerModules (packages/core-runtime.js:206:3)
    at processNext (packages/core-runtime.js:128:3)

Node.js v20.17.0
```
