Bug reproduction.

```bash
git clone git@github.com:brillout/vite-3-cjs-bug
cd vite-3-cjs-bug/
pnpm install
pnpm run build
```

Same as single line (copy-paste me):

```shell
git clone git@github.com:brillout/vite-3-cjs-bug && cd vite-3-cjs-bug/ && pnpm install && pnpm run build
```

Throws:

```
vite v3.0.0-beta.5 building SSR bundle for production...
✓ 56 modules transformed.
'escapeInject' is not exported by node_modules/.pnpm/vite-plugin-ssr@0.4.0-beta.43_vite@3.0.0-beta.5/node_modules/vite-plugin-ssr/dist/cjs/node/index.js, imported by node_modules/.pnpm/vikepress@0.0.21_biqbaboplfbrettd7655fr4n2y/node_modules/vikepress/src/algolia/DocSearch.ts
file: /home/romuuu/tmp/vite-3-babel-bug/node_modules/.pnpm/vikepress@0.0.21_biqbaboplfbrettd7655fr4n2y/node_modules/vikepress/src/algolia/DocSearch.ts:1:0
1: import { escapeInject } from 'vite-plugin-ssr'
   ^
2: import { PageContextResolved } from '../config/resolvePageContext'
file:///home/romuuu/tmp/vite-3-babel-bug/node_modules/.pnpm/rollup@2.75.7/node_modules/rollup/dist/es/shared/rollup.js:1858
        base = Object.assign(new Error(base.message), base);
                             ^

Error: 'escapeInject' is not exported by node_modules/.pnpm/vite-plugin-ssr@0.4.0-beta.43_vite@3.0.0-beta.5/node_modules/vite-plugin-ssr/dist/cjs/node/index.js, imported by node_modules/.pnpm/vikepress@0.0.21_biqbaboplfbrettd7655fr4n2y/node_modules/vikepress/src/algolia/DocSearch.ts
```

The Vite config can be edited at `node_modules/vikepress/vite.config.ts`.
