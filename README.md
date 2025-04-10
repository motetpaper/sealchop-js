> ## **NOTE:** This is the software object for developers. To create a seal chop design online, please use [the Chinese Korean Seal Chop Generator](https://motetpaper.github.io/chop/).

# sealchop-js

## Purpose

**`sealchop-js`** is designed to create Chinese seal chops for display on web pages (and blogs) or for print on paper stationery (e.g., business cards, letterheads, envelopes, notebooks, etc.). 

This is the web version, designed as a JavaScript module, as opposed to the other versions designed for GitHub Actions workflows or RESTful APIs.

## Quick Start

We start with two files: `app.js` and `index.html`.

Here is the directory structure:
```bash
├── app.js
└── index.html
```

### `index.html`

Copy and paste the following into your empty `index.html` file.

```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
</head>
<body>
<div id="motet-sealchop"></div>
<script type="module" src="/app.js"></script>
</body>
</html>
```

### `app.js`

Copy and paste the following into your `app.js`. As you can see, a single line imports the object into the module. Now, you can start making Chinese seal chops.

```javascript
import { SealChopObject } from 'https://motetpaper.github.io/sealchop-js/SealChopObject.js'

const chop = new SealChopObject();
const img = chop.setName('姓名字').asImageElement();
document.querySelector('#motet-sealchop').innerHTML = img;
```

That was easy.

Now, let us start a local web server to see this in action.

In the same directory as `index.html`, start a localhost web server with a [secure context][sec].

For example:
```bash
php -S localhost:8888
```

[sec]: https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts


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

> **NOTE:** These methods will be removed soon.

### `.setXingMing(string)`

Same as `.setName()`. This method will be removed soon.


