# electron-titlebar-windows [![Build Status](https://travis-ci.org/sidneys/electron-titlebar-windows.svg?branch=master)](https://travis-ci.org/sidneys/electron-titlebar-windows)

**Adds the Windows 10 ModernUI (Metro)-style titlebars to any Electron-based desktop app.**



![screen](screen.png)



# Installation

```
$ npm install --save electron-titlebar-windows
```



# API

### Requiring the module

```js
const titlebarWindows = require('electron-titlebar-windows');
```



### Configuration

The module takes a single optional `options` argument and exports the `TitleBar` class:

```js
const titlebar = new titlebarWindows(opts);
```

- options `object`
  - **darkMode** - `string` (optional) - **Light titlebar buttons (for dark backgrounds)**
  - **backgroundColor** - `string` (optional) - **Titlebar color in CSS color syntax**
  - **draggable** - `boolean` (optional) - **Titlebar enables dragging of contained window**



### Integration

```js
titlebar.appendTo(document);
```



### Events

`TitleBar` extends `EventEmitter` and emits the following events: `close`, `minimize`, `fullscreen`, `maximize`

Register handlers like so:

```js
titlebar.on('close', function(e) {
    console.log('close');
});
```



### Convenience

Use the ```element``` property for reference:

```js
titlebar.element.appendChild(document.createElement('div'));
```

Clean up after usage:

```js
titlebar.destroy();
```



## License

MIT © [sidneys](http://sidneys.github.io)



## Related

Based on [titlebar](https://github.com/kapetan/titlebar)
