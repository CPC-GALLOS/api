# Guía de Contribución

¡Gracias por tu interés en contribuir a nuestra API estática! Los datos viven en este repositorio y cualquier persona puede ayudar agregando o corrigiendo información sin necesidad de tocar el código del blog o las aplicaciones.

## Convenciones

Al agregar o modificar datos, por favor respeta las siguientes reglas de idioma:

- **Las claves (keys) del JSON van en inglés:** e.g., `id`, `name`, `description`.
- **Los valores y el contenido van en español:** La información que leerán los usuarios debe estar en español.
- **Validación con Esquemas JSON (Schemas):** Todos los archivos de datos (`index.json`, `data.json`) deben incluir la propiedad `"$schema"` en su raíz apuntando a su esquema correspondiente.
- **Creación de Esquemas:** Todo esquema nuevo debe utilizar el estándar `2020-12` (`"$schema": "https://json-schema.org/draft/2020-12/schema"`), definir un `"$id"` absoluto y validar la estructura completa del archivo.

## Cómo contribuir

Para agregar nuevos datos o corregir información existente (como clubes, certificados o comunidades), sigue estos pasos:

1. **Haz un Fork** de este repositorio.
2. **Crea una nueva rama** para tus cambios:

   ```bash
   git checkout -b actualizar-datos
   ```

3. **Modifica los archivos JSON** necesarios (ej. `credentials/data.json` o `communities/data.json`). Asegúrate de que el formato JSON sea válido.
4. **Haz commit** de tus cambios:

   ```bash
   git commit -m "Agrega nuevo certificado de ejemplo"
   ```

5. **Haz push** a tu rama:

   ```bash
   git push origin actualizar-datos
   ```

6. **Abre un Pull Request (PR)** en este repositorio explicando brevemente los cambios que realizaste.

> 💡 **Nota sobre Integración Continua (CI):** Cuando abras tu Pull Request, GitHub Actions validará automáticamente que el formato de tus archivos JSON cumpla con nuestros esquemas. Si la prueba falla (aparecerá una "X" roja en tu PR), revisa los detalles, haz la corrección necesaria y sube un nuevo commit; el CI volverá a validar automáticamente.

Una vez que las validaciones pasen y tu PR sea aprobado, será fusionado y los datos estarán disponibles automáticamente a través de GitHub Pages.
