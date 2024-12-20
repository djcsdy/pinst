# pinst [![Node.js CI](https://github.com/typicode/pinst/workflows/Node.js%20CI/badge.svg)](https://github.com/typicode/pinst/actions) [![npm](https://img.shields.io/npm/v/pinst.svg)](https://www.npmjs.com/package/pinst)

> `pinst` lets you have `postinstall` hook that runs only in dev 🍺

__Important__ if your project is using npm or pnpm, you can achieve the desired effect by setting a `prepare` hook instead. `pinst` is mainly useful for Yarn 2+ since it doesn't support `prepare` hook. See https://yarnpkg.com/advanced/lifecycle-scripts

## Usage

```js
// package.json
{
  "scripts": {
    "postinstall": "<some dev only command>",
  }
}
```

Before publishing your package, run `pinst --disable`. It will rename the `postinstall` script to `_postinstall` (disabled).

After publishing your package, run `pinst --enable`. It will rename the script back to `postinstall` (enabled).

**Caution**: [It is not safe to run `pinst` in the `prepack` script](https://gist.github.com/djcsdy/3ca078e23fdac4c50e077c84e8284a95).

## CLI

`pinst` accepts the following flags:

```
--enable, -e   Enable postinstall hook
--disable, -d  Disable postinstall hook
--silent, -s
```

## Tips

By inverting commands, you can also use `pinst` to enable `postinstall` for your users only and not yourself.

`pinst` also supports `install` alias.

## License

MIT - [Typicode :cactus:](https://github.com/typicode)
