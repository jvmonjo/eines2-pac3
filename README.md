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


- Instal·lar fontawesome

```
npm install @fortawesome/fontawesome-free --save-dev
```

- Importar fontawesome des de main.js

```js
import '@fortawesome/fontawesome-free/js/all.min.js';
```

## Desenvolupament
S'ha seguit un enfocament mobile first, de manera que s'han aplicat els estils pensant en una pantalla petita i després s'han afegit modificadors en funció de pantalles més grans. Per exemple per ajustar l'amplada dels ítems a la pantalla:

```html
<li class="w-full sm:w-1/2 md:w-1/3">
<!-- ... -->
</li>
```

S'han extret els següents components amb @apply. S'ha especificat al fitxer main.scss entre les importacions @tailwind components i @tailwind utilities, per a permetre l'adició d'utilitats de tailwind als nostres components:

```scss
.card {
  @apply bg-white text-center border border-gray-200 mb-6;
}

.card__title {
  @apply font-serif text-xl font-bold;
}

.page__title {
  @apply font-serif text-4xl font-bold;
}

.article__header {
  @apply bg-image-overlay p-6 flex flex-col items-center justify-center text-white h-64 min-h-full bg-cover bg-no-repeat bg-center;
}

.blockquote {
  @apply font-serif text-2xl italic mb-8;
}
```

## Millores de rendiment

Seguint les recomanacions s'ha importat fontawesome des del CSS en lloc de des del JS per disminuir la mida del bundle.

## Validació

La web s'ha validat en els següents estàndards:

- CSS3: https://jigsaw.w3.org/css-validator/ (algunes regles de tailwind no validen)
- HTML5: https://validator.w3.org/
- Accessibility Review (Guidelines: WCAG 2.0 (Level AA)): https://achecker.ca/checker/index.php

## Publicació i codi font
La web s'ha publicat a https://eines2-pac3.netlify.app i el codi font està allotjat a https://github.com/jvmonjo/eines2-pac3