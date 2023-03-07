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
✔ How would you like to use ESLint? · style
✔ What type of modules does your project use? · commonjs
✔ Which framework does your project use? · none
✔ Does your project use TypeScript? · No / <Yes>
✔ Where does your code run? · node
✔ How would you like to define a style for your project? · prompt
✔ What format do you want your config file to be in? · JavaScript
✔ What style of indentation do you use? · tab
✔ What quotes do you use for strings? · double
✔ What line endings do you use? · unix
✔ Do you require semicolons? · No / <Yes>
The config that you've selected requires the following dependencies: ...
✔ Would you like to install them now? · No / <Yes>
✔ Which package manager do you want to use? · yarn
```

```
yarn add v1.22.19
[1/4] Resolving packages...
[2/4] Fetching packages...
[3/4] Linking dependencies...
[4/4] Building fresh packages...
success Saved 2 new dependencies.
info Direct dependencies
├─ @typescript-eslint/eslint-plugin@5.54.1
└─ @typescript-eslint/parser@5.54.1
info All dependencies
├─ @typescript-eslint/eslint-plugin@5.54.1
└─ @typescript-eslint/parser@5.54.1
Done in 3.30s.
Successfully created .eslintrc.js file in ...
```

```
module.exports = {
	"env": {
		"commonjs": true,
		"es2021": true,
		"node": true
	},
	"extends": ["eslint:recommended","plugin:@typescript-eslint/recommended"],
	"parser": "@typescript-eslint/parser",
	"parserOptions": {
		"ecmaVersion": "latest"
	},
	"plugins": ["@typescript-eslint"],
	"rules": {
		"indent": ["error","tab"],
		"linebreak-style": ["error","unix"],
		"quotes": ["error","double"],
		"semi": ["error","always"],
	}
};

```


```
yarn add -D eslint-config-airbnb-base
```