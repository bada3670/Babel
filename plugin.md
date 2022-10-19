## Usage

If you want to use a specific function, then you can use the plugin of the function.

## Where Is the List of the Plugins?

Babel homepage > Docs > (the left bar) > Config Reference > Plugins List

## Example

### Plugins Which Will Be Used

Please install these as dev dependencies.

- @babel/plugin-transform-arrow-functions: This will change arrow functions into regular functions.

- @babel/plugin-transform-block-scoping: This will change 'let' or 'const' into 'var'.

### Using with CLI

Please write this in |app.js|.

```js
const increment = (num) => num + 1;
```

If you run this,

```sh
$ npx babel app.js --plugins=@babel/plugin-transform-arrow-functions,@babel/plugin-transform-block-scoping
```

you will get this result.

```sh
var increment = function (num) {
  return num + 1;
};
```

### Using with a Configuration File

Please write this in |app.js|. (same as above)

```js
const increment = (num) => num + 1;
```

Also, please write this in |app.config.json|

```json
{
  "plugins": [
    "@babel/plugin-transform-arrow-functions",
    "@babel/plugin-transform-block-scoping"
  ]
}
```

If you run this,

```sh
$ npx babel app.js --config-file ./app.config.json
```

you will get this result.

```sh
var increment = function (num) {
  return num + 1;
};
```
