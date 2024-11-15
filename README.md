# Country Information Data

Este archivo TypeScript contiene información detallada sobre países, incluyendo:
- **Nombre del país**
- **Código ISO del país** (Código de país estándar)
- **Código de marcación internacional** (código de área telefónica)
- **Emoji de la bandera** (representación visual del país)

Este archivo puede ser utilizado para obtener datos relacionados con países y sus códigos telefónicos, y es especialmente útil cuando se necesitan implementar características como selecciones de países, validación de códigos de marcación o interfaces de usuario con banderas.

## Estructura de Datos

Cada país está representado por un objeto que contiene:
- `name`: El nombre del país.
- `code`: El código ISO del país.
- `dial_code`: El código de área telefónica internacional.
- `flag`: Un emoji de la bandera del país.

## Ejemplo de la Estructura de un País

A continuación se muestra cómo está estructurado cada país en el archivo `countries.ts`:

```typescript
{
  name: "Chile",
  code: "CL",
  dial_code: "+56",
  flag: "🇨🇱"
}:
```

## Ejemplo de uso y salida de countriesList()

```typescript
const countriesList = allCountry();
console.log(countriesList);  // Salida: ['🇨🇱 Chile', '🇵🇪 Peru', ...]
```

## Ejemplo de uso y salida de areaCodes()
```typescript
const areaCodes = codeArea();
console.log(areaCodes);
/*
  Salida:
  [
    { id: 0, code: '+56', flag: '🇨🇱', name: 'Chile' },
    { id: 1, code: '+51', flag: '🇵🇪', name: 'Peru' },
    ...
  ]
*/
```

## Ejemplo de uso en componente de React arrow functions
```typescript
import React from 'react';
import { allCountry, codeArea } from './countries'; // Asegúrate de usar la ruta correcta

const App: React.FC = () => {
  // Obtenemos la lista de países y los códigos de área
  const countriesList = allCountry();
  const areaCodes = codeArea();

  return (
    <div>
      <h1>Lista de Países</h1>
      {/* Mapeamos la lista de países */}
      <ul>
        {countriesList.map((country, index) => (
          <li key={index}>{country}</li>
        ))}
      </ul>

      <h1>Códigos de Área</h1>
      {/* Mapeamos los códigos de área y mostramos la bandera junto con el nombre y código de área */}
      <ul>
        {areaCodes.map((area) => (
          <li key={area.id}>
            {area.flag} {area.name} - {area.code}
          </li>
        ))}
      </ul>
    </div>
  );
};

export default App;

```


## ¡Se Agradece Mucho Una Estrellita! 🌟

Si este proyecto te ha sido útil o te ha gustado, no dudes en darle una estrella ⭐️ en GitHub. ¡Tu apoyo nos motiva a seguir mejorando! 😊

[¡Dale una estrella aquí!](https://github.com/SHRicard/countries.ts)

¡Gracias por contribuir al open-source! 🎉
