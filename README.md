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
