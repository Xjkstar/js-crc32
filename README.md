# 修正会出现负数的bug
JavaScript采用IEEE 754标准定义的64位浮点格式表示数字，因此它的数字都是有符号的。在运算过程中虽然都使用了>>>(Zero-fill right shift)，但是在最后返回结果的时候没有将有符号数转化为无符号数，因此出现了负数的情况。

解决方法很简单，把上述源码里的：
```js
return C ^ -1;
```
全部替换为
```js
return (C ^ (-1)) >>> 0;
```

# crc32
参见[SheetJS/js-crc32](https://github.com/SheetJS/js-crc32)

## Badges

[![Sauce Test Status](https://saucelabs.com/browser-matrix/crc32.svg)](https://saucelabs.com/u/crc32)

[![Build Status](https://travis-ci.org/SheetJS/js-crc32.svg?branch=master)](https://travis-ci.org/SheetJS/js-crc32)
[![Coverage Status](http://img.shields.io/coveralls/SheetJS/js-crc32/master.svg)](https://coveralls.io/r/SheetJS/js-crc32?branch=master)
[![Dependencies Status](https://david-dm.org/sheetjs/js-crc32/status.svg)](https://david-dm.org/sheetjs/js-crc32)
[![NPM Downloads](https://img.shields.io/npm/dt/crc-32.svg)](https://npmjs.org/package/crc-32)
[![ghit.me](https://ghit.me/badge.svg?repo=sheetjs/js-xlsx)](https://ghit.me/repo/sheetjs/js-xlsx)
[![Analytics](https://ga-beacon.appspot.com/UA-36810333-1/SheetJS/js-crc32?pixel)](https://github.com/SheetJS/js-crc32)
