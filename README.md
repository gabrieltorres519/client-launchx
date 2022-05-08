# Análisis del proyecto VUE JS

* main.js

En este archivo se están importando dos archivos más del proyecto, **App.vue** (componente principal del proyecto que contiene el navbar para navegar entre las vistas del mismo) y **router.js** (archivo donde se define la navegación entre las vistas y se relaciona a los componentes con el path de los endpoints del servidor). En este archivo se crea la app de VUE usando el componente principal y el archivo router.js para navegar en las vistas.

* Components

**ExplorersList.vue** -> Se trata del componente en donde se muestran todos los registros de la tabla explorers, pudiendo dar clic en el nombre del explorer para la información en detalle del mismo y ver el botón de Editar. Este componente está ligado al endpoint /explorers del servidor (esto definido en router.js), para el que tenemos una petición GET, donde obtenemos todos los registros de la tabla explorers.

**Explorer.vue** -> Se trata del componente que se muestra al hacer clic en el botón de Editar en la vista del componente ExplorersList, y nos permite visualizar un formulario donde se muestran los datos del explorer que decidimos editar, y solo un campo (mission) es editable, con lo que podemos actualizar ese valor o incluso borrar dicho explorer ya que este componente está ligado al endpoint /explorers/:id del servidor (esto definido en router.js), para el cual tenemos una petición PUT y una DELETE.

**AddExplorer.vue** -> Se trata del componente donde se muestra un formulario con todos los campos editables para crear un nuevo explorer. Este componente está ligado al endpoint /add (esto definido en router.js), aunque en realidad nosotros no tenemos este endpoint en el servidor, es en ExplorerService.js donde se liga al endpoint /explorers, con petición PUT (Create).


* Conexión a server y CRUD

**http-common.js** -> Se trata del archivo donde se utiliza a Axios, definiendo el "dominio" o url a la que le haremos las peticiones (CRUD) y definimos una comunicación en formato JSON.

**ExplorerService.js** -> Se trata del archivo que importa a http-common.js para realizar los CRUD, estos se relacionan directamente con los endpoints en el server y además se trata de funciones que nos proporciona Axios para poder mandar la información introducida por el cliente.


* La definición del puerto donde se accederá al proyecto cliente se da en el archivo **vue.config.js**, este puerto o "dominio" es el que se define en los CORS del proyecto servidor para escucarlo y recibir sus peticiones.


# Diagrama del proyecto cliente

![Imgur](https://i.imgur.com/6NazN1r.jpg)


# vue-3-crud

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
