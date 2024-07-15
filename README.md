# TailwindCSS Jekyll site

a more stripped down version of [https://github.com/mzrnsh/jekyllwind/tree/main](https://github.com/mzrnsh/jekyllwind/tree/main)

## what I did here

jekyll new jekyll-store-display

npm install

bundle install

bundle add jekyll-postcss


added the following files that aren't there in the Jekyll install:

* `tailwind.config.js`
* `postcss.config.js`
* `_layouts/default.html` or whatever you want your layout to be
* `assets/css/main.css` with the below contents
* renamed `index.markdown` to `index.md` just because I'm processing *.md files
## file contents

### tailwind.config.js

```js
module.exports = {
  content: [
    './_drafts/**/*.html',
    './_includes/**/*.html',
    './_layouts/**/*.html',
    './_posts/*.md',
    './*.md',
    './*.html',
  ],
  theme: {
    [whatever theme values you want to add here]
  },
  plugins: []
}
```

### postcss.config.js

```js
module.exports = {
  plugins: [
    require('tailwindcss'),
    require('autoprefixer'),
    ...(process.env.JEKYLL_ENV == 'production'
      ? [require('cssnano')({ preset: 'default' })]
      : [])
  ]
}

```

### assets/css/main.css

This is the default stuff you need to make tailwind compile

```css
---
---

@tailwind base;
@tailwind components;
@tailwind utilities;
```

## Next actions

go crazy.