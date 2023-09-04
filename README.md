# Setup steps

## EditorConfig [↗](https://editorconfig.org/)

#### 1. Create and define rules in `.editorconfig` file

```bash
touch .editorconfig
```

#### 2. Install [EditorConfig extension](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig) (extension ID: _EditorConfig.EditorConfig_) to apply rules in .editorconfig

## Prettier [↗](https://prettier.io/)

#### 1. Install prettier package

```bash
pnpm add -D prettier
# yarn add -D -E prettier
# npm install -D -E prettier
```

#### 2. Create and define rules in `.prettierrc` file and ignore files in `.prettierignore`

```bash
touch .prettierrc .prettierignore
```

#### 3. Add script and run prettier

```bash
# Add script to package.json
npm pkg set scripts.prettier="prettier . --write --list-different"
# Run script
pnpm prettier
```

#### 4. Install [Prettier extension](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) (extension ID: _esbenp.prettier-vscode_) and config to format on save

## Eslint [↗](https://eslint.org/)

#### 1. Install and config Eslint

```bash
pnpm create @eslint/config
# yarn create @eslint/config
# npm init @eslint/config
```

Ignore files in `.eslintignore` file

```bash
touch .eslintignore
```

#### 2. Init TS config and JS config

```bash
# Init tsconfig.json
npx tsc --init
# Init jsconfig.json
npx jsconfig.json -m commonJS
```

#### 3. Reload window to editor reload config

Press `Command/Ctrl + Shift + P` > `Reload window` > Press `Enter`

#### 4. Add script and run

```bash
# Add script to package.json
npm pkg set scripts.lint="eslint . --fix --max-warnings=0"
# Run script
pnpm lint
```

## Lint staged + Husky [↗](https://prettier.io/docs/en/precommit#option-1-lint-stagedhttpsgithubcomokonetlint-staged)

#### 1. Set up lint-staged and husky with Prettier guideline

```bash
pnpm exec -- npx mrm lint-staged
# yarn exec -- npx mrm lint-staged
# npx mrm lint-staged
```

This command will:

- Install lint-staged, husky package
- Config built-in lint-staged options in package.json
- Add prepare script for Husky
- Create `pre-commit` hook with lint-staged script

#### 2. Update lint-staged options for more properly your project.

Example:

```json
{
  "lint-staged": {
    "*.{js,ts}": ["pnpm lint"],
    "*.{json,md}": ["pnpm prettier"]
  }
}
```

## Commitlint + Husky [↗](https://commitlint.js.org/#/)

#### 1. Install commitlint

```bash
pnpm add -D @commitlint/cli @commitlint/config-conventional
# yarn add -D @commitlint/cli @commitlint/config-conventional
# npm install -D @commitlint/cli @commitlint/config-conventional
```

#### 2. Add standard convention for commitlint config

```bash
echo "module.exports = { extends: ['@commitlint/config-conventional'] }" > .commitlintrc.js
```

#### 3. Add `commit-msg` hook in husky

```bash
npx husky add .husky/commit-msg  'npx --no -- commitlint --edit ${1}'
```
