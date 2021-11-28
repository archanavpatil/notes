## Tailwind installation

- Create project: yarn create next-app --typescript 
- yarn add --dev tailwindcss@latest postcss@latest postcss-cli autoprefixer@latest
- Install VS Code extensions: headwind, Tailwind CSS IntelliSense
- Create Tailwind configuration file: npx tailwindcss init -p
- To remove unused styles, use following in configure tailwind.config.css - ``` purge: ['./pages/**/*.{js,ts,jsx,tsx}', './components/**/*.{js,ts,jsx,tsx}'] ```
- Include tailwind in the application, in next app include it in _app.tsx - import 'tailwindcss/tailwind.css'
- Create a file: styles/tailwind.css
- include following code to styles/tailwind.css
```
@tailwind base;
@tailwind components;
@tailwind utilities;
```
- We can add default styling here. Base layer contains default tags styling. 
- New properties (like font-type, size, colors) can be added or overrides in tailwind.config.js
- Add [patterns](https://heropatterns.com/) Its optional.
- Add own color palette
```
//tailwind.config.js

const colors = require('tailwindcss/colors')
then you can extend or modify color inside theme in tailwind.config.js
```
- tailwind [source code](https://github.com/tailwindlabs/tailwindcss/releases)
- To debug screens use [debug-screen](https://github.com/jorenvanhee/tailwindcss-debug-screens), run ```yarn add --dev tailwindcss-debug-screens``` and add following code in tailwind.config.js
```
module.exports = {
  //...
  plugins: [
    require('tailwindcss-debug-screens'),
  ]
}
```
- To disable any plugins, add following code in tailwind.config.js
```
module.exports = {
  //...
  corePlugins: {
    container: false,
  }
}
```
- To add new plgin, add following code in tailwind.config.js
```
module.exports = {
  plugins: function ({ addComponents }) {
    addComponents({
      '.container': {
        maxWidth: '100%',
        '@screen desktop': {
          maxWidth: '1140px',
        },
      }
    })
  }
}
```
