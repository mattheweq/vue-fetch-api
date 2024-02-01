## /|\v/|\ Discography

[LIVE SITE](https://vue.olk1.com)

![ALT:preview](preview.png)

## Install tailwindcss
```
npm install -D tailwindcss
npx tailwindcss init
```
## add to tailwind.config.js
```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js,vue}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
## add to main.css
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```


```sh
npx create-vue@latest .
```
```sh
npm run build
```

## deploy dist folder to static server