# api

API REST (GET) utilizando GitHub Pages para proveer archivos JSON a nuestras aplicaciones y página web.

## Convenciones

Para mantener un estándar profesional:

- **Estructura de la API (Claves):** Las propiedades de los archivos JSON están en **inglés** (ej. `name`, `description`, `provider`).
- **Contenido y Documentación:** El valor de los datos como por ejemplo el de `description` y toda la documentación de este repositorio están en **español**.

## Endpoints Disponibles

Los datos se sirven estáticamente como archivos JSON:

- `https://cpc-gallos.github.io/api/index.json` - **Directorio principal** con la información de la API y rutas a todos los endpoints disponibles. (Validado por `index.schema.json`).
- `https://cpc-gallos.github.io/api/credentials/data.json` - Datos de certificados. (Validado por `schema.json`).
- `https://cpc-gallos.github.io/api/communities/data.json` - Datos de comunidades de programación competitiva. (Validado por `schema.json`).

> **Tip para desarrolladores:** Cada endpoint cuenta con su propio esquema JSON (`schema.json`). Puedes usarlos para validar las respuestas o para generar tipados estáticos (ej. interfaces de TypeScript) automáticamente en tus aplicaciones.

## Ejemplo de uso (fetch)

Tener los datos en la API permite que cualquiera los consuma fácilmente. Puedes obtener los datos desde cualquier aplicación usando la API `fetch()` nativa de JavaScript:

```javascript
fetch('https://cpc-gallos.github.io/api/credentials/data.json')
  .then(response => response.json())
  .then(data => {
    console.log('Datos de certificados:', data);
    // Aquí puedes procesar los datos para mostrarlos en el blog o aplicación
  })
  .catch(error => console.error('Error al obtener los datos:', error));
```

## Contribuir

Cualquier colaborador puede contribuir abriendo un PR para agregar o corregir información (clubes, certificados, comunidades). Para más detalles sobre cómo hacerlo, por favor revisa nuestra [guía de contribución](CONTRIBUTING.md).
