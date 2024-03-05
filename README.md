# webpack-dev-server-repro

> Minimal Webpack Dev Server 5 bug reproduction: https://github.com/webpack/webpack-dev-server/issues/5088

## Start

```sh
npm install && npm start
```

Gives:

```none
> webpack serve

[webpack-cli] Invalid options object. Dev Server has been initialized
using an options object that does not match the API schema.
 - options has an unknown property '_assetEmittingPreviousFiles'.
   These properties are valid:
   object { allowedHosts?, bonjour?, client?, compress?, devMiddleware?,
   headers?, historyApiFallback?, host?, hot?, ipc?, liveReload?,
   onListening?, open?, port?, proxy?, server?, setupExitSignals?,
   setupMiddlewares?, static?, watchFiles?, webSocketServer? }
```

Note that when replacing Webpack CLI version in `package.json`:

```diff
- "webpack-cli": "4.10.0"
+ "webpack-cli": "5.1.4"
```

And re-installing, the build works fine!