# Ejercicio: CRUD de Luchadores (Node.js + Express + MongoDB)

## Antes de empezar

1. Forkea el repositorio  
2. Clónalo en tu ordenador:
   ```bash
   git clone URL_GITHUB
   ```
3. Abre el proyecto en Visual Studio Code (o tu IDE preferido)

---

## Configuración inicial del proyecto

1. Inicializa el proyecto:

   ```bash
   npm init -y
   ```

2. Instala las dependencias necesarias:

   ```bash
   npm i express mongoose dotenv
   ```

3. Configura el proyecto como módulos:

   ```json
   "type": "module"
   ```

4. Añade un script de inicio:

   ```json
   "scripts": {
     "start": "node --watch server.js"
   }
   ```

5. Crea un archivo `.env` en la raíz del proyecto

---

## Variables de entorno

En el archivo `.env` debes añadir:

```env
MONGO_URI=TU_URI_DE_MONGODB
PORT=3000
```

La URI la debes obtener desde tu cuenta de MongoDB Atlas

---

## Objetivo

Construir una API REST con Node.js y Express que permita gestionar un CRUD de **luchadores de una empresa**.

El proyecto debe estar modularizado siguiendo una arquitectura por capas:

* routes
* controllers
* services
* models

Se trabajará con MongoDB utilizando Mongoose.

---

## Estructura del proyecto

```
├── app.js
├── server.js
│
├── routes/
│   └── fighters.routes.js
│
├── controllers/
│   └── fighters.controller.js
│
├── services/
│   └── fighters.service.js
│
├── models/
│   └── fighters.model.js
│
├── config/
│   └── db.js
│
├── .env
├── package.json
```

---

## ¿Qué debe hacer cada parte?

### server.js

* Levanta el servidor
* Lee el puerto desde `.env`
* Importa la app

---

### app.js

* Configura Express
* Usa middlewares necesarios
* Conecta las rutas

---

### config/db.js

* Configura la conexión a MongoDB
* Usa la URI del `.env`

---

### models/

* Define el esquema de Mongoose
* Representa la estructura del luchador

---

### routes/

* Define las rutas del CRUD
* No contiene lógica
* Redirige al controller

---

### controllers/

* Maneja `req` y `res`
* Llama a los services
* Controla la respuesta

---

### services/

* Contiene la lógica del negocio
* Interactúa con el modelo de Mongoose

---

## Datos del modelo

El luchador debe tener al menos:

* name (string)
* age (number)
* company (string)
* weight (number)
* active (boolean)

---

## Requisitos del CRUD

Debes implementar:

* GET    → obtener todos los luchadores
* GET    → obtener uno por ID
* POST   → crear un luchador
* PUT    → actualizar un luchador
* DELETE → eliminar un luchador

---

## Pistas

* Necesitas un middleware para leer JSON en las peticiones
* La conexión a la base de datos debe hacerse al iniciar el servidor
* Piensa dónde debe ir la lógica de acceso a datos
* El modelo de Mongoose define la estructura de los datos
* Usa import/export (ES Modules)
* No mezcles responsabilidades entre capas
* ¿Qué ocurre si un ID no existe?

---

## Testing con Postman

Debes probar todo el CRUD usando Postman:

### Comprueba:

* Crear un luchador correctamente
* Obtener todos los luchadores
* Obtener uno por ID
* Actualizar un luchador
* Eliminar un luchador

---

## Importante

* No pongas lógica en las rutas
* No accedas directamente a la base de datos desde el controller
* Usa el `.env` para datos sensibles
* Mantén el código limpio y modular

---

## Resultado esperado

Una API funcional con:

* CRUD completo en MongoDB
* Arquitectura modular clara
* Conexión a base de datos mediante Mongoose
* Probado completamente con Postman
