# campuslands-cli-node-antonio

Este proyecto es una aplicación de línea de comandos (CLI) desarrollada en Node.js que permite gestionar un registro de campers. La aplicación utiliza ES Modules (ESM) y realiza operaciones de lectura y escritura en un archivo JSON para almacenar los datos de los campers.

## Funcionalidad

La aplicación permite realizar las siguientes operaciones:

1. **Agregar campers**: Registra un nuevo camper con su nombre y stack tecnológico.
2. **Listar campers**: Muestra una tabla con todos los campers registrados.
3. **Buscar campers**: Busca campers por nombre y muestra los resultados.

## Archivos del proyecto

### `src/index.js`
Este archivo es el punto de entrada principal de la aplicación. Se encarga de interpretar los comandos ingresados por el usuario en la línea de comandos y ejecutar las funciones correspondientes. Los comandos disponibles son:

- `listar`: Lista todos los campers registrados.
- `agregar <nombre> <stack>`: Agrega un nuevo camper con el nombre y stack proporcionados.
- `buscar <nombre>`: Busca campers cuyo nombre coincida (parcial o totalmente) con el término proporcionado.

### `src/campers.js`
Este archivo contiene las funciones principales para gestionar los datos de los campers. Estas funciones interactúan con el archivo JSON donde se almacenan los datos:

- `leerCampers()`: Lee y devuelve la lista de campers desde el archivo JSON.
- `guardarCampers(lista)`: Guarda la lista de campers en el archivo JSON.
- `agregarCamper(nombre, stack)`: Agrega un nuevo camper a la lista y lo guarda en el archivo JSON.
- `listarCampers()`: Devuelve la lista completa de campers.
- `buscarCamperPorNombre(termino)`: Busca campers cuyo nombre coincida con el término proporcionado.

### `src/interactivo.js`
Este archivo implementa una versión interactiva de la aplicación utilizando el módulo `readline`. Permite al usuario registrar campers de manera interactiva, solicitando el nombre y el stack tecnológico a través de preguntas en la terminal.

### `data/campers.json`
Este archivo almacena los datos de los campers en formato JSON. Es el "almacén" principal de la aplicación. Si no existe, se crea automáticamente al agregar el primer camper.

## Requisitos

- Node.js versión 16.8.0 o superior.
- Un archivo `data/campers.json` vacío o inexistente (se creará automáticamente).

## Instalación

1. Clona este repositorio:
   ```bash
   git clone https://github.com/canuxantonio502/campuslands-cli-node-antonio
   cd campuslands-cli-node-antonio
   ```

2. Instala las dependencias:
    ```bash
   npm install
   ```
3. Uso

    Comandos disponibles
    - Listar campers:
        ```bash
       node src/index.js listar
       ```
    - Agregar un camper:
        ```bash
       node src/index.js <nombre> <stack>
       ```
    - Buscar campers por nombre:
        ```bash
       node src/index.js <nombre>
       ```
4. Modo interactivo:
    ```bash
   node src/interactivo.js
   ```

## Estructura del proyecto

    campuslands-cli-node-antonio/
    ├── src/
    │   ├── index.js          # Punto de entrada principal
    │   ├── campers.js        # Funciones para gestionar campers
    │   ├── interactivo.js    # Versión interactiva de la CLI
    ├── data/
    │   └── campers.json      # Archivo JSON para almacenar datos
    ├── package.json          # Configuración del proyecto y dependencias
    ├── README.md             # Documentación del proyecto
    
**Notas**:
Asegúrate de que el archivo data/campers.json tenga permisos de lectura y escritura.
Si encuentras algún error, verifica que estás utilizando una versión compatible de Node.js y que las dependencias están instaladas correctamente.