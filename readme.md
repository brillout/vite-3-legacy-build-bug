Bug reproduction.

```bash
git clone git@github.com:brillout/vite-3-babel-bug
cd vite-3-babel-bug/
pnpm install
pnpm run build
```

Same as single line (copy-paste me):

```shell
git clone git@github.com:brillout/vite-3-babel-bug && cd vite-3-babel-bug/ && pnpm install && pnpm run build
```

Throws:

```
vite v3.0.0-beta.5 building for production...
✓ 116 modules transformed.
[vite:react-babel] /home/romuuu/tmp/vite-3-bug-dependency-transpiling/node_modules/.pnpm/vikepress@0.0.21_biqbaboplfbrettd7655fr4n2y/node_modules/vikepress/src/utils/Emoji/Emoji.ts: Support for the experimental syntax 'flow' isn't currently enabled (7:8):

   5 |
   6 | export { Emoji }
>  7 | export type { EmojiName }
     |        ^
   8 |
   9 | type EmojiName =
  10 |   | 'warning'

Add @babel/preset-flow (https://github.com/babel/babel/tree/main/packages/babel-preset-flow) to the 'presets' section of your Babel config to enable transformation.
If you want to leave it as-is, add @babel/plugin-syntax-flow (https://github.com/babel/babel/tree/main/packages/babel-plugin-syntax-flow) to the 'plugins' section to enable parsing.
file: /home/romuuu/tmp/vite-3-bug-dependency-transpiling/node_modules/.pnpm/vikepress@0.0.21_biqbaboplfbrettd7655fr4n2y/node_modules/vikepress/src/utils/Emoji/Emoji.ts:7:7
```

This only happens with Vite 3. See the [branch `vite-2`](https://github.com/brillout/vite-3-babel-bug/tree/vite-2) which is the same but uses Vite 2 and works.
