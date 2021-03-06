---
layout: page
title: Transpilers | Integration | PM2 Documentation
menu: starter
lang: en
section: runtime
redirect_from: "/runtime/integration/transpilers"
---

# Using PM2 with transpilers

This tutorial will show you how to use pm2 with transpilers.

!> We highly don't recommend to use this in **production** as it slows down your app. In that case, your app must be bundled i.e. transpiled from the source to get a pre-processed version of your app.

---

## Babel

```bash
## Install the Babel CLI globally:
npm install -g babel-cli

## Start pm2 with the Babel CLI binary in watch mode:
pm2 start --watch --interpreter babel-cli app.js
```

Or, you can create an other file, which requires the transpiler and your app:
```javascript
// index.js
require('babel-register');
require('./app.js');
```
Then, run:
```bash
pm2 start --watch index.js
```

?> The cluster mode is only available with the second option.

---

## Coffee-script

```bash
## Install Coffee Script globally:
npm install -g babel-cli

## Start pm2 with coffee binary in watch mode:
pm2 start --watch --interpreter coffee app.coffee
```

Or, you can create an other file, which requires the transpiler and your app:
```javascript
// index.js
require('coffee/register');
require('./app.coffee');
```
Then, run:
```bash
pm2 start --watch index.js
```

?> The cluster mode is only available with the second option.

---

## Questions?

We are always happy to help with questions you might have. Use the search or check out the FAQ. You can also post questions or comments on the [PM2 github repository](https://github.com/Unitech/pm2/issues).
