#  MANTRA - Plataforma de Gestión de Eventos y Comunidad

[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-18-336791?style=flat&logo=postgresql)](https://www.postgresql.org/)
[![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=flat&logo=nodedotjs)](https://nodejs.org/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=flat&logo=javascript)](https://developer.mozilla.org/es/docs/Web/JavaScript)

> **Solución integral para la centralización, organización y socialización de eventos, conectando a organizadores y asistentes en un entorno digital seguro y escalable.**

🔗 **[Ver Demo Frontend (Estática)](https://julio-milan.github.io/MANTRA-ESTATICO/)** | 📂 **[Ver Documentación](#-documentación)**

---

##  Sobre el Proyecto

MANTRA nace de la necesidad de resolver la fragmentación en la gestión de eventos. Las plataformas tradicionales suelen separar la organización del evento de la interacción entre asistentes. 

Esta solución unifica ambos mundos en una sola plataforma, permitiendo que la experiencia del usuario fluya antes, durante y después del evento. A diferencia de un CRUD básico, MANTRA incorpora una capa social (comunidades, publicaciones y chat) y un motor de base de datos robusto que garantiza la integridad de los datos mediante roles, restricciones y validaciones de negocio estrictas.

---

##  Funcionalidades Principales

-  **Gestión de Roles:** Flujo diferenciado y seguro para *Organizadores* (creación, estadísticas, reputación) y *Participantes* (descubrimiento, registro, reseñas).
-  **Ciclo de Vida del Evento:** Creación, edición, clasificación por categorías y monitoreo de asistencia en tiempo real.
-  **Capa Social:** Muro de publicaciones, intercambio de experiencias y mensajería privada entre usuarios.
-  **Seguridad a Nivel de Datos:** Implementación de control de acceso (DCL), restricciones de dominio (CHECK, UNIQUE) e integridad referencial (CASCADE/RESTRICT) directamente en PostgreSQL.

---

##  Stack Tecnológico

| Área | Tecnologías |
| :--- | :--- |
| **Base de Datos** | PostgreSQL 18, pgAdmin 4 (Diseño EER, Normalización, DCL) |
| **Backend** | Node.js, Express.js |
| **Frontend** | HTML5, CSS3, JavaScript (ES6+), Bootstrap |
| **Control de Versiones** | Git, GitHub |
| **Despliegue** | Render (Backend - Capa Gratuita) / GitHub Pages (Frontend) |

---

##  Estructura del Proyecto

El repositorio ha sido estructurado para separar las responsabilidades del cliente y el servidor, facilitando el mantenimiento y la escalabilidad:

    mantra/
    ├── backend/
    │   ├── index.js            # Punto de entrada del servidor (Node/Express)
    │   ├── package.json        # Dependencias y scripts del backend
    │   └── .gitignore          # Reglas para ignorar node_modules y .env
    ├── frontend/
    │   ├── index.html          # Página principal
    │   ├── dashboard-organizador.html # Panel de control
    │   ├── feed-eventos.html   # Listado de eventos
    │   ├── comunidad.html      # Muro social
    │   ├── chat.html           # Mensajería en tiempo real
    │   └── ...                 # Resto de vistas HTML
    ├── docs/
    │   └── Entrevista_MANTRA.pdf # Documento de requerimientos
    ├── capturas/               # Evidencias visuales de la UI
    ├── uploads/                # Directorio para archivos subidos
    └── README.md

---

##  Cómo ejecutar el proyecto localmente

Para levantar el entorno de desarrollo en tu máquina, sigue estos pasos:

1. Clona el repositorio:
    git clone https://github.com/JULIO-MILAN/mantra.git
    cd mantra

2. Configura el Backend:
    cd backend
    npm install

3. Variables de entorno:
   - Crea un archivo `.env` dentro de la carpeta `backend/`.
   - Añade tus credenciales de PostgreSQL:
    PORT=3000
    DATABASE_URL=postgresql://tu_usuario:tu_password@localhost:5432/mantra_db

4. Inicia el servidor:
    node index.js

5. Ejecuta el Frontend:
   - Abre el archivo `frontend/index.html` directamente en tu navegador, o utiliza una extensión como "Live Server" en VS Code para servir los archivos estáticos.

---

##  Demo y Despliegue

 **Nota sobre el entorno de demostración:**  
El backend de este proyecto fue desplegado originalmente en Render (capa gratuita). Debido a las limitaciones de inactividad de este servicio, actualmente se mantiene activa la **versión estática del frontend** para fines de demostración visual de la interfaz y la experiencia de usuario (UI/UX).

-  **[Ver Versión Estática (Frontend Demo)](https://julio-milan.github.io/MANTRA-ESTATICO/)**
-  **Prueba local completa:** Sigue los pasos de la sección [⚙️ Cómo ejecutar el proyecto localmente](#-cómo-ejecutar-el-proyecto-localmente) para interactuar con la base de datos y la API en tiempo real.

---

##  Retos de Ingeniería y Aprendizajes

- **Manejo de Integridad Referencial Compleja:** 
  - *Reto:* Gestionar las relaciones N:M entre usuarios, eventos y categorías, asegurando que la eliminación de un evento no dejara datos huérfanos.
  - *Solución:* Implementación estratégica de `ON DELETE CASCADE` y `ON DELETE RESTRICT` en las tablas de `Asistencia` y `Reseñas`.
  - *Aprendizaje:* Comprendí la importancia de delegar la integridad de los datos a la capa de base de datos (PostgreSQL) en lugar de confiar únicamente en la validación del backend.

- **Investigación y Autodidacta:** 
  - *Reto:* Implementar un sistema de roles y permisos (DCL) que no es común en tutoriales básicos de Node.js.
  - *Solución:* Investigación en la documentación oficial de PostgreSQL para diseñar un esquema de permisos a nivel de base de datos, complementándolo con middleware de autorización en Express.

---

##  Próximos Pasos y Mejoras Futuras

Como proyecto en evolución, tengo identificadas las siguientes áreas de mejora para llevarlo a un entorno de producción real:

1. **Refactorización a Arquitectura MVC:** Separar la lógica actual del `index.js` en **Routes** (endpoints), **Controllers** (lógica de negocio) y **Models** (capa de datos) para mejorar la mantenibilidad.
2. **Containerización:** Migrar el entorno a **Docker** (Dockerfile + docker-compose) para garantizar la consistencia entre entornos de desarrollo y producción.
3. **Testing:** Implementar pruebas unitarias e integración (Jest/Supertest) para validar las reglas de negocio críticas.
4. **Optimización de Consultas:** Añadir índices en columnas de búsqueda frecuente para mejorar el rendimiento a medida que crece el volumen de datos.

---

## Documentación

- 📑 [Ver Documento de Entrevista y Requerimientos](./docs/Entrevista_MANTRA.pdf)

##  Capturas de Pantalla

<details>
<summary><b>🖼️ Click para ver galería completa</b></summary>
<br>

<table>
<tr>
<td align="center">
<b>Landing Page</b><br><br>
<img src="capturas/landing.png" width="400">
</td>

<td align="center">
<b>Feed de Eventos</b><br><br>
<img src="capturas/feed-eventos.png" width="400">
</td>
</tr>

<tr>
<td align="center">
<b>Dashboard Organizador</b><br><br>
<img src="capturas/dashborad-organizador.png" width="400">
</td>

<td align="center">
<b>Comunidad</b><br><br>
<img src="capturas/comunidad.png" width="400">
</td>
</tr>

<tr>
<td align="center">
<b>Chat en Tiempo Real</b><br><br>
<img src="capturas/chat.png" width="400">
</td>

<td align="center">
<b>Perfil de Usuario</b><br><br>
<img src="capturas/perfil.png" width="400">
</td>
</tr>
</table>

</details>


---
## Diagramas ER Y EEX

<details>
<summary><b>🖼️ Click para ver los diagramas</b></summary>
<br>

<table>
<tr>
<td align="center">
<b>EER</b><br><br>
<img src="https://github.com/user-attachments/assets/b353fb68-700c-46cc-b2f5-3784f5105ce4" width="400">
</td>

<td align="center">
<b>ER</b><br><br>
<img src="https://github.com/user-attachments/assets/0f419152-cdcc-4451-9c05-bc0ddb101c24" width="400">
</td>
</tr>
</tr>
</table>

</details>
---

## Autor

- **Julio Milan** - [GitHub](https://github.com/JULIO-MILAN) | 

> *Proyecto desarrollado con enfoque en la aplicación práctica de arquitectura de bases de datos, desarrollo web full-stack y buenas prácticas de ingeniería de software.*
