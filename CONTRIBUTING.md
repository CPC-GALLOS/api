# Guía de Contribución

¡Gracias por tu interés en contribuir a nuestra API estática! Los datos viven en este repositorio y cualquier persona puede ayudar agregando o corrigiendo información sin necesidad de tocar el código del blog o las aplicaciones.

## Cómo contribuir

Para agregar nuevos datos o corregir información existente (como clubes, certificados o comunidades), sigue estos pasos:

1. **Haz un Fork** de este repositorio.
2. **Crea una nueva rama** para tus cambios:
   ```bash
   git checkout -b actualizar-datos
   ```
3. **Modifica los archivos JSON** necesarios (ej. `credentials/Credentials.json` o `comunidades/comunidades.json`). Asegúrate de que el formato JSON sea válido.
4. **Haz commit** de tus cambios:
   ```bash
   git commit -m "Agrega nuevo certificado de ejemplo"
   ```
5. **Haz push** a tu rama:
   ```bash
   git push origin actualizar-datos
   ```
6. **Abre un Pull Request (PR)** en este repositorio explicando brevemente los cambios que realizaste.

Una vez revisado, tu PR será fusionado y los datos estarán disponibles automáticamente a través de GitHub Pages.
