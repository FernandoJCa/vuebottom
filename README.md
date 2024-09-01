# Proyecto de Botón de Formas en Vue

Este proyecto es una aplicación simple en Vue.js que demuestra un componente de botón interactivo con diferentes formas y contenido asociado.

## Estructura del Proyecto

El proyecto consta de los siguientes archivos principales:

- `compose.yaml`: Archivo de configuración de Docker Compose
- `Dockerfile`: Configuración de Docker para la aplicación
- `ShapeButton.vue`: Componente Vue para el botón de formas interactivo
- `App.vue`: Componente principal de la aplicación Vue
- `main.js`: Punto de entrada para la aplicación Vue

## Configuración

### Requisitos Previos

- Docker y Docker Compose instalados en su sistema
- Node.js y npm (para desarrollo local sin Docker)

### Ejecución con Docker

1. Clone el repositorio en su máquina local.
2. Navegue hasta el directorio del proyecto en su terminal.
3. Ejecute el siguiente comando para iniciar la aplicación:

   ```shell
   docker-compose up
   ```

4. La aplicación estará disponible en `http://localhost:8080`.

### Ejecución Local (sin Docker)

1. Clone el repositorio en su máquina local.
2. Navegue hasta el directorio del proyecto en su terminal.
3. Instale las dependencias:

   ```shell
   npm install
   ```

4. Inicie el servidor de desarrollo:

   ```shell
   npm run dev
   ```

5. La aplicación estará disponible en `http://localhost:8080`.

## Uso

La aplicación muestra un botón interactivo que puede cambiar de forma y revelar diferentes contenidos basados en la interacción del usuario:

1. Use el menú desplegable para seleccionar una forma (Círculo, Cuadrado o Triángulo).
2. Haga clic en el botón "Mostrar" para revelar el contenido asociado con la forma seleccionada.
3. Haga clic en el botón "Ocultar" para esconder el contenido.

### Características

- Círculo: Muestra un video de YouTube incrustado
- Cuadrado: Muestra una imagen (código QR)
- Triángulo: Presenta una animación de triángulos en movimiento

## Componentes

### ShapeButton.vue

Este es el componente interactivo principal de la aplicación. Incluye:

- Un selector de formas desplegable
- Un botón que cambia de forma según la selección
- Área de visualización de contenido para cada forma

### App.vue

El componente principal de la aplicación que:

- Define el diseño general
- Incluye el título y la descripción
- Incorpora el componente ShapeButton

## Desarrollo

Para propósitos de desarrollo, el proyecto está configurado con recarga en caliente (hot-reloading) habilitada. Cualquier cambio realizado en los componentes Vue se reflejará inmediatamente en el navegador.