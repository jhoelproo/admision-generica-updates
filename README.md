# Admisión genérica — actualizaciones

Canal público de instaladores de Windows para la aplicación local de admisión de emergencia. El código de la aplicación es privado. Este repositorio no contiene información de pacientes, usuarios ni configuraciones de hospitales.

## Descargar

Utilice la sección [Releases](https://github.com/jhoelproo/admision-generica-updates/releases). La versión 0.2.0 continúa en fase de pruebas: no utilice pacientes reales hasta completar la validación del hospital.

La primera instalación desde una versión portable 0.1.x se hace con el instalador descargado. Cierre las versiones portables antes de instalar. A partir de la versión 0.2.0, la aplicación comprueba actualizaciones al abrir una sesión y permite buscarlas con un botón. Un administrador confirma la descarga e instalación.

## Conservación de datos

El instalador solo añade archivos del programa. No incluye ni elimina bases locales, logos, usuarios, nombre del hospital, ARS u horarios. La aplicación reutiliza el perfil local existente y realiza un respaldo de base y recursos administrados antes de una actualización iniciada desde la app. La instalación manual no sustituye el respaldo: conserve una copia de sus datos antes de instalar.

La nueva versión exige iniciar sesión. Si el perfil está vacío, permite crear el primer administrador. No crea cuentas de demostración automáticamente. Las cuentas de prueba antiguas se conservan; sus contraseñas compartidas no son apropiadas para uso real.

## Verificación y seguridad

`update.json` lleva una firma Ed25519. La app verifica firma, producto, versión, tamaño y SHA-256 antes de ejecutar un instalador. Nunca solicita ni guarda un token de GitHub. La clave privada de publicación no está en este repositorio ni en los hospitales.

La firma de actualización no es una firma Authenticode de Windows; el instalador puede aparecer como editor desconocido. No desactive las protecciones de Windows. Las contraseñas se guardan como hashes con sal, no como texto plano; esto no cifra toda la base local. Proteja el equipo y las copias de respaldo.

No haga downgrade de una base actualizada: los programas 0.1.x no entienden el nuevo formato de contraseñas. La recuperación desde el respaldo anterior debe realizarse con la aplicación cerrada y asistencia técnica.

## Componentes de terceros

El instalador incluye avisos de los componentes que utiliza. SumatraPDF 3.6.1 se incluye sin modificar como programa independiente; su código fuente oficial correspondiente se adjunta a la release como `SumatraPDF-3.6.1-source.zip`. Fuente original y licencia: [SumatraPDF 3.6.1rel](https://github.com/sumatrapdfreader/sumatrapdf/tree/3.6.1rel).

Windows 10/11 x64. La aplicación funciona sin Internet; únicamente la búsqueda y descarga de actualizaciones requieren conexión.
