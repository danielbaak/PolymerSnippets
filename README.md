# Polymer Snippets for Sublime

## Install

To install through [Package Control](http://wbond.net/sublime_packages/package_control),
search for **Polymer & Web Component Snippets**. If you still don't have Package Control in Sublime Text, [go get it](http://wbond.net/sublime_packages/package_control/installation).
It's pure awesomeness.

If you don't use Package Control, you can download the package and put it manually inside your `Packages` directory. It should work but will not update automatically.

## Polymer

### [pe] polymer element

```html
${1:<link rel="import" href="../polymer/polymer.html">}
<polymer-element name="${2}" attributes="${3}">
  <template>
    <style>
      :host {
        display: block;
      }
    </style>$4
  </template>
  <script>
    Polymer('$2', {
      
    });
  </script>
</polymer-element>
```

### [pen] polymer element noscript

```html
${1:<link rel="import" href="../polymer/polymer.html">}
<polymer-element name="${2}" noscript>
  <template>
    <style>
      :host {
        display: block;
      }
    </style>$4
  </template>
</polymer-element>
```

### [ipe] import polymer-element

```html
<link rel="import" href="${1:bower_components}/polymer-${2}/polymer-${2}.html">
```

### [ipu] import polymer-ui-element

```html
<link rel="import" href="${1:bower_components}/polymer-ui-${2}/polymer-ui-${2}.html">
```

## Web Components

### [tm] template
```html
<template$1>$0</template>
```

### [hi] html import

```html
<link rel="import" href="${0}">
```

### [ce] custom element

```javascript
var ${4:tmpl} = document.querySelector('${5:template}');

var ${1:WidgetProto} = Object.create(HTMLElement.prototype);

${1:WidgetProto}.createdCallback = function() {
  var root = this.createShadowRoot();
  root.appendChild(document.importNode(${4:tmpl}.content, true));
};

var ${2:Widget} = document.registerElement('${3:my-widget}', {
  prototype: ${1:WidgetProto}
});
```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## License

[MIT License](http://robdodson.mit-license.org/) © Rob Dodson
