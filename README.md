Eslint et Prettier

npm i -D eslint

npx eslint —init

- check syntax and find problems
- JS import and exports
- React
- TS yes
- Browser …

LOOK AT:
Airbnb style guide

Pour ne pas configurer eslint manuellement on peut s’inspirer de la config d’AirBB
https://www.npmjs.com/package/eslint-config-airbnb

npx install-peerdeps --dev eslint-config-airbnb
permet d’installer tout ce qu’il nous faut avec les autres package eslint tel que eslint react hook….

eslint-config-airbnb/hooks
This entry point enables the linting rules for React hooks (requires v16.8+). To use, add "extends": ["airbnb", "airbnb/hooks"] to your .eslintrc.

puis:
https://www.npmjs.com/package/eslint-config-airbnb-typescript

npm install eslint-config-airbnb-typescript \
 @typescript-eslint/eslint-plugin@^5.13.0 \
 @typescript-eslint/parser@^5.0.0 \
 --save-dev

Configure ESLint
Within your ESLint config file:
extends: [
'airbnb',

- 'airbnb-typescript'
  ]

This config requires knowledge of your TypeScript config.
In your ESLint config, set parserOptions.project to the path of your tsconfig.json.
For example:
{
extends: ['airbnb', 'airbnb-typescript'],

- parserOptions: {
- project: './tsconfig.json'
- }
  }

cmd shift p Reload window (reload ts et eslint server)

On doit dire à TS de regarder eslint
Dans tsconfig.json:
dans le include:
“.eslintrc.js?” (voir si bonne extension)

cmd shift p Reload window (reload ts et eslint server)
cmd shift p eslint fix all auto-fixable problems (corrige auto les pb)

cmd + . on peut dans un ficheir sur une erreur permet d’importer un eslint-disable par exemple
par exemple le eslint veut qu’on import React from react mais dans certains fichiers on n’en a pas besoin…

ça affiche aussi le rule name qu’on peut copier coller dans la config -> eslintrc -> rules,
coller ‘’react/react-in-jsx-sxope’: 0 (pour turn off cette règle)

Err: React must be in the scope:
dans eslintrc:
rules:
‘react/react-in-jsx-scope’: 0

———————————————————

PRETTIER:

auto formatting

npm i -D prettier eslint-config-prettier eslint-plugin-prettier

dans .prettierrc.js

// prettier.config.js or .prettierrc.js
module.exports = {
trailingComma: "es5",
tabWidth: 2,
semi: true,
singleQuote: true,
};

Dans eslintrc:
dans plugins:
ajouter:
‘prettier’
et dans extends:
ajouter:
‘plugin:prettier/recommended’

Etre sur qu’a chaq fois quon change la config Fermer/ouvrir Vscode pour qu’il prenne les changements en compte!
-> cmd shift p Reload window (reload ts et eslint server)
cmd shift p eslint fix all auto-fixable problems (corrige auto les pb)
