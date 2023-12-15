```shell
  npm install gh-pages --save-dev
```

```json

"homepage":"https://<your-github-username>.github.io/<your-repo-name>", 
"scripts": { 
"predeploy": "npm run build", 
"deploy": "gh-pages -d build"
}

```