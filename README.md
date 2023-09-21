# Pim Bootcamp 2023 Summer 1, Program 1
[HTML](https://html.spec.whatwg.org/multipage/), [Bootstrap](https://getbootstrap.com/) and [Nuxt](https://nuxt.com/)

## Initialize Nuxt project

```shell
pnpx nuxi@latest init pim-bc-23s1
```

[See files after this section](https://github.com/shimane-u-pim/bootcamp2023s1-nuxt/tree/11c6f33d1a79ee752aa797655f686f08e088c638)

## Install Bootstrap

[See files after this section](https://github.com/shimane-u-pim/bootcamp2023s1-nuxt/tree/0ec2412a00e228ca242feaf76fafc6a18c37b88a)

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

## Add NuxtPage

[See files after this section](https://github.com/shimane-u-pim/bootcamp2023s1-nuxt/tree/54024d5d108319b71bab87e47e15bf8223a3fb54)

### Create Nav component

Create `components/Nav.vue` like:

```vue,components/Nav.vue
<template>
    <NuxtLink to="/">Home</NuxtLink>
    |
    <NuxtLink to="/about">About</NuxtLink>
</template>
```

### Create index page

Create `pages/index.vue` like:

```vue,page/index.vue
<template>
    <h1>Hello Index</h1>
</template>
```

### Create about page

Create `pages/about.vue` like:

```vue,page/about.vue
<template>
    <h1>hello about</h1>
</template>
```

### Edit app.vue

Edit `app.vue` like:

```vue,app.vue
<template>
    <Nav />
    <NuxtPage />
</template>
```
