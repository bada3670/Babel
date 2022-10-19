## Usage

Let's save the result not in a shell, but in another file.

## Example

### Settings

|app.js|

```js
const increment = (num) => num + 1;
```

|app.confing.json|

```json
{
  "plugins": [
    "@babel/plugin-transform-arrow-functions",
    "@babel/plugin-transform-block-scoping"
  ]
}
```

### Execution

Please make |result.js| where the result will be written.

If you run this,

```sh
$ npx babel app.js --config-file ./app.config.json -o result.js
```

※ Also, you can use '--out-file' instead of '-o'.

|result.js| will look like this.

```js
var increment = function (num) {
  return num + 1;
};
```
