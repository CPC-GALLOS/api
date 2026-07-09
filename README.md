# api
API REST (GET) utilizando GitHub Pages para proveer archivos JSON a nuestras aplicaciones y página web.

## Endpoints Disponibles

Los datos se sirven estáticamente como archivos JSON:

- `https://cpc-gallos.github.io/api/credentials/Credentials.json` - Datos de certificados.
- `https://cpc-gallos.github.io/api/comunidades/comunidades.json` - Datos para el mapa interactivo de comunidades.

## Ejemplo de uso (fetch)

Tener los datos en la API permite que cualquiera los consuma fácilmente. Puedes obtener los datos desde cualquier aplicación usando la API `fetch()` nativa de JavaScript:

```javascript
fetch('https://cpc-gallos.github.io/api/credentials/Credentials.json')
  .then(response => response.json())
  .then(data => {
    console.log('Datos de certificados:', data);
    // Aquí puedes procesar los datos para mostrarlos en el blog o aplicación
  })
  .catch(error => console.error('Error al obtener los datos:', error));
```

## Contribuir

Cualquier colaborador puede contribuir abriendo un PR para agregar o corregir información (clubes, certificados, comunidades). Para más detalles sobre cómo hacerlo, por favor revisa nuestra [guía de contribución](CONTRIBUTING.md).
