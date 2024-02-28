# esbuild-jest

### A Jest transformer using esbuild
With this transformer you can use and transform (ts, js, tsx and jsx) files

## Install

```bash
npm install --save-dev @lgse/esbuild-jest esbuild
```

#### Setting up Jest config file

esbuild-jest transformer should be used in your Jest config file like this:

```js
{
  "transform": {
    "^.+\\.tsx?$": "@lgse/esbuild-jest"
  }
}
```

#### Setting up Jest config file with transformOptions
```typescript
export interface Options {
  jsxFactory?: string
  jsxFragment?: string
  sourcemap?: boolean | 'inline' | 'external'
  loaders?: {
    [ext: string]: Loader
  },
  target?: string
  format?: string
  define?: { [key: string]: string }
}
```

```js
{
  "transform": {
    "^.+\\.tsx?$": [ 
      "@lgse/esbuild-jest", 
      { 
        sourcemap: true,
        loaders: {
          '.spec.ts': 'tsx'
        }
      } 
    ]
  }
}
```

> Note: if you are using tsconfig.json and jsconfig.json with "paths", Please look `alias-hq` and there documentation https://github.com/davestewart/alias-hq/blob/master/docs/integrations.md

