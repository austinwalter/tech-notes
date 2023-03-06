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

```
yarn init
```

```
question name (node-boilerplate): 
question version (1.0.0): 0.0.0
question description: A Node.js project
question entry point (index.js): 
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

