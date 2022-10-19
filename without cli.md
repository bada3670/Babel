## Usage

We can use Babel without CLI. Let me show you how to do it.

## Example

### Settings

|@babel/preset-env|

Please install it.

|app.js|

```js
const increment = (num) => num + 1;
```

|result.js|

Nothing in it.

### Execution

|execute.js|

```js
const babel = require('@babel/core');

const path = require('path');
const fs = require('fs');

const inputPath = path.join(__dirname, 'app.js');
const theContent = fs.readFileSync(inputPath);

const { code } = babel.transformSync(theContent, {
  presets: ['@babel/preset-env'],
});

const outputPath = path.join(__dirname, 'result.js');
fs.writeFileSync(outputPath, code);
```

Please run the above file.

```sh
$ node execute
```

Then, the result will be like this.

|result.js|

```js
'use strict';

var increment = function increment(num) {
  return num + 1;
};
```
