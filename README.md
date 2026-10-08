# 🎉 MANTRA - Plataforma de Gestión de Eventos y Comunidad

[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-18-336791?style=flat&logo=postgresql)](https://www.postgresql.org/)
[![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=flat&logo=nodedotjs)](https://nodejs.org/)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=flat&logo=javascript)](https://developer.mozilla.org/es/docs/Web/JavaScript)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

> **Solución integral para la centralización, organización y socialización de eventos, conectando a organizadores y asistentes en un entorno digital seguro y escalable.**

🔗 **[Ver Demo Frontend (Estática)](https://tu-link-de-la-version-estatica.com)** | 📂 **[Ver Documentación de BD](#-diagramas-y-documentación)**

---

## 📖 Sobre el Proyecto

MANTRA nace de la necesidad de resolver la fragmentación en la gestión de eventos. Las plataformas tradicionales suelen separar la organización del evento de la interacción entre asistentes. 

Esta solución unifica ambos mundos en una sola plataforma, permitiendo que la experiencia del usuario fluya antes, durante y después del evento. A diferencia de un CRUD básico, MANTRA incorpora una capa social (comunidades, publicaciones y chat) y un motor de base de datos robusto que garantiza la integridad de los datos mediante roles, restricciones y validaciones de negocio estrictas.

## ✨ Funcionalidades Principales

- 👤 **Gestión de Roles:** Flujo diferenciado y seguro para *Organizadores* (creación, estadísticas, reputación) y *Participantes* (descubrimiento, registro, reseñas).
- 🎉 **Ciclo de Vida del Evento:** Creación, edición, clasificación por categorías y monitoreo de asistencia en tiempo real.
- 🤝 **Capa Social:** Muro de publicaciones, intercambio de experiencias y mensajería privada entre usuarios.
- 🔒 **Seguridad a Nivel de Datos:** Implementación de control de acceso (DCL), restricciones de dominio (CHECK, UNIQUE) e integridad referencial (CASCADE/RESTRICT) directamente en PostgreSQL.

---

## 🛠️ Stack Tecnológico

| Área | Tecnologías |
| :--- | :--- |
| **Base de Datos** | PostgreSQL 18, pgAdmin 4 (Diseño EER, Normalización, DCL) |
| **Backend** | Node.js, Express.js |
| **Frontend** | HTML5, CSS3, JavaScript (ES6+), Bootstrap |
| **Control de Versiones** | Git, GitHub |
| **Despliegue** | Render (Backend - Capa Gratuita) / GitHub Pages (Frontend) |

---

## ⚙️ Cómo ejecutar el proyecto localmente

Para que cualquier desarrollador pueda levantar el proyecto, sigue estos pasos:

1. Clona el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/mantra.git
   cd mantra
   
