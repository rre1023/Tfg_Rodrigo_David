# Tfg_Rodrigo_David
TFG Aplicacion de Gestion de Reservas de Pistas de Pádel
# 🎾 Aplicación Integral de Gestión de Reservas de Pádel

![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Expo](https://img.shields.io/badge/Expo-000020?style=for-the-badge&logo=expo&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2CA5E0?style=for-the-badge&logo=docker&logoColor=white)

## 📖 Descripción del Proyecto

Este proyecto es el resultado de un **Trabajo de Fin de Grado (TFG)**. Consiste en una plataforma integral *Full-Stack* diseñada para digitalizar y centralizar la gestión de clubes de pádel. 

Resuelve los problemas habituales de la gestión analógica (overbooking, falta de control en pagos, dificultad para organizar partidos) mediante una arquitectura Cliente-Servidor. Ofrece una aplicación móvil nativa para los jugadores y un panel de administración robusto para la gestión del club, operando bajo un sistema transaccional de créditos virtuales.

---

## ✨ Funcionalidades Principales

### 👤 Para el Jugador (App Móvil)
* **Exploración de Clubes:** Búsqueda interactiva de clubes con integración directa a mapas nativos (Google Maps/Apple Maps).
* **Reservas Dinámicas:** Selección de pistas (muro/cristal) y horarios en tiempo real, bloqueando horas pasadas u ocupadas.
* **Monedero Virtual:** Sistema de pago automatizado mediante créditos virtuales (`1 reserva = 5 créditos`).
* **Sistema de Valoraciones:** Posibilidad de puntuar instalaciones (1-5 estrellas) con recálculo dinámico y burla de caché móvil para actualización instantánea.
* **Torneos:** Visualización e inscripción a eventos competitivos filtrados por nivel (Iniciación, Medio, Alto).

### 🛡️ Para el Administrador (Panel de Control)
* **Gestión de Usuarios (CRUD):** Visualización de la base de datos de usuarios, edición de niveles de juego y eliminación de cuentas.
* **Control Financiero:** Asignación manual de saldo (créditos) a los monederos de los usuarios.
* **Gestión de Infraestructuras:** Creación de nuevos clubes importando imágenes dinámicas mediante URLs públicas. Borrado seguro en cascada (evitando errores de clave foránea `FK_1451`).
* **Publicación de Torneos:** Creación de nuevos eventos definiendo fechas, niveles y plazas máximas.

---

## 🛠️ Stack Tecnológico y Arquitectura

El proyecto sigue una arquitectura **Cliente-Servidor** separada y paquetizada.

* **Frontend (App Móvil):** React Native, Expo, Expo Router, TypeScript. (Gestión de estado asíncrono y llamadas `fetch`).
* **Backend (API RESTful):** Java 17, Spring Boot 3, Spring Data JPA/Hibernate.
* **Seguridad:** Spring Security con JSON Web Tokens (JWT). Control de acceso basado en roles (RBAC) e inyección de tokens en *Headers*.
* **Base de Datos:** MySQL 8.0.
* **DevOps / Despliegue:** Docker y Docker Compose para garantizar la inmutabilidad del entorno.

---

## 🚀 Guía de Instalación y Despliegue (Local)

### Requisitos Previos
* [Docker Desktop](https://www.docker.com/products/docker-desktop/) instalado y en ejecución.
* [Node.js](https://nodejs.org/) (v16 o superior).
* App **Expo Go** instalada en tu dispositivo físico (iOS/Android).

### Paso 1: Levantar el Backend y Base de Datos (Docker)
El proyecto incluye la infraestructura como código. Para levantar la base de datos MySQL y el servidor Spring Boot de forma automática:



1. Clona este repositorio:
   ```bash
   git clone [https://github.com/TU_USUARIO/TU_REPOSITORIO.git](https://github.com/TU_USUARIO/TU_REPOSITORIO.git)


   2 Navega al directorio del backend:

Bash
cd backend-reservas

  3 Ejecuta Docker Compose:

Bash
docker compose up -d --build

Paso 4: Configurar y Arrancar el Frontend
Abre una nueva terminal y navega al directorio del frontend:

Bash
cd app-padel

 5 Instala las dependencias:

Bash
npm install

IMPORTANTE Configurar la IP: Busca el archivo de configuración en tu frontend donde defines la URL de tu API

Inicia la aplicación:

Bash
npx expo start
Escanea el código QR resultante con la cámara de tu móvil (iOS) o desde la app Expo Go (Android).
