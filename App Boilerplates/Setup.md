
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

#### Initialize `package.json` with `yarn`
```
yarn init
```

```
question name (node-boilerplate): 
question version (1.0.0): 0.0.0
question description: A Node.js project
question entry point (index.js): index.ts
question repository url: 
question author (austinwalter <awalterdev@gmail.com>): 
question license (MIT): 
question private: false
success Saved package.json
```

#### Install TypeScript, linter and Jest
```
yarn add -D typescript @types/node ts-node
yarn add -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin
yarn add -D jest ts-jest @types/jest
```

#### Initialize TypeScript Config
```
npx typescript --init
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

#### Initialize Linter
```
npx eslint --init
```

```
You can also run this command directly using 'npm init @eslint/config'.
✔ How would you like to use ESLint? · style
✔ What type of modules does your project use? · esm
✔ Which framework does your project use? · none
✔ Does your project use TypeScript? · No / <Yes>
✔ Where does your code run? · node
✔ How would you like to define a style for your project? · guide
✔ Which style guide do you want to follow? · standard-with-typescript
✔ What format do you want your config file to be in? · JavaScript
The config that you've selected requires the following dependencies: ...
✔ Would you like to install them now? · <No> / Yes
Successfully created .eslintrc.js file in ...
```

```
yarn add -D eslint-config-standard-with-typescript
yarn add -D @typescript-eslint/eslint-plugin eslint-plugin-import eslint-plugin-n eslint-plugin-promise
```

#### Prettier

```
yarn add -D prettier
```

## References
https://github.com/tsconfig/bases
https://typestrong.org/ts-node/docs/installation
https://medium.com/@oxodesign/node-js-express-with-typescript-eslint-jest-prettier-and-husky-part-2-f129188ce404