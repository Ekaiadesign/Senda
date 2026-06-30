# Senda

Senda es una herramienta beta de pipeline local para organizar proyectos pequeños: escaneo de carpetas, estado general, revisión de renders, salidas a cliente, archivos de trabajo, launcher de aplicaciones y registro de tiempo.

La herramienta funciona en local desde una interfaz web en `http://127.0.0.1:8765`. No necesita ShotGrid, ftrack ni servicios externos.

## Requisitos

- Windows.
- Navegador web moderno.
- Opcional: OpenRV, FFmpeg y las aplicaciones de trabajo que quieras abrir desde el Launcher.

OpenRV no es obligatorio para usar Senda, pero es recomendable si vas a revisar secuencias EXR/DPX, renders por versiones o salidas desde la interfaz. Se puede descargar desde las releases oficiales de Academy Software Foundation:

https://github.com/AcademySoftwareFoundation/OpenRV/releases

Senda necesita Python 3.10 o superior para arrancar. Si no lo tienes instalado, descárgalo desde python.org y marca la opción de añadirlo al PATH durante la instalación.

## Instalación rápida

1. Descomprime el ZIP de Senda en una carpeta, por ejemplo `C:\Senda` o `D:\Herramientas\Senda`.
2. Haz doble click en `Senda.vbs` o `Senda.cmd`.
3. Se abrirá la interfaz en `http://127.0.0.1:8765`.
4. Entra en `Inicio > Configuración > General` y define la carpeta de proyectos.
5. Pulsa `Guardar y cerrar`.
6. Vuelve a `Inicio` y pulsa `Escanear proyectos`.

Si quieres ver qué hace el servidor, abre `Senda_consola.cmd`. Esa ventana se puede cerrar con `Ctrl+C`.

## Archivos principales

- `Senda.vbs`: lanzador silencioso.
- `Senda.cmd`: lanzador alternativo para doble click.
- `Senda_consola.cmd`: lanzador con consola visible.
- `web_server.py`: servidor local.
- `project_auditor.py`: escáner de proyectos.
- `web/`: interfaz web.
- `web/help.html`: documentación local.
- `senda_settings.example.json`: ejemplo limpio de configuración.

## Primer uso

Senda no escanea hasta que hay una carpeta de proyectos configurada. La ruta se define en `Configuración > General`.

Al escanear, Senda genera datos locales en:

- `reports/project_audit.json`
- `reports/project_audit.csv`
- `reports/project_tracker_status.csv`
- `reports/review_queue.csv`
- `project_tracker.csv`

Estos archivos se crean automáticamente cuando escaneas tus proyectos por primera vez.

## Funciones principales

- Inicio con estado general, espacio libre, avisos, launcher y gráfico circular de ocupación por proyecto.
- Lista lateral de proyectos ordenable por recientes, nombre o tamaño.
- Creación de proyectos con estructura base y carpetas por software.
- Edición de proyecto para añadir carpetas nuevas sin borrar nada existente.
- Ficha de proyecto con cliente, prioridad, estado, responsable, deadline, versión, notas y miniaturas.
- Secuencias editables por proyecto.
- Pestaña Trabajo con archivos de software agrupados por aplicación.
- Pestaña Revisión para renders internos desde `Renders`, agrupando secuencias de imagen como un solo render y detectando versiones `v001`, `v002`, etc.
- Pestaña Salida para archivos de `Output`, con estado de plano, notas, secuencia, versión y apertura en reproductor compatible.
- Registro de tiempo global con contador, edición de registros, calendario y analíticas.
- Facturación y presupuestos con clientes, líneas editables, impuestos, plantillas, PDF, Excel y CSV.
- Launcher global con detección de aplicaciones e iconos.
- Copias de seguridad completas o por proyecto.
- Actualizaciones desde GitHub Releases o manifest HTTPS.
- Panel Ayuda con documentación y Acerca de Senda.

## Configuración

Los ajustes globales se guardan en `senda_settings.json`, que se crea al guardar configuración desde la interfaz.

Apartados principales:

- `General`: idioma, tema, color de acento y carpeta de proyectos.
- `Rutas`: OpenRV y reproductor para Salida.
- `Launcher`: aplicaciones visibles en Inicio, ruta e icono.
- `Escaneo`: umbrales de actividad, proyecto pesado y caché alto.
- `Copia de seguridad`: exportación completa, exportación por proyecto e importación.
- `Actualizaciones`: repositorio de GitHub, manifest opcional, canal estable/beta y comprobación al abrir.
- `Servidor`: limpiar caché y cerrar servidor.

El botón `Cancelar` cierra Configuración sin guardar. El botón `Guardar y cerrar` guarda y cierra el panel.

## OpenRV y secuencias

Si defines OpenRV, Senda puede abrir renders y salidas desde la interfaz. Es una herramienta opcional: Senda puede escanear proyectos, gestionar fichas, salidas, launcher y registros de tiempo sin OpenRV, pero la revisión de secuencias será más completa si está instalado.

Después de instalarlo, define la ruta a `rv.exe` en `Configuración > Rutas`. Suele estar en una carpeta parecida a:

```text
C:\OpenRV...\app\bin\rv.exe
```

Las secuencias de imagen se tratan como un único render. Por ejemplo:

```text
Plano01_v001_1001.exr
Plano01_v001_1002.exr
Plano01_v001_1003.exr
```

se catalogan como una secuencia completa y se envían a OpenRV con patrón de secuencia, no como un único frame.

## Miniaturas

Las miniaturas solo se generan si el proyecto tiene activado `Generar miniaturas` en su Ficha.

Requieren FFmpeg disponible en el sistema. Se guardan dentro de `cache/thumbnails`, y se eliminan al usar `Limpiar caché`.

## Facturación

El área de Facturación permite crear facturas y presupuestos a partir de líneas manuales, datos de proyecto y registros de tiempo. Los documentos se pueden exportar a PDF, Excel o CSV.

Antes de emitir documentos reales, revisa:

- Tus datos profesionales en `Facturación > Datos y fiscalidad`.
- Cliente, moneda, idioma del documento y estado.
- Líneas, cantidades, unidades, precios e impuestos.
- Plantilla visual y color de plantilla.
- Totales, notas y condiciones de pago.

Senda ayuda a preparar documentos, pero no sustituye asesoría fiscal o legal. Comprueba siempre los requisitos de tu país o región antes de enviar una factura.

## Copias de seguridad

En `Configuración > Copia de seguridad` puedes exportar:

- Una copia completa de datos de Senda.
- Una copia parcial de un proyecto concreto.

Las copias por proyecto sirven para archivar junto a la carpeta del proyecto información como ficha, planos, secuencias, artistas, registros de tiempo y facturación relacionada.

## Actualizaciones desde GitHub

Senda puede comprobar si hay nuevas versiones publicadas en GitHub desde `Configuración > Actualizaciones`.

Para esta beta, usa:

- `Repositorio GitHub`: `Ekaiadesign/Senda`
- `Canal`: `Beta`

Cuando haya una versión nueva, Senda mostrará el aviso y permitirá descargarla e iniciar la instalación desde la propia aplicación.

## Datos locales

Senda guarda la configuración, fichas, planos, secuencias, artistas, registros de tiempo, clientes y facturas en archivos locales dentro de la carpeta donde está instalada la herramienta.

Antes de mover Senda a otro equipo, reinstalarla o probar una actualización importante, es recomendable crear una copia desde `Configuración > Copia de seguridad`.

## Uso por consola

Escaneo manual:

```powershell
.\run_scan.ps1 -Root "D:\Proyectos"
```

Arranque manual del servidor:

```powershell
.\run_web.ps1
```

Si PowerShell bloquea scripts, usa:

```powershell
powershell -ExecutionPolicy Bypass -File .\run_web.ps1
```

## Créditos

Creado por Edu León.

Ekaiadesign.com
