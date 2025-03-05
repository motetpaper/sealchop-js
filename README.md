# sealchop-js

## Quick Start

Start with two files: `app.js` and `index.html`.

```bash
├── app.js
└── index.html
```

### `index.html`

```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title></title>
</head>
<body>
<div id="motet-sealchop"></div>
<script type="module" src="/app.js"></script>
</body>
</html>
```

### `app.js`

Add a single line to import the object. Start making chops instantly.

```javascript
import { SealChopObject } from 'https://motetpaper.github.io/sealchop-js/SealChopObject.js'

const chop = new SealChopObject();
const img = chop.setName('姓名字').asImageElement();
document.querySelector('#motet-sealchop').innerHTML = img;
```

Done! That was easy.

## Do more

```javascript
// create a new seal chop object
const chop = new SealChopObject();

// export the chop as a JSON string
const json = chop.toJSON();

// toString() also exports as a JSON string
const str = chop.toString();
const str = '' + chop;

// set the name, then get the base64 url
const img = new Image();
const url = chop.setName('姓名字').toDataURL();
img.src = url;

// export as Image element
// put into a div element
const img = chop.setName('姓名字').asImageElement();
document.querySelector('#chop').innerHTML = img;
```
