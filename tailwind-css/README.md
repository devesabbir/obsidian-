#### Tailwind css installation 

```shell
# create project with tailwind, vite & react
 npm create vite@latest my-project -- --template react 
```


```shell
# install tailwind css, postcss, autoprefixer as dev dependencies 
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

- After init `npx tailwindcss init -p` tailwind and postcss(-p) two configuration files will be created in the project directory
   1. `tailwind.config.js`
   2. `postcss.config.js`



###### In `tailwind.config.js` file

```javascript
 /** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

###### In `index.css` file

```css
 @tailwind base;
 @tailwind components;
 @tailwind utilities;
```