# Senda

**Local pipeline for small creative projects. Beta version.**

[Español](#español) | [English](#english)

---

## English

Senda is a local pipeline tool for managing small creative projects: folder scanning, project status, render review, client outputs, work files, application launching, time logs, backups, and basic billing.

It runs locally from a web interface at:

```text
http://127.0.0.1:8765
```

Senda does not require ShotGrid, ftrack, or any external service.

### Requirements

- Windows.
- A modern web browser.
- Python 3.10 or later.
- Optional: OpenRV, FFmpeg, and the creative applications you want to launch from Senda.

OpenRV is optional, but recommended for reviewing EXR/DPX image sequences, render versions, and output files. You can download it from the official Academy Software Foundation releases:

https://github.com/AcademySoftwareFoundation/OpenRV/releases

### Quick Start

1. Download the latest Senda ZIP from the GitHub Releases page.
2. Extract it to a folder, for example `C:\Senda`.
3. Double-click `Senda.vbs` or `Senda.cmd`.
4. Open `Home > Settings > General`.
5. Set your projects folder.
6. Save settings and click `Scan projects`.

If you want to see what the local server is doing, open `Senda_consola.cmd`.

### Main Features

- Home dashboard with global project status, free disk space, warnings, launcher, and project size chart.
- Sortable project list.
- Project creation with configurable folder templates.
- Project sheet with client, status, priority, notes, sequences, artists, and thumbnails.
- Work tab for software files such as Nuke, Photoshop, Maya, Fusion, Unreal Engine, and more.
- Review tab for internal renders from `Renders`, including image sequence grouping and version detection.
- Output tab for client-facing files from `Output`, with shot status, notes, version selection, metadata, and player launch.
- Global time logs with timer, manual entries, calendar, records, and analytics.
- Billing and bids with clients, editable line items, taxes, templates, PDF, Excel, and CSV export.
- Application launcher with detection and icons.
- Full and project-level backups.
- Updates from GitHub Releases.

### Suggested Folder Structure

Senda works best when each project uses a clear folder structure:

```text
ProjectName/
  Source/
  Renders/
  Output/
  Nuke/
  Maya/
  Fusion/
  Photoshop/
  AfterEffects/
```

`Renders` is intended for internal review versions. `Output` is intended for client-facing exports or final deliveries. Keeping those folders separate helps Senda catalogue the project correctly.

### Image Sequences and Versions

Image sequences are treated as one render, not as hundreds of individual files. Version names such as `v001`, `v002`, `v003` help Senda group renders by shot and version.

Example:

```text
Shot01_v001_1001.exr
Shot01_v001_1002.exr
Shot01_v001_1003.exr
```

### Local Data and Backups

Senda stores settings, project sheets, shots, sequences, artists, time logs, clients, and invoices locally inside the Senda folder.

Before moving Senda to another computer, reinstalling it, or testing an important update, create a backup from:

```text
Settings > Backup
```

### Updates

Senda can check GitHub for new versions from:

```text
Settings > Updates
```

For this beta, use:

```text
Repository: Ekaiadesign/Senda
Channel: Beta
```

When a newer version is available, Senda can download it and start the installer from inside the app.

### Billing Notice

Senda helps prepare invoices and bids, but it is not legal or tax advice. Always check the fiscal requirements for your country or region before sending an invoice.

### Credits

Created by Edu León.

Ekaiadesign.com

---

## Español

Senda es una herramienta de pipeline local para administrar pequeños proyectos creativos: escaneo de carpetas, estado de proyectos, revisión de renders, salidas a cliente, archivos de trabajo, launcher de aplicaciones, registro de tiempo, copias de seguridad y facturación básica.

Funciona en local desde una interfaz web en:

```text
http://127.0.0.1:8765
```

Senda no necesita ShotGrid, ftrack ni servicios externos.

### Requisitos

- Windows.
- Un navegador web moderno.
- Python 3.10 o superior.
- Opcional: OpenRV, FFmpeg y las aplicaciones de trabajo que quieras abrir desde Senda.

OpenRV no es obligatorio, pero es recomendable para revisar secuencias EXR/DPX, versiones de renders y archivos de salida. Puedes descargarlo desde las releases oficiales de Academy Software Foundation:

https://github.com/AcademySoftwareFoundation/OpenRV/releases

### Primer Arranque

1. Descarga el ZIP más reciente de Senda desde la página de Releases de GitHub.
2. Descomprímelo en una carpeta, por ejemplo `C:\Senda`.
3. Haz doble click en `Senda.vbs` o `Senda.cmd`.
4. Abre `Inicio > Configuración > General`.
5. Define tu carpeta de proyectos.
6. Guarda los ajustes y pulsa `Escanear proyectos`.

Si quieres ver qué está haciendo el servidor local, abre `Senda_consola.cmd`.

### Funciones Principales

- Inicio con estado general, espacio libre, avisos, launcher y gráfico de ocupación por proyecto.
- Lista de proyectos ordenable.
- Creación de proyectos con plantillas de carpetas.
- Ficha de proyecto con cliente, estado, prioridad, notas, secuencias, artistas y miniaturas.
- Pestaña Trabajo para archivos de software como Nuke, Photoshop, Maya, Fusion, Unreal Engine y más.
- Pestaña Revisión para renders internos desde `Renders`, agrupando secuencias de imagen y detectando versiones.
- Pestaña Salida para archivos destinados a cliente desde `Output`, con estado de plano, notas, versiones, metadata y apertura en reproductor.
- Registro de tiempo global con contador, registros manuales, calendario y analíticas.
- Facturación y presupuestos con clientes, líneas editables, impuestos, plantillas y exportación a PDF, Excel y CSV.
- Launcher de aplicaciones con detección e iconos.
- Copias de seguridad completas o por proyecto.
- Actualizaciones desde GitHub Releases.

### Estructura Recomendada

Senda funciona mejor cuando cada proyecto mantiene una estructura clara:

```text
NombreProyecto/
  Source/
  Renders/
  Output/
  Nuke/
  Maya/
  Fusion/
  Photoshop/
  AfterEffects/
```

`Renders` está pensado para versiones internas de revisión. `Output` está pensado para archivos enviados al cliente o entregas finales. Mantener esas carpetas separadas ayuda a que Senda catalogue el proyecto correctamente.

### Secuencias y Versiones

Las secuencias de imagen se tratan como un solo render, no como cientos de archivos independientes. Los nombres de versión como `v001`, `v002`, `v003` ayudan a Senda a agrupar renders por plano y versión.

Ejemplo:

```text
Plano01_v001_1001.exr
Plano01_v001_1002.exr
Plano01_v001_1003.exr
```

### Datos Locales y Copias

Senda guarda configuración, fichas, planos, secuencias, artistas, registros de tiempo, clientes y facturas de forma local dentro de la carpeta de Senda.

Antes de mover Senda a otro equipo, reinstalarla o probar una actualización importante, crea una copia desde:

```text
Configuración > Copia de seguridad
```

### Actualizaciones

Senda puede comprobar nuevas versiones en GitHub desde:

```text
Configuración > Actualizaciones
```

Para esta beta, usa:

```text
Repositorio: Ekaiadesign/Senda
Canal: Beta
```

Cuando haya una versión nueva, Senda podrá descargarla e iniciar la instalación desde la propia aplicación.

### Aviso Sobre Facturación

Senda ayuda a preparar facturas y presupuestos, pero no sustituye asesoría legal o fiscal. Comprueba siempre los requisitos de tu país o región antes de enviar una factura.

### Créditos

Creado por Edu León.

Ekaiadesign.com
