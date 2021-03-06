# Polymer Snippets for Atom

![banner](http://s12.postimg.org/opgzpvtpp/banner.png)

![Demo](http://imageshack.com/a/img513/5969/4hz.gif)

## Install
Go to `atom > Preferences...` then search for Polymer Snippets in Packages tab.

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

### [hic] html import core-* element

```html
<link rel="import" href="${1:bower_components}/core-${2}/core-${2}.html">
```

### [hip] html import paper-* element

```html
<link rel="import" href="{1:bower_components}/paper-$2/paper-$2.html">
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

### [sh] ::shadow
```css
::shadow ${2:target} {
  $0
}
```

### [sd] /deep/
```css
/deep/ ${2:target} {
  $0
}
```

### [cn] content::content
```css
${1:content}::content ${2:target} {
	$0
}
```

### [ho] :host
```css
:host$0
```

### [hc] :host-context()
```css
:host-context($0)
```

### [pf] polyfill-next-selector
```css
polyfill-next-selector { content: '${1::host > .foo}'; }$0
```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## License

[MIT License](http://robdodson.mit-license.org/) Â© Rob Dodson
