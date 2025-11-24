# To-Do App

Aplicación de ejemplo para gestionar tareas (To-Do) con autenticación, verificación por correo y una interfaz con Tailwind CSS.

**Estado:** Proyecto local con servidor Express + MongoDB. Incluye vistas (HTML/JS), controladores y modelos.

**Tecnologías principales**
- **Node.js / Express:** Servidor y API.
- **MongoDB / Mongoose:** Persistencia de datos.
- **Tailwind CSS:** Estilos y utilidades.
- **JWT / bcrypt:** Autenticación y seguridad.
- **Nodemailer:** Envío de correos para verificación.

**Requisitos**
- Node.js (>= 18 recomendado)
- npm
- Una instancia de MongoDB (local o Atlas)

**Variables de entorno**
Configura las variables según tu entorno. Un archivo `.env` típico puede incluir:

```
NODE_ENV=dev
MONGO_URI_TEST=mongodb://localhost:27017/todo-dev
MONGO_URI_PROD=...            # URI de producción si aplica
JWT_SECRET=tu_clave_secreta
EMAIL_HOST=smtp.example.com
EMAIL_PORT=587
EMAIL_USER=usuario@example.com
EMAIL_PASS=contraseña
```

Nota: `config.js` usa `MONGO_URI_TEST` cuando `NODE_ENV !== 'production'` y `MONGO_URI_PROD` en producción.

**Instalación**
Clona el repositorio e instala dependencias:

```powershell
git clone <repo-url>
cd "To-Do"
npm install
```

**Ejecución**
- Modo desarrollo (con `nodemon`):

```powershell
npm run dev
```

- Modo producción:

```powershell
npm start
```

- Construcción/observador de Tailwind (para desarrollo de estilos):

```powershell
npm run tailwind-build
```

**Estructura del proyecto (resumen)**
- **`index.js` / `app.js`**: Punto de entrada del servidor.
- **`config.js`**: Configuración de URIs y URLs.
- **`controllers/`**: Lógica de rutas (login, logout, todos, users).
- **`models/`**: Modelos de Mongoose (`user.js`, `todo.js`).
- **`views/`**: HTML y JS del cliente (home, login, signup, todos, verify).
- **`middleware/`**: Middlewares como `auth.js`.
- **`src/`**: CSS compilado (output de Tailwind).

**Rutas y controladores importantes**
- **Auth:** rutas de inicio de sesión/registro y cierre de sesión — controladores en `controllers/login.js`, `controllers/logout.js`, `controllers/users.js`.
- **Todos:** creación, listado, edición y borrado de tareas — `controllers/todos.js`.

**Autenticación y verificación**
- El proyecto usa JWT para sesiones y `bcrypt` para el hashing de contraseñas.
- Se envían correos de verificación con `nodemailer` — revisa la configuración SMTP en tus variables de entorno.

**Contribuir**
- Abre un issue para proponer mejoras o reportar bugs.
- Para cambios importantes, crea una rama feature y abre un pull request con una descripción clara.

**Licencia**
- Licencia indicada en `package.json` (ISC).

---

