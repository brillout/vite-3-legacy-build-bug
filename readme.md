Bug reproduction.

```bash
git clone git@github.com:brillout/vite-3-legacy-build-bug
cd vite-3-legacy-build-bug/
pnpm install
pnpm run build
```

Same as single line (copy-paste me):

```shell
git clone git@github.com:brillout/vite-3-legacy-build-bug && cd vite-3-legacy-build-bug/ && pnpm install && pnpm run build
```

Throws:

```
vite v3.0.0-beta.7 building SSR bundle for production...
✓ 78 modules transformed.
[commonjs] Unexpected token (12:17)
file: /home/romuuu/tmp/vite-3-legacy-build-bug/node_modules/.pnpm/vite-plugin-ssr@0.4.0-beta.45-legacy-build_vite@3.0.0-beta.7/node_modules/vite-plugin-ssr/dist/legacy-build/node/createPageRenderer.js:12:17
/home/romuuu/tmp/vite-3-legacy-build-bug/node_modules/.pnpm/acorn@8.7.1/node_modules/acorn/dist/acorn.js:3462
    var err = new SyntaxError(message);
              ^

SyntaxError: Unexpected token (12:17)
    at pp$4.raise (/home/romuuu/tmp/vite-3-cjs-bug/node_modules/.pnpm/acorn@8.7.1/node_modules/acorn/dist/acorn.js:3462:15)
```

Observe how `./node_modules/.pnpm/vite-plugin-ssr@0.4.0-beta.45-legacy-build_vite@3.0.0-beta.7/node_modules/vite-plugin-ssr/dist/cjs/node/plugin/plugins/buildConfig.js` has `legacy.buildRollupPluginCommonjs` set to `true`.
