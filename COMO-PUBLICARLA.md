# Publicar la intranet en GitHub Pages

Todo lo de esta carpeta ya está compilado y listo. Solo hay que subirlo.

## Los pasos

**1. Crear el repositorio**

Entrar a github.com con la cuenta MiguelMata-25 y crear un repositorio nuevo llamado
exactamente `tc-intranet`. Público, y sin marcar la casilla de agregar README.

El nombre importa: la dirección final depende de él, y el compilado ya viene armado para
ese nombre. Si se usa otro, hay que volver a compilar.

**2. Subir los archivos**

En el repositorio recién creado, la liga que dice *uploading an existing file*.

Arrastrar **todo el contenido de esta carpeta**, no la carpeta. Se abre la carpeta, se
seleccionan todos los archivos con Ctrl+E y se arrastran.

Ojo con dos archivos que Windows no muestra por defecto: `.nojekyll` y `404.html`. Si no
aparecen, en el Explorador hay que activar Vista, Mostrar, Elementos ocultos. Los dos son
necesarios: sin `.nojekyll` GitHub ignora algunos archivos, y sin `404.html` las secciones
dan error al recargar la página.

Abajo, en el mensaje, poner algo como `Plantilla de la intranet` y confirmar.

**3. Prender Pages**

En el repositorio, Settings, y en el menú de la izquierda, Pages.

En Source elegir **Deploy from a branch**, rama `main`, carpeta `/ (root)`, y guardar.

**4. Esperar y abrir**

Tarda entre uno y tres minutos la primera vez. La dirección queda:

```
https://miguelmata-25.github.io/tc-intranet/
```

Esa dirección no caduca y no cambia aunque se vuelvan a subir los archivos.

## Cómo enseñarla

Entra con `admin` / `admin`. Los otros usuarios de demostración están listados en la misma
pantalla.

Para mostrar el cambio de empresa: salir con el botón junto al nombre y volver a entrar con
`dael` / `dael`.

## Si se hacen cambios y hay que volver a subirla

```
cd C:\Proyectos\tc-intranet
npm run build -- --base-href "/tc-intranet/"
```

Lo compilado queda en `dist\tc-intranet\browser`. Se copia el contenido a esta carpeta, se
vuelve a copiar `index.html` como `404.html`, y se sube otra vez.

## Dos cosas que conviene tener presentes

La dirección es pública. Cualquiera con la liga entra, y Google puede indexarla. El
contenido incluye el organigrama con nombres, la estructura de direcciones y los
indicadores de la flota.

Para una demostración de un día no tiene mayor consecuencia, pero conviene **borrar el
repositorio en cuanto deje de usarse**, que se hace en Settings, hasta abajo, Delete this
repository. Diez segundos.

Y el archivo `contenido.json` es el que trae todo el texto de las secciones. Si algún día
se quiere publicar una versión sin el organigrama o sin los indicadores, se edita ese
archivo y no hace falta volver a compilar.
