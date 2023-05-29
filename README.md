## Forked by [Dinesh Solanki](https://github.com/DineshSolanki)

This fork update the pako dependency to 2.0.0, see https://github.com/Hopding/pdf-lib/issues/689.

Install with: `npm i @dineshsolanki/standard-fonts`

<hr/>
<h1>
  standard-fonts

  <br />

  <!-- NPM Version -->
  <a href="https://www.npmjs.com/package/standard-fonts">
    <img
      src="https://img.shields.io/npm/v/@pdf-lib/standard-fonts.svg?style=flat-square"
      alt="NPM Version"
    />
  </a>

  <!-- Prettier Badge -->
  <a href="https://prettier.io/">
    <img
      src="https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square"
      alt="Prettier Badge"
    />
  </a>
</h1>

> Collection of metrics and encodings for the standard 14 PDF fonts

This project is a fork of [`afm`](https://github.com/chbrown/afm) and was created for use in [`pdf-lib`](https://github.com/Hopding/pdf-lib). This forks exists for two primary reasons:

1. The original project did not include mappings from Unicode to WinAnsi/ZapfDingbats/Symbol encodings.
2. The font metrics included in the original project were uncompressed (not ideal for usage in `pdf-lib`).

## Usage
```js
import { Font, FontNames, Encodings } from '@pdf-lib/standard-fonts';

const codePoint = '∑'.charCodeAt(0);

const glyph = Encodings.Symbol.encodeUnicodeCodePoint(codePoint);
glyph // => { code: 229, name: 'summation' }

const font = Font.load(FontNames.Symbol);
const width = font.getWidthOfGlyph(glyph.name);
width // => 713
```

## Installation
### NPM Module
To install the latest stable version:
```bash
# With npm
npm install --save @dineshsolanki/standard-fonts

# With yarn
yarn add @dineshsolanki/standard-fonts
```
This assumes you're using [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/lang/en/) as your package manager.

```javascript
// NPM module
import { Font, FontNames, Encodings } from '@pdf-lib/standard-fonts';
const font = Font.load(FontNames.HelveticaBold);
const encoding = Encodings.WinAnsi;

// UMD module
var font = StandardFonts.Font.load(StandardFonts.FontNames.HelveticaBold);
var encoding = StandardFonts.Encodings.WinAnsi;
```

## License
[MIT](https://choosealicense.com/licenses/mit/)

## Original Repo's License

Copyright 2015–2018 Christopher Brown.
[MIT Licensed](https://chbrown.github.io/licenses/MIT/#2015-2018).
