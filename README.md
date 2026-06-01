# 🌊 WaterWay+ Backend API

<div align="center">
  <h3>🏆 Hackathon-Winning Project</h3>
  <p>Capa de API REST robusta y escalable diseñada para <strong>WaterWay+</strong>, una plataforma dedicada a la protección de ríos, reporte de incidentes ambientales y organización de acciones comunitarias.</p>
</div>

---

## 🚀 Tecnologías y Herramientas

El backend de **WaterWay+** está construido sobre un stack moderno y eficiente enfocado en alto rendimiento y escalabilidad:

*   **Runtime:** Node.js (con TypeScript / JavaScript ES6+)
*   **Framework:** Express.js / NestJS (arquitectura RESTful limpia)
*   **Base de Datos:** PostgreSQL / MongoDB (con Prisma ORM o Mongoose)
*   **Autenticación:** JSON Web Tokens (JWT) & bcrypt para encriptación de credenciales
*   **Geolocalización:** Soporte para coordenadas geográficas (Latitud y Longitud) para mapeo de incidentes de contaminación en ríos en tiempo real.

---

## 🛠️ Características Principales

*   🔒 **Autenticación Segura:** Registro e inicio de sesión de usuarios y organizaciones con manejo seguro de sesiones JWT.
*   📌 **Sistema de Reportes Georreferenciados:** Creación, lectura y actualización de reportes de contaminación ambiental con coordenadas precisas para visualización en mapa.
*   💧 **Monitoreo de Ríos:** Base de datos estructurada con información del estado actual de cuencas de agua y ríos principales.
*   🌱 **Eventos Comunitarios:** Gestión y coordinación de jornadas de limpieza y voluntariado ambiental.

---

## ⚙️ Configuración del Entorno

1. **Clona el repositorio:**
   ```bash
   git clone https://github.com/asanabria-2021067/waterway-backend.git
   cd waterway-backend
   ```

2. **Instala las dependencias:**
   ```bash
   npm install
   ```

3. **Configura las variables de entorno:**
   Crea un archivo `.env` en la raíz del proyecto y configura los siguientes parámetros:
   ```env
   PORT=5000
   DATABASE_URL="postgresql://usuario:contraseña@localhost:5432/waterway_db?schema=public"
   JWT_SECRET="tu_secreto_super_seguro_para_tokens"
   NODE_ENV="development"
   ```

4. **Ejecuta las migraciones de la base de datos (si aplica):**
   ```bash
   npx prisma migrate dev
   ```

5. **Inicia el servidor en desarrollo:**
   ```bash
   npm run dev
   ```

---

## 🛣️ API Endpoints (Estructura de Rutas)

### Autenticación
| Método | Endpoint | Descripción | Acceso |
| :--- | :--- | :--- | :--- |
| `POST` | `/api/auth/register` | Registro de nuevos usuarios / organizaciones | Público |
| `POST` | `/api/auth/login` | Inicio de sesión y entrega de JWT | Público |

### Reportes Ambientales
| Método | Endpoint | Descripción | Acceso |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/reports` | Obtiene todos los reportes de incidentes | Público |
| `POST` | `/api/reports` | Registra un nuevo reporte (con coordenadas) | Autorizado |
| `GET` | `/api/reports/:id` | Obtiene el detalle de un reporte específico | Público |
| `DELETE` | `/api/reports/:id` | Elimina o desactiva un reporte | Admin / Creador |

### Ríos & Estado de Cuencas
| Método | Endpoint | Descripción | Acceso |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/rivers` | Listado de ríos monitoreados | Público |
| `POST` | `/api/rivers` | Registrar un nuevo río al sistema | Admin |

### Eventos de Limpieza Comunitaria
| Método | Endpoint | Descripción | Acceso |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/events` | Listar todos los eventos de voluntariado programados | Público |
| `POST` | `/api/events` | Crear una nueva convocatoria de limpieza | Organizaciones |
| `POST` | `/api/events/:id/join` | Unirse como voluntario a un evento | Autorizado |

---

## 📈 Scripts Disponibles

*   `npm start`: Inicia el servidor en modo producción.
*   `npm run dev`: Inicia el servidor localmente con recarga automática (*nodemon*).
*   `npm run build`: Compila el código de TypeScript a JavaScript de producción (dist).
*   `npm test`: Ejecuta las pruebas unitarias y de integración.

---

## 🏆 Hackathon
Este proyecto fue galardonado en su respectiva Hackathon gracias a su enfoque práctico sobre el impacto ambiental y la facilidad de uso e integración móvil/web para la participación de las comunidades.

---
