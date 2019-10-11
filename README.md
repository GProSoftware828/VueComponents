# components

## Project setup

Please follow these steps to see what I've been tinkering around in with Vue as of late:
1. Go to release 2.0.0 and download zip to desktop.
2. Uncompress zip.
3. Open the folder in Visual Studio Code
4. Open the terminal under View
5. Make sure the terminal is in the root directory; run npm install just to be safe, then run npm run serve.
6. This should show the build in localhost:8080; if not please confirm in the file package.json line 6 is asking for serve rather than dev, for the npm run command.
```
vue create components #vue create folder-name
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
