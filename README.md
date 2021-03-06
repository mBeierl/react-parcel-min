# React 🙌 Parcel

The most minimalistic React starter code using [Parcel](https://github.com/parcel-bundler/parcel).

## Getting started

1. Install with yarn or npm:

`yarn` or `npm install`

2. Bundle and start development server:

`yarn start` or `npm run start`

3. It will tell you "Server running at http://localhost:1234". Go to this address in your browser.

4. Open `index.js` and change "Hello, world!" to something different. The change shows in your browser immediately!

5. Happy hacking!

## How does it work?

Parcel does the heavy lifting internally. [Learn more about Parcel](https://parceljs.org/getting_started.html). 

The only necessary config is for [babel](https://babeljs.io/), as we want to compile React's JSX to browser-compatible JavaScript code. That's why there's the `.babelrc` file and the corresponding preset [`babel-preset-react`](https://babeljs.io/docs/plugins/preset-react/) as dev-dependency in the `package.json` file.

## Beyond the Starter Code

### Support ES6, ES7 etc. using babel

If you want to add support for new ES specifications, you'd look up the appropriate babel preset or plugin. A popular example would be to add the ["env" preset](https://babeljs.io/docs/plugins/preset-env/), by running `yarn add --dev babel-preset-env` and adding `env` in your `.babelrc` file's preset array.

To add plugins, you will have to install the plugin, e.g. [babel-plugin-transform-class-properties](https://babeljs.io/docs/plugins/transform-class-properties/) to define your component's state outside of the component's constructor. After installing `yarn add --dev babel-plugin-transform-class-properties`, you have to modify your `.babelrc` again and add a new key `plugins`, which holds an array of plugins. Your .babelrc file will look like this:

```
{
  "presets": ["env", "react"],
  "plugins": ["transform-class-properties"]
}
```

### Production-specific transforms

Use your `.babelrc` file to further optimize your production build, e.g. by automatically removing all `debugger;` statements from your code. To do this, just edit the `.babelrc` file and add this part:

```
...
"env": {
  "production": {
    "plugins": ["transform-remove-debugger"]
  }
}
...
```

### Test with Jest

To test your code, you can use Jest, which works well with React with little set-up.

- `yarn add --dev jest babel-jest babel-preset-es2015 babel-preset-react react-test-renderer`
- in `package.json`, add `"test": "jest"` to your scripts
- in `.babelrc`, add `"es2015"` to the presets array
- create test files, either in [`__test__` folders or with the `*.test.js` or `*.spec.js` filename pattern](https://facebook.github.io/jest/docs/en/configuration.html#testmatch-array-string)
- `yarn test`

To learn more about Jest, read their [Getting Started](https://facebook.github.io/jest/docs/en/getting-started.html) guide and their [Testing React Apps](https://facebook.github.io/jest/docs/en/tutorial-react.html) guide. You can also configure Jest, have a look at the [Jest Configuration](https://facebook.github.io/jest/docs/en/configuration.html) docs.

### TODO

*TODO:* In this section we will discuss where you could take this simple starter code.

Possible topics:
- how to add testing
- using PostCSS and PostHTML
- using parcel's built-in code splitting
- ...

**Contributions welcome!**

## Other React Starter-Projects
- Also /w parcel, but using more config: [react-parcel-example](https://github.com/jaredpalmer/react-parcel-example)
- Famous CRA, using webpack internally: [create-react-app](https://github.com/facebookincubator/create-react-app)

## Contributors

This repo is meant to deliver the simplest possible React starter code using the parcel bundler. Keep this in mind for code contributions.

The README can be used to show how this starter code could be extended.

## License

MIT
