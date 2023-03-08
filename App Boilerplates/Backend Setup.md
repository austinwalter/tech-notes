
#### Add ReadMe and License
```
touch README.md
touch LICENSE
```

#### Initialize Git
```
git init
touch .gitignore
git add -A
git commit -m "Initial commit"
```

`.gitignore`
```
node_modules/
build/
lib/
dist/
docs/
.idea/*

.DS_Store
coverage
*.log
```

#### Initialize `package.json` with `npm`
```
npm init
```

```
package name: (node-boilerplate) 
version: (1.0.0) 0.0.0
description: A Node.js project
entry point: (index.js) index.ts
test command: 
git repository: 
keywords: 
author: austinwalter <awalterdev@gmail.com>
license: (ISC) MIT
```

#### Install TypeScript and Linter
```
pnpm add -D typescript @types/node ts-node
pnpm add -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin
```

#### Jest
```
pnpm add -D jest ts-jest @types/jest
```

#### Initialize TypeScript Config
```
npx tsc --init
```

```
Created a new tsconfig.json with:

  target: es2016
  module: commonjs
  strict: true
  esModuleInterop: true
  skipLibCheck: true
  forceConsistentCasingInFileNames: true

You can learn more at https://aka.ms/tsconfig
```

```
npx tsc --watch
```

#### Initialize Linter
```
npx eslint --init
```

```
You can also run this command directly using 'npm init @eslint/config'.
✔ How would you like to use ESLint? · problems
✔ What type of modules does your project use? · esm
✔ Which framework does your project use? · none
✔ Does your project use TypeScript? · No / Yes
✔ Where does your code run? · node
✔ What format do you want your config file to be in? · JSON
```

```
printf "node_modules\ndist" > .eslintignore
```

```
npx eslint .
npx eslint --ignore-path .eslintignore --ext .ts .
```

```
// package.json
{
  // ...
  "scripts": {
    "lint": "eslint --ignore-path .eslintignore --ext .js,.ts ."
   },
  // ...
}
```

```
pnpm run lint --fix
```

#### Prettier
```
pnpm add -D --exact prettier
printf "{}" > .prettierrc.json
touch .prettierignore
```

`.prettierignore`
```
# Ignore artifacts:
build
coverage
```

#### Husky
```
pnpm dlx husky-init && pnpm install
npx husky add .husky/pre-commit "npx format"
```

https://blog.typicode.com/husky-git-hooks-javascript-config/
https://medium.com/@oxodesign/node-js-express-with-typescript-eslint-jest-prettier-and-husky-part-2-f129188ce404
https://www.metachris.com/2021/04/starting-a-typescript-project-in-2021/

## References
https://github.com/tsconfig/bases
https://typestrong.org/ts-node/docs/installation
https://medium.com/@oxodesign/node-js-express-with-typescript-eslint-jest-prettier-and-husky-part-2-f129188ce404
https://prettier.io/docs/en/install.html
https://typicode.github.io/husky/#/
https://github.com/othneildrew/Best-README-Template
https://github.com/jsynowiec/node-typescript-boilerplate
https://nodejs.org/en/docs/guides/getting-started-guide/
https://www.digitalocean.com/community/tutorials/typescript-new-project
https://www.metachris.com/2021/04/starting-a-typescript-project-in-2021/
