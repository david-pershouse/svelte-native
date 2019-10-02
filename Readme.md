# Svelte Native

Create Mobile applications using native widgets via Svelte [Svelte](https://github.com/sveltejs/svelte) and [NativeScript](https://github.com/nativescript/nativescript).

See https://svelte-native.technology for docs and tutorials

![todo in svelte-native](https://raw.githubusercontent.com/halfnelson/svelte-native/master/nativescript-svelte-todo.gif)

## Features

Svelte-Native includes Svelte specific integrations such as

 * The ability to use svelte components to create native applications on top of NativeScript core
 * Svelte specific navigation and modals eg `navigate({ page: MySvelteComponent })`
 * Integration with svelte's transistions eg `<label transition:fade="{duration: 2000}">`
 * Integration with sveltes scoped styles
 * Complete coverage of the Nativescript core UI modules
 * Uses unmodified Svelte and Nativescript modules

## Work In Progress

While Svelte Native is feature complete, there are some items outstanding to bring it to the level of other Nativescript library integrations

 - [ ] Full support for the Progress professional UI components [#22](https://github.com/halfnelson/svelte-native/issues/22)
 - [ ] Improved documentation around importing Nativescript plugins [#45](https://github.com/halfnelson/svelte-native/issues/45)
 - [ ] A Nativescript app template for use with `tns create --template` [#52](https://github.com/halfnelson/svelte-native/issues/52)
 - [ ] An examples page that shows open source applications made with Svelte Native [#51](https://github.com/halfnelson/svelte-native/issues/51)
 - [ ] Migrate the site to the latest version of Svelte's [SiteKit](https://github.com/sveltejs/site-kit) [#53](https://github.com/halfnelson/svelte-native/issues/53)
 - [x] At least 1 emoji in readme.md :+1:
 - [ ] More Tests 😳 [#54](https://github.com/halfnelson/svelte-native/issues/54)
 

## Installation

You can get started developing with this using the [latest template app](https://github.com/halfnelson/svelte-native-template)

```bash
$ npx degit halfnelson/svelte-native-template myapp
```

A fresh Svelte Native app will be found in the `myapp` folder

Once installed, the build workflow is to use the `tns build` or `tns run` commands as normal. 

## Usage

App.svelte
```html
<page>
    <actionBar title="Svelte Native"></actionBar>
    <stackLayout>
        <label text={msg}></label>
        <button text="Change" on:tap="{toggle}"></button>
    </stackLayout>
</page>

<script>
  export let msg = 'Hello World!'
  const toggle = () => {
      msg = "Hi from svelte"
  }
</script>
```

Main.ts
```js
import App from './components/App.svelte';

import { svelteNative } from 'svelte-native'

svelteNative(App, {msg: "Hi from launcher"});
```

## Credits

The DOM implementation is based on the one from Nativescript-Vue. Thanks!

The API documentation was originally ported from the Nativescript-Vue site.

The site design is from SvelteJS

