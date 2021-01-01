# npm

## Summary

| Command | Flag | Description |
| --- | --- | ----------- |
| npm init |  | Create a new npm project/package  |
| | -y  | Initialize default configuration |
| npm i [package] |  | Install a package |
| | -D | install as devDependency |
|| -g | install globally|

## Best Practices

## Notes

#### Initialization

```
cd code
mkdir mathjs-test
cd mathjs-test
touch index.js
code .
npm init
node index.js
```

Index.js:
```
const { sqrt } = require('mathjs')

console.log(sqrt(-4).toString())  // 2i
```

- [Setting up new project](https://philna.sh/blog/2019/01/10/how-to-start-a-node-js-project/)
- [HelloWorld with Node and Express](https://medium.com/@adnanrahic/hello-world-app-with-node-js-and-express-c1eb7cfa8a30)


## Useful links

- [npm Cheat Sheet - Most Common Commands and nvm](https://www.freecodecamp.org/news/npm-cheat-sheet-most-common-commands-and-nvm/)
