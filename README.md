# tp2DiplomaturaMarSprint32025

## Descripción

Este proyecto es parte del Sprint 3 de la Diplomatura en Node.js 2024. Consiste en la creación de un sistema para gestionar superhéroes, incluyendo validaciones de datos y manejo de errores. El proyecto utiliza `express-validator` para validar las solicitudes y sigue buenas prácticas de desarrollo en Node.js.

## Características

- **Registro de superhéroes**: Permite registrar superhéroes con campos como nombre, edad, poderes, aliados, enemigos, entre otros.
- **Edición de superhéroes**: Permite actualizar los datos de un superhéroe existente.
- **Validaciones**: Uso de `express-validator` para validar los datos de entrada.
- **Manejo de errores**: Middleware personalizado para manejar errores de validación y devolver respuestas claras al cliente.

## Instalación

1. Clona este repositorio:
   ```bash
   git clone <URL_DEL_REPOSITORIO>
   ```
2. Navega al directorio del proyecto:
   ```bash
   cd tp2DiplomaturaMarSprint32025
   ```
3. Instala las dependencias:
   ```bash
   npm install
   ```

## Uso

### Scripts disponibles

- **Iniciar el servidor**:
```bash
node .\app
```

### Endpoints principales

#### Registro de superhéroes
- **URL**: `/api/superheroes`
- **Método**: `POST`
- **Cuerpo de la solicitud**:
  ```json
  {
      "nombreSuperHeroe": "Omni-Man",
      "nombreReal": "Nolan Grayson",
      "edad": 500,
      "poderes": ["Vuelo", "Fuerza sobrehumana"],
      "planetaOrigen": "Viltrum",
      "debilidad": "Emociones humanas",
      "aliados": ["Invincible"],
      "enemigos": ["Cecil Stedman"]
  }
  ```

#### Edición de superhéroes
- **URL**: `/api/superheroes/:id`
- **Método**: `PUT`
- **Cuerpo de la solicitud**:
  ```json
  {
      "nombreSuperHeroe": "Omni-Man",
      "edad": 501
  }
  ```

## Estructura del proyecto

```
src/
├── routes/
│   ├── validations/
│   │   ├── superHerovalidationRules.mjs
│   ├── errorMiddleware/
│   │   ├── superHeroeErrorMiddleware.mjs
├── index.js
```

## Dependencias principales

- **express**: Framework para construir la API.
- **express-validator**: Para validaciones de datos.
- **nodemon**: Herramienta para desarrollo en tiempo real.

## Contribución

1. Haz un fork del repositorio.
2. Crea una rama para tu funcionalidad:
   ```bash
   git checkout -b nueva-funcionalidad
   ```
3. Realiza tus cambios y haz un commit:
   ```bash
   git commit -m "Agrega nueva funcionalidad"
   ```
4. Envía tus cambios:
   ```bash
   git push origin nueva-funcionalidad
   ```
5. Abre un Pull Request.
