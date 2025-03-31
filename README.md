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
- **Respuesta de ejemplo**:
  ```json
  {
      "message": "Superhéroe registrado correctamente",
      "data": {
          "id": 1,
          "nombreSuperHeroe": "Omni-Man",
          "nombreReal": "Nolan Grayson",
          "edad": 500,
          "poderes": ["Vuelo", "Fuerza sobrehumana"],
          "planetaOrigen": "Viltrum",
          "debilidad": "Emociones humanas",
          "aliados": ["Invincible"],
          "enemigos": ["Cecil Stedman"]
      }
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
- **Respuesta de ejemplo**:
  ```json
  {
      "message": "Superhéroe actualizado correctamente",
      "data": {
          "id": 1,
          "nombreSuperHeroe": "Omni-Man",
          "nombreReal": "Nolan Grayson",
          "edad": 501,
          "poderes": ["Vuelo", "Fuerza sobrehumana"],
          "planetaOrigen": "Viltrum",
          "debilidad": "Emociones humanas",
          "aliados": ["Invincible"],
          "enemigos": ["Cecil Stedman"]
      }
  }
  ```


#### Obtener todos los superhéroes
- **URL**: `/api/superheroes`
- **Método**: `GET`
- **Descripción**: Devuelve una lista de todos los superhéroes registrados.
- **Respuesta de ejemplo**:
  ```json
  [
      {
          "id": 1,
          "nombreSuperHeroe": "Omni-Man",
          "nombreReal": "Nolan Grayson",
          "edad": 500,
          "poderes": ["Vuelo", "Fuerza sobrehumana"],
          "planetaOrigen": "Viltrum",
          "debilidad": "Emociones humanas",
          "aliados": ["Invincible"],
          "enemigos": ["Cecil Stedman"]
      },
      {
          "id": 2,
          "nombreSuperHeroe": "Invincible",
          "nombreReal": "Mark Grayson",
          "edad": 20,
          "poderes": ["Vuelo", "Fuerza sobrehumana"],
          "planetaOrigen": "Tierra",
          "debilidad": "Inexperiencia",
          "aliados": ["Omni-Man"],
          "enemigos": ["Reanimen"]
      }
  ]
  ```

#### Obtener un superhéroe por ID
- **URL**: `/api/superheroes/:id`
- **Método**: `GET`
- **Descripción**: Devuelve los datos de un superhéroe específico según su ID.
- **Parámetros**:
  - `id` (path): ID del superhéroe a buscar.
- **Respuesta de ejemplo**:
  ```json
  {
      "id": 1,
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

#### Eliminar un superhéroe por ID
- **URL**: `/api/superheroes/:id`
- **Método**: `DELETE`
- **Descripción**: Elimina un superhéroe específico según su ID y devuelve los datos del superhéroe eliminado.
- **Parámetros**:
  - `id` (path): ID del superhéroe a eliminar.
- **Respuesta de ejemplo**:
  ```json
  {
      "message": "Superhéroe eliminado correctamente",
      "data": {
          "id": 1,
          "nombreSuperHeroe": "Omni-Man",
          "nombreReal": "Nolan Grayson",
          "edad": 500,
          "poderes": ["Vuelo", "Fuerza sobrehumana"],
          "planetaOrigen": "Viltrum",
          "debilidad": "Emociones humanas",
          "aliados": ["Invincible"],
          "enemigos": ["Cecil Stedman"]
      }
  }
  ```

#### Eliminar un superhéroe por nombre
- **URL**: `/api/superheroes`
- **Método**: `DELETE`
- **Descripción**: Elimina un superhéroe específico según su nombre y devuelve los datos del superhéroe eliminado.
- **Cuerpo de la solicitud**:
  ```json
  {
      "nombreSuperHeroe": "Omni-Man"
  }
  ```
- **Respuesta de ejemplo**:
  ```json
  {
      "status": "success",
      "message": "Superhéroe eliminado correctamente",
      "data": {
          "id": 1,
          "nombreSuperHeroe": "Omni-Man",
          "nombreReal": "Nolan Grayson",
          "edad": 500,
          "poderes": ["Vuelo", "Fuerza sobrehumana"],
          "planetaOrigen": "Viltrum",
          "debilidad": "Emociones humanas",
          "aliados": ["Invincible"],
          "enemigos": ["Cecil Stedman"]
      }
  }
  ```

## Estructura del proyecto

```
src/
├── config/
│   ├── dbConfig.mjs                   # Configuración de la base de datos
├── controllers/
├── models/
│   ├── superHero.mjs                   # Modelo de datos de superhéroes
├── repositories/
│   ├── IRepository.mjs                  # Interfaz genérica para repositorios
│   ├── SuperHeroRepository.mjs          # Repositorio específico para superhéroes
├── routes/
│   ├── errorMiddleware/
│   │   ├── superHeroeErrorMiddleware.mjs # Middleware de manejo de errores
│   ├── validations/
│   │   ├── superHeroValidationRules.mjs  # Reglas de validación para superhéroes
│   ├── superHeroRoutes.mjs               # Rutas para los endpoints de superhéroes
├── services/
│   ├── superheroesService.mjs            # Lógica de negocio de superhéroes
├── views/
│   ├── responseView.mjs                  # Formato de respuesta para la API
├── .gitignore
├── app.mjs                               # Archivo principal de la aplicación
├── package-lock.json
├── package.json
└── README.md
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
