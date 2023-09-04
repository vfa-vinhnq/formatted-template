# Setup step

## EditorConfig [↗](https://editorconfig.org/)

1. Create and define rules in `.editorconfig` file

```bash
touch .editorconfig
```

2. Install [EditorConfig extension](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig) (extension ID: _EditorConfig.EditorConfig_) to apply rules in .editorconfig

## Prettier [↗](https://prettier.io/)

1. Install prettier package

```bash
pnpm add -D -E prettier
# yarn add -D -E prettier
# npm install -D -E prettier
```

2. Create and define rules in `.prettierrc` file and ignore files in `.prettierignore`

```bash
touch .prettierrc .prettierignore
```

3. Add script and run prettier

```bash
# Add script to package.json
npx json -I -f package.json -e "this.scripts.prettier='prettier . --write --list-different'"
# Run script
pnpm prettier
```

4. Install [Prettier extension](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) (extension ID: _esbenp.prettier-vscode_) and config to format on save

## Eslint [↗](https://eslint.org/)

1. Install and config Eslint

```bash
pnpm create @eslint/config
# yarn create @eslint/config
# npm init @eslint/config
```

Ignore files in `.eslintignore` file

```bash
touch .eslintignore
```

2. Init TS config and JS config

```bash
# Init tsconfig.json
npx tsc --init
# Init jsconfig.json
npx jsconfig.json -m commonJS
```

3. Reload window to editor reload config

Press `Command/Ctrl + Shift + P` > `Reload window` > Press `Enter`

4. Add script and run

```bash
# Add script to package.json
npx json -I -f package.json -e "this.scripts.lint='eslint . --fix --max-warnings=0'"
# Run script
pnpm lint
```
