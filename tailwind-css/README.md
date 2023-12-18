#### Tailwind CSS installation with React


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

#tailwindCss #react-tailwind 


##### Tailwind Css installation with CLI

```shell
  # install as dev dependency 
  npm install -D tailwindcss
```


```shell
  # init tailwind css 
  npx tailwindcss init
```

###### in main css file

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

```shell
# run build command in terminal 
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch
```

# or

###### In `package.json file`

```JSON
 "scripts": {
    "tail" : "npx tailwindcss -i ./src/index.css -o ./output/style.css --watch"
  },
```

```shell
# run this command in terminal
 npm run tail
```
