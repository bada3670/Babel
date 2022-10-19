## Usage

Suppose you want to change your ES6 codes into previous version. You have to download many plugins and write the plugins in CLI or in a configuration file.

To make the cumbersome process simpler, we can make and use a bundle of plugins and/or config options. And the bundle is called 'preset'.

## Official Presets

@babel/preset-env: for compiling ES2015+ syntax

@babel/preset-typescript: for TypeScript

@babel/preset-react: for React

@babel/preset-flow: for Flow

## Example

### Presets Which Will Be Used

We will use @babel/preset-typescript, @babel/preset-react. Please install them as dev dependencies.

### Using with CLI

Please write this in |App.tsx|.

```tsx
function App(num: number) {
  return <div>{num}</div>;
}
```

Also, please make |result.js| file.

If you run this code,

```sh
$ npx babel App.tsx --presets=@babel/preset-react,@babel/preset-typescript -o result.js
```

you will get this result in |result.js|.

```js
function App(num) {
  return /*#__PURE__*/ React.createElement('div', null, num);
}
```

### Using with a Configuration File

Please write this in |App.tsx|. (same as above)

```tsx
function App(num: number) {
  return <div>{num}</div>;
}
```

Also, please make |result.js| file. (same as above)

Also, please write this in |app.config.json|.

```json
{
  "presets": ["@babel/preset-react", "@babel/preset-typescript"]
}
```

If you run this code,

```sh
$ npx babel App.tsx --config-file ./app.config.json -o result.js
```

you will get this result in |result.js|.

```js
function App(num) {
  return /*#__PURE__*/ React.createElement('div', null, num);
}
```
