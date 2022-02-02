# vite-plugin-firebase [![npm](https://img.shields.io/npm/v/vite-plugin-firebase.svg)](https://www.npmjs.com/package/vite-plugin-firebase)

This plugin will start firebase emulators (by default hosting & functions) in-process when running vite dev server (vite serve).

### Installation

```
npm install --save-dev vite-plugin-firebase
```

### Usage

Add it to vite.config.js

```js
import firebasePlugin from 'vite-plugin-firebase';

export default {
  plugins: [firebasePlugin({
    // mandatory firebase project id
    projectId: 'my-project-id',
    // project directory, i.e. where firebase.json is (defaults to `config.root`)
    root: path.resolve('somewhere'),
    // whether to materialize (write on disk) `.runtimeconfig.json` for functions emulator (defaults to `false`)
    materializeConfig: true,
    // emulator targets (defaults to `['hosting', 'functions']`)
    targets = ['hosting']
  })]
}
```

### Caveats

This plugin uses internal firebase-tools APIs to load emulators in-process.
May break upon firebase-tools releases, have been tested with `9.22` & `9.23`

### License

[MIT](https://opensource.org/licenses/MIT)

Copyright (c) 2021-present, <DIV>Riots
