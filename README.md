# DOCS
## COnfiguració de l'entorn

- Clonar UOC Boilerplate

```
git clone https://github.com/uoc-advanced-html-css/uoc-boilerplate.git
```

- Instal·lar tailwindcss

```
npm install tailwindcss --save-dev
```

- Importar tailwindcss al main.scss

```scss
@tailwind base;

@tailwind components;

@tailwind utilities;
```

- Crear el fitxer de configuració de tailwind

```
npx tailwindcss init
```

- Afegir tailwind a postcss.config.js

```js
module.exports = {
  plugins: [
    // ...
    require('tailwindcss')(),
    // ...
  ]
}
```

- Afegir l'opció de purga de css no usat als fitxers html (tailwind.comfig.js)

```js
module.exports = {
  purge: [
    './src/*.html'
  ],
  //...
}
```

- Instal·lar stylelint recommended config

```
npm install stylelint-config-recommended --save-dev
```

- Deshabilitar el lint integrat de VSCode i habilitar el de stylelint

```json
"scss.validate": false, // Disable css built-in lint
"stylelint.enable": true, // Enable sytlelint
```

- Fitxer de configuració .stylelintrc

```json
{
  "extends": "stylelint-config-recommended",
  "rules": {
    "at-rule-no-unknown": [ true, {
      "ignoreAtRules": [
        "extends",
        "tailwind"
      ]
    }],
    "block-no-empty": null,
    "unit-whitelist": ["em", "rem", "s"]
  }
}
```
