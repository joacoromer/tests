Proyecto CORE
Requerimientos para implementación de Cypress

Tener instalada la versión de node js homologada por la compañía.
Visual Code es el IDE sugerido para el framework.
Tener instalado GIT.
Disponer de un repositorio en github: URL REPO
Tener acceso a Jenkins para la CD/CI.
Tener definido los 2 flujos principales de automatización para el spike o POC.
Permiso de red para bajar dependencias (si se requiere).

Proyecto GIT
INGRESAR URL

Extensiones del Visual Code
(\*) : Prioritarios de instalación.
(-) : IA de autocompletado

Cucumber (Gherkin) Full Support (_)
Prettier - Code formatter (_)
Bracket Pair Colorizer
Tabnine (-)
Git flow
GitLens — Git supercharged
Quokka.js
Error Lens
JavaScript (ES6) code snippets
Material Icon Theme
Andromeda
Atom One Dark Theme
Atom Material Theme

Arquitectura del Proyecto
Uso de Page Object Model + Cucumber

Observaciones
Los casos pueden tener extensiones .js como .ts si se requiere hacer validaciones de tipos de datos.

Estructura del Proyecto

Convenciones:
*IMPORTANTE: No incluir ninguna mención o alusión al framework Selenium
*Uso de punto y coma al finalizar una línea de código
*Uso de inglés obligatorio en todo el código salvo el BDD que se usa español en primera persona, sin comentarios y evitar el uso del famoso spanglish
*Patrón de diseño a usar: Page Object Model. Investigar para usar el principio SOLID: App Actions o Screen Play
*PageObjects deben ser usadas con terminación Page, ejemplo LoginPage
*Los .js de los feature con terminación spec.js para diferencias las clases, ejemplo login.spec.js
*Variables y funciones explícitas y descriptivas.
*Las clases y los objetos deben tener nombres formados por un sustantivo o frases de sustantivo.
*Los nombres, imprescindiblemente en inglés, deben ser pronunciables, no deben ser abreviaturas ni llevar guion bajo o medio, priorizando el estilo CamelCase.
*Las funciones deben representar acciones, en verbos seguido de un sustantivo, ejemplo createUser(...)
*En el caso de las funciones de acceso, modificación o predicado, el nombre debe el prefijo get, set, e is, respectivamente. getUser() setUser(...) isValidUser()
*Uso correcto de let y const. Constantes en mayúsculas separadas por guiones bajos. Let para inicialización de clases, ejemplo let class = new Class();
*Arrays: pluralizar el nombre de la variable puede ser una buena idea: const fruitNames = ['manzana', 'plátano', 'fresa'];
*Booleanos: Uso de prefijos como "is", "has" y "can" ayudará inferir el tipo de variable, mejorando así la legibilidad de nuestro código: const isOpen = true; const canWrite = true; const hasFruit = true;
\*Números: Es interesante escoger palabras que describan números, como “min”, “max”, “total”: const totalFruits = 3;

Mas info: https://softwarecrafters.io/javascript/clean-code-javascript
Cucumber + BDD
Buenas prácticas de Cucumber - Federico Toledo
https://www.federico-toledo.com/buenas-practicas-de-cucumber/
*Como [rol ] quiero [ característica ] para que [los beneficios]
*Los escenarios se escriben en primera persona
Escenario: Describe cada escenario que vamos a probar.
Dado: Provee contexto para el escenario en que se va a ejecutar el test, tales como punto donde se ejecuta el test, o prerrequisitos en los datos. Incluye los pasos necesarios para poner al sistema en el estado que se desea probar.
Como: Especifica el conjunto de acciones que lanzan el test. La interacción del usuario que acciona la funcionalidad que deseamos testear.
Cuando: Especifica el resultado esperado en el test. Observamos los cambios en el sistema y vemos si son los deseados.

BASH

## Install Dependencies

Instalar las dependencias

```bash
npm i
```

## Run Test

Correr los casos de prueba

```bash
npm run cy:run
```

Abrir el Dashboard

```bash
npm run cy:open
```

## Libraries

Estas librerías se instalan automáticamente usando el npm i, sin embargo, dejó las líneas de instalación por si se requieren para otro proyecto.

### Cucumber

```bash
npm install --save-dev cypress-cucumber-preprocessor
```

### Test-Rail

```bash
npm i salty-cypress-testrail-reporter
```

### Configuración del reporter options

"reporterOptions": {
"domain": "invertironline.testrail.com",
"username": "qa@invertironline.com",
"password": "QKsaJAE3PxB9t7zr8YXm-y/FwZ5CogpS72R.b1J/w",
"projectId": 0,
"suiteId": 0,
"createTestRun": "boolean",
"runId": 0,
"runName": "Test Run Name"
}

Usamos la extensión Prettier.
En el directorio hay un archivo .prettierrc con estos parámetros:

{
"trailingComma": "all",
"tabWidth": 4,
"semi": true,
"singleQuote": true
}

Api key de cypress:
QKsaJAE3PxB9t7zr8YXm-y/FwZ5CogpS72R.b1J/w

Para integrar base de datos usaremos más adelante esta librería:
https://www.npmjs.com/package/cypress-sql-server

## Definir parametrización en Jenkins
