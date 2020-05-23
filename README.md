# DOCS
## Configuració de l'entorn

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

- Instal·lar stylelint i stylelint-scss

```
npm install stylelint stylelint-scss --save-dev
```

- Deshabilitar el lint integrat de VSCode i habilitar el de stylelint

```json
"scss.validate": false, // Disable css built-in lint
"stylelint.enable": true, // Enable sytlelint
```

- Fitxer de configuració .stylelintrc.json

```json
{
  "plugins": [
    "stylelint-scss"
  ],
  "rules": {
    "at-rule-no-unknown": null,
    "scss/at-rule-no-unknown": [true, {
      "ignoreAtRules": [
        "extends",
        "tailwind"
      ]
    }]
  }
}
```
