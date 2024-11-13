# vue-tumblr

## A small application which runs vue and connects to the Tumblr API

An `.env` file in the root directory contains the following keys that you will need to populate in order to authenticate the app. Use the `.env.example` as a starting point. 

- VITE_TUMBLR_API
- VITE_TUMBLR_API_KEY
- VITE_TUMBLR_BLOG_URL

The last one can be any tumblr url. 

### Recommended IDE Setup

This template should help get you started developing with Vue 3 in Vite.

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

### Customize configuration

See [Vite Configuration Reference](https://vite.dev/config/).

### Project Setup

```sh
bun install
```

#### Compile and Hot-Reload for Development

```sh
bun dev
```

#### Compile and Minify for Production

```sh
bun build
```

#### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
bun test:unit
```

#### Lint with [ESLint](https://eslint.org/)

```sh
bun lint
```
