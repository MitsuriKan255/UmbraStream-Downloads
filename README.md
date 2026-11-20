# NovaStream

![Introducción animada de NovaStream](assets/novastream-intro.png)

NovaStream es un servidor multimedia personal para organizar y reproducir tus películas, series, música y fotos. Se ejecuta en tu propio equipo y guarda el progreso, los favoritos y las preferencias por cuenta.

**[Descargar NovaStream](https://github.com/MitsuriKan255/NovaStream-Downloads/releases)** · [Ver novedades](CHANGELOG.md) · [Informar de un problema](https://github.com/MitsuriKan255/NovaStream-Downloads/issues)

## Elige tu descarga

Descarga el instalador de tu sistema. Instala dos apps:

- **NovaStream Server**: el servidor. Organiza tus películas, series, música y fotos y las comparte con tus dispositivos.
- **NovaStream Player**: la app para ver tu biblioteca sin navegador, en el mismo equipo o en otro.

| Sistema | Instalador | Requisitos |
| --- | --- | --- |
| [macOS](https://github.com/MitsuriKan255/NovaStream-Downloads/releases/latest) | `NovaStream-…-macOS.pkg` | Mac con Apple Silicon y macOS 13.5 o posterior. Para Mac con Intel, usa la [0.3.9](https://github.com/MitsuriKan255/NovaStream-Downloads/releases/tag/v0.3.9), su última versión. |
| [Windows](https://github.com/MitsuriKan255/NovaStream-Downloads/releases/latest) | `NovaStream-…-Windows-Setup.exe` | Windows 11 en un equipo x64 con procesador Intel o AMD. |

Los archivos ZIP de cada release los usan las actualizaciones automáticas; no hace falta descargarlos.

## Instalar

1. Abre el instalador y sigue los pasos.
   - **Mac:** instala NovaStream Server y NovaStream Player en Aplicaciones. Te pedirá la contraseña del Mac.
   - **Windows:** elige qué instalar. Se instala en tu usuario, sin permisos de administrador, con accesos en el menú Inicio. Si aparece «Windows protegió su PC», pulsa «Más información» y «Ejecutar de todas formas».
2. Abre **NovaStream Server**, busca su icono en la barra de menús de macOS o junto al reloj en Windows y crea tu cuenta de administrador.
3. Añade tus carpetas en **Administración → Bibliotecas**. Puedes explorar carpetas del servidor o pegar sus rutas.
4. Abre **NovaStream Player** para ver tu biblioteca. En el equipo del servidor, **Abrir como app** lo abre ya conectado. En otro equipo, escribe la dirección que aparece en **Administración → General → Acceso desde la red local** e inicia sesión.

Si faltan FFmpeg y FFprobe, el primer arranque del servidor descarga y verifica su paquete.

### Si macOS no deja abrir el instalador o las apps

NovaStream no está notarizado por Apple. Si macOS no deja abrir el instalador, ve a **Ajustes del Sistema → Privacidad y seguridad** y pulsa **Abrir igualmente**. También puedes quitarle la cuarentena desde **Terminal**:

```sh
xattr -d com.apple.quarantine ~/Downloads/NovaStream-*-macOS.pkg
```

Si una app dice que «está dañada», quítale la cuarentena igual, cambiando la ruta por la de la app:

```sh
xattr -dr com.apple.quarantine "/Applications/NovaStream Server.app"
```

Si no sabes la ruta, escribe `xattr -dr com.apple.quarantine ` (con un espacio al final), arrastra el archivo a la ventana de Terminal y pulsa Intro.

## Qué incluye

- Fichas con metadatos, imágenes y logotipos. Admite NFO de Jellyfin e imágenes de las carpetas de contenido.
- Reproducción directa, selección de pistas y transcodificación con VideoToolbox en macOS, Intel Quick Sync o AMD AMF en Windows.
- Preferencias por biblioteca, vigilancia de cambios, historial y copias de seguridad.
- Catálogo, búsqueda, episodios pendientes y reanudación desde la cuenta.

Los códecs H.264, HEVC y AV1 y la reproducción a 2160p dependen de las capacidades del equipo, del navegador y del modo de reproducción. El menú **Mostrar logs** y **Administración → Diagnóstico de vídeo** ayudan a comprobarlo.

## Actualizar

NovaStream Server y NovaStream Player comprueban cada día si hay una versión nueva y te avisan. También puedes pulsar **Buscar actualizaciones** en el menú de cada app. Elige **Actualizar y reiniciar** para instalarla: se descarga, se verifica su suma SHA-256 y se conservan tus datos.

Si vienes de la **0.3.8 o anterior**, descarga e instala la última versión una vez. Cada release incluye `SHA256SUMS.txt` para verificar los archivos.

| Sistema | Datos de la instalación descargable |
| --- | --- |
| macOS | `~/Library/Application Support/NovaStream` |
| Windows | `%LOCALAPPDATA%\NovaStream` |

## Soporte y licencia

Al informar de un problema, indica tu versión, sistema operativo y los pasos para reproducirlo. Puedes consultar la versión activa en el panel del servidor.

Este repositorio contiene la documentación de distribución y las releases de NovaStream. El proyecto se desarrolla en un repositorio privado y se distribuye bajo su [licencia de uso personal](LICENSE). Los componentes de terceros conservan sus licencias.
