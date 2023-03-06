```
touch README.md
touch LICENSE
```

```
git init
touch .gitignore
git add -A
git commit -m "Initial commit"
```

Initialize `.gitignore`

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

Initialize `package.json` with `yarn`

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

Install TypeScript, linter and Jest

```
yarn add -D typescript @types/node ts-node
yarn add -D eslint @typescript-eslint/parser @typescript-eslint/eslint-plugin
yarn add -D jest ts-jest @types/jest
```

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
npx eslint --init
```

```
You can also run this command directly using 'npm init @eslint/config'.
? How would you like to use ESLint? … 
  To check syntax only
  To check syntax and find problems
▸ To check syntax, find problems, and enforce code style
```

```
✔ How would you like to use ESLint? · style
? What type of modules does your project use? … 
▸ JavaScript modules (import/export)
  CommonJS (require/exports)
  None of these
```

```
✔ How would you like to use ESLint? · style
✔ What type of modules does your project use? · esm
? Which framework does your project use? … 
  React
  Vue.js
▸ None of these
```

```
✔ How would you like to use ESLint? · style
✔ What type of modules does your project use? · esm
✔ Which framework does your project use? · none
? Does your project use TypeScript? ‣ No / Yes
```

```
✔ How would you like to use ESLint? · style
✔ What type of modules does your project use? · esm
✔ Which framework does your project use? · none
✔ Does your project use TypeScript? · No / Yes
? Where does your code run? …  (Press <space> to select, <a> to toggle all, <i> to invert selection)
✔ Browser
✔ Node
```

