## Usage

So far, we had to write the name of the configuration file. However, we can use a default configuration file so that we don't have to write the file name.

The name of the file is |babel.config.json|.

## Example

Please write this in |App.tsx|.

```tsx
function App(num: number) {
  return <div>{num}</div>;
}
```

Also, please make |result.js| file.

Also, please write this in |babel.config.json|.

```json
{
  "presets": ["@babel/preset-react", "@babel/preset-typescript"]
}
```

If you run this code,

```sh
$ npx babel App.tsx -o result.js
```

|result.js| will be like this.

```js
function App(num) {
  return /*#__PURE__*/ React.createElement('div', null, num);
}
```
