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

## SYNPOSIS

### `constructor()`

Constructs a new chop object. Returns this object.

```javascript
const chop = new SealChopObject();
```

### `.toJSON()`

Returns a JSON string.

```javascript
const json = chop.toJSON();

// output
{
  "p": "#ffffff",
  "b": "#33aa55",
  "f": "#ffffff",
  "i": "#003300",
  "x": "姓名字"
}
```

### `.toString()`

Same as `.toJSON()`.

```javascript
const str = chop.toString();
const str = '' + chop;
```

### `.toDataURL()`

Returns a base64 data string.

```javascript
// set the name, then get the base64 url
const img = new Image();
const url = chop.setName('姓名字').toDataURL();
img.src = url;
```

### `.asImageElement()`

Returns an HTML Image element with a chop in it.

```javascript
const chop = new SealChopObject();
const img = chop.setName('姓名字').asImageElement();
document.querySelector('#motet-sealchop').innerHTML = img;
```

### `.setName(string)`

Set `name` with a valid Chinese characters (1, 2, 3 or 4 characters). All other characters are removed. If no characters remain, it is set to `null`. Also, returns this object.

### `.setPaperColor(string)`

Sets `paper` color with a valid 6-digit hex color (e.g., `#ffffff`). Otherwise, sets it to `null`. Also, returns this object.

### `.setBackgroundColor(string)`

Sets `background` color with a valid 6-digit hex color (e.g., `#ffffff`). Otherwise, sets it to `null`. Also, returns this object.


### `.setForegroundColor(string)`

Sets `foreground` color with a valid 6-digit hex color (e.g., `#ffffff`). Otherwise, sets it to `null`. Also, returns this object.


### `.setInkColor(string)`

Sets `ink` color with a valid 6-digit hex color (e.g., `#ffffff`). Otherwise, sets it to `null`. Also, returns this object.


## Deprecated methods

### `.setXingMing(string)`

Same as `.setName()`. This method will be removed soon.


