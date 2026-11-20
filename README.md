# NovaStream

![Introducción animada de NovaStream](assets/novastream-intro.png)

NovaStream es un servidor multimedia personal para organizar y reproducir tus películas, series, música y fotos. Se ejecuta en tu propio equipo y guarda el progreso, los favoritos y las preferencias por cuenta.

**[Descargar NovaStream](https://github.com/MitsuriKan255/NovaStream-Downloads/releases)** · [Ver novedades](CHANGELOG.md) · [Informar de un problema](https://github.com/MitsuriKan255/NovaStream-Downloads/issues)

## Elige tu descarga

| Sistema | Archivo de la release | Requisitos |
| --- | --- | --- |
| [macOS](https://github.com/MitsuriKan255/NovaStream-Downloads/releases/latest) | `NovaStream-…-macOS-universal.zip` | macOS 13.5 o posterior con Apple Silicon. Para Mac con Intel, usa la [0.3.9](https://github.com/MitsuriKan255/NovaStream-Downloads/releases/tag/v0.3.9), su última versión. |
| [Windows](https://github.com/MitsuriKan255/NovaStream-Downloads/releases/latest) | `NovaStream-…-Windows-x64.zip` | Windows 11 en un equipo x64 con procesador Intel o AMD. Edición preliminar. |

Para una instalación nueva de macOS, usa **macOS-universal**. La variante **macOS-project-universal** se publica para instalaciones existentes que arrancan desde un proyecto local con su propio archivo `.env`.

## Instalar

1. Extrae el ZIP de tu sistema. En Windows, mantén `runtime` junto a `NovaStream.exe`.
2. Abre **NovaStream** y busca su icono en la barra de menús de macOS o en la bandeja de Windows.
3. Elige **Abrir en navegador** o **Abrir como app**. El segundo modo usa Chrome o Chromium en macOS y Edge, Chrome o Chromium en Windows.
4. Crea tu cuenta de administrador y añade tus carpetas en **Administración → Bibliotecas**. Puedes explorar carpetas del servidor o pegar sus rutas.

La app incluye el entorno del servidor. Si faltan FFmpeg y FFprobe, el primer arranque descarga y verifica su paquete. Cuando el servidor esté listo, puedes abrir la dirección local desde el menú.

### Si macOS no deja abrir NovaStream

NovaStream no está notarizado por Apple. Al abrirlo por primera vez, macOS puede decir que la app «está dañada» o que «no se puede verificar el desarrollador». Para quitarle la cuarentena, abre **Terminal** y ejecuta este comando, cambiando la ruta por la de tu `NovaStream.app`:

```sh
xattr -dr com.apple.quarantine /Applications/NovaStream.app
```

Si no sabes la ruta, escribe `xattr -dr com.apple.quarantine ` (con un espacio al final), arrastra `NovaStream.app` a la ventana de Terminal y pulsa Intro. Después vuelve a abrir NovaStream.

## Qué incluye

- Fichas con metadatos, imágenes y logotipos. Admite NFO de Jellyfin e imágenes de las carpetas de contenido.
- Reproducción directa, selección de pistas y transcodificación con VideoToolbox en macOS, Intel Quick Sync o AMD AMF en Windows.
- Preferencias por biblioteca, vigilancia de cambios, historial y copias de seguridad.
- Catálogo, búsqueda, episodios pendientes y reanudación desde la cuenta.

Los códecs H.264, HEVC y AV1 y la reproducción a 2160p dependen de las capacidades del equipo, del navegador y del modo de reproducción. El menú **Mostrar logs** y **Administración → Diagnóstico de vídeo** ayudan a comprobarlo.

## Actualizar

Desde la **0.3.9**, abre **Buscar actualizaciones** desde el icono de NovaStream. Si hay una versión más nueva para tu equipo, podrás consultar las novedades y elegir **Actualizar y reiniciar**.

Si vienes de la **0.3.8 o anterior**, instala la **0.3.9** una vez desde [Releases](https://github.com/MitsuriKan255/NovaStream-Downloads/releases). Cierra NovaStream y sustituye `NovaStream.app` en macOS, o `NovaStream.exe` y `runtime` en Windows. Conserva tus carpetas de datos. Cada release incluye `SHA256SUMS.txt` para verificar los ZIP.

| Sistema | Datos de la instalación descargable |
| --- | --- |
| macOS | `~/Library/Application Support/NovaStream` |
| Windows | `%LOCALAPPDATA%\NovaStream` |

## Soporte y licencia

Al informar de un problema, indica tu versión, sistema operativo y los pasos para reproducirlo. Puedes consultar la versión activa en el panel del servidor.

Este repositorio contiene la documentación de distribución y las releases de NovaStream. El proyecto se desarrolla en un repositorio privado y se distribuye bajo su [licencia de uso personal](LICENSE). Los componentes de terceros conservan sus licencias.
