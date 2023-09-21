# Pim Bootcamp 2023 Summer 1: HTML, Boostrap and Nuxt

## Initialize Nuxt project

```shell
pnpx nuxi@latest init pim-bc-23s1
```

## Install Bootstrap

### Install node modules

```shell
pnpm i bootstrap
```

### Prepare bootstrap as plugin

Create `plugins/bootstrap.client.ts` and edit like:

```typescript,plugins/bootstrap.client.ts
import bootstrap from 'bootstrap/dist/js/bootstrap.bundle'

export default defineNuxtPlugin(nuxtApp => {
    nuxtApp.provide('bootstrap', bootstrap)
})
```

### Register bootstrap plugin / styles

Edit `nuxt.config.ts` like:

```typescript,nuxt.config.ts
export default defineNuxtConfig({
  devtools: { enabled: true },
  css: [
    'bootstrap/dist/css/bootstrap.min.css'
  ],
  plugins: [
    '~/plugins/bootstrap.client.ts'
  ],
})
```