# 🚀 API Spring Boot con Pipeline CI/CD Automatizado en AWS

![Java](https://img.shields.io/badge/Java-17-orange)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-green)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI%2FCD-blue)
![AWS Elastic Beanstalk](https://img.shields.io/badge/AWS-Elastic_Beanstalk-orange)
![Build Status](https://img.shields.io/badge/build-passing-brightgreen)

## 📋 Descripción del Proyecto

Este proyecto implementa una arquitectura completa de **DevOps** para una API REST desarrollada con **Spring Boot**. El objetivo principal no es solo la lógica de la aplicación, sino la automatización total del ciclo de vida del software, desde el desarrollo local hasta el despliegue en producción en la nube.

[cite_start]Se ha configurado un pipeline de **Integración Continua (CI)** y **Despliegue Continuo (CD)** utilizando **GitHub Actions** y **AWS Elastic Beanstalk**, garantizando que cada cambio en el código sea probado y desplegado automáticamente sin intervención manual[cite: 36, 41].

## 💼 Competencias Profesionales y Aplicación Real

Este proyecto simula un flujo de trabajo empresarial real. Demuestra las siguientes capacidades clave para un entorno laboral:

* **Automatización de Procesos:** Eliminación del error humano mediante pipelines automáticos. [cite_start]"Si funciona en local, el pipeline asegura que funcione en la nube"[cite: 48].
* [cite_start]**Infrastructure as Code (IaC):** Configuración de despliegues mediante archivos (`Procfile`, workflows YAML) en lugar de configuraciones manuales en servidor[cite: 1009].
* [cite_start]**Control de Calidad (QA):** El pipeline ejecuta tests automáticos antes de permitir cualquier despliegue, actuando como una barrera de calidad[cite: 112].
* [cite_start]**Entornos Reproducibles:** Uso de **Maven Wrapper** para garantizar que la versión de construcción sea idéntica en local, en el servidor de CI y en producción[cite: 252].
* [cite_start]**Gestión de Cloud (AWS):** Despliegue de aplicaciones Java en **Elastic Beanstalk**, gestionando versiones y entornos de producción[cite: 90].

## 🛠️ Stack Tecnológico

* [cite_start]**Lenguaje:** Java 17 (Amazon Corretto)[cite: 176].
* [cite_start]**Framework:** Spring Boot 3 (Web & Test starters)[cite: 914].
* [cite_start]**Gestión de Dependencias:** Maven (con Wrapper para consistencia)[cite: 226].
* **CI/CD:** GitHub Actions (Workflows para Build y Deploy).
* **Nube:** AWS Elastic Beanstalk (Entorno Java SE).
* **Control de Versiones:** Git & GitHub.

## 🔄 Arquitectura del Pipeline (CI/CD)

El flujo de trabajo automatizado sigue estos pasos estrictos:

1.  [cite_start]**Desarrollo Local:** El código se crea y valida en local[cite: 39].
2.  [cite_start]**Push al Repositorio:** Al hacer `git push` a la rama `main`, se dispara el workflow[cite: 76].
3.  **Integración Continua (CI):**
    * GitHub Actions descarga el código.
    * Configura el entorno Java 17.
    * [cite_start]Ejecuta `mvn test` para validar la compilación y pruebas unitarias[cite: 84].
    * *Si falla, el proceso se detiene.*
4.  **Despliegue Continuo (CD):**
    * [cite_start]Generación del artefacto `.jar` y preparación del `.zip` de despliegue (incluyendo `Procfile`)[cite: 1052].
    * [cite_start]Autenticación segura en AWS mediante **Secrets** (IAM)[cite: 1485].
    * [cite_start]Despliegue automático en el entorno de Elastic Beanstalk[cite: 1572].

## 🚀 Instalación y Ejecución Local

Para probar este proyecto en tu máquina local:

1.  **Clonar el repositorio:**
    ```bash
    git clone [https://github.com/tu-usuario/dam-ci-cd-api-001.git](https://github.com/tu-usuario/dam-ci-cd-api-001.git)
    cd dam-ci-cd-api-001
    ```

2.  **Ejecutar la aplicación (usando Maven Wrapper):**
    ```bash
    ./mvnw spring-boot:run
    ```
    [cite_start]*Nota: El wrapper asegura que uses la versión correcta de Maven sin instalar nada extra[cite: 252].*

3.  **Probar Endpoints:**
    * Status: `http://localhost:8080/api/estado`
    * Home: `http://localhost:8080/`

## ☁️ Endpoints de Producción (Demo)

La aplicación expone los siguientes endpoints REST:

| Método | Endpoint | Descripción | Respuesta Ejemplo |
| :--- | :--- | :--- | :--- |
| `GET` | `/` | Verificación de despliegue | `"Fin de la práctica..."` |
| `GET` | `/api/estado` | JSON con estado del servicio | [cite_start]`{"estado": "OK", "servicio": "..."}` [cite: 894] |

> [cite_start]**Nota:** El entorno AWS se gestiona mediante políticas de ahorro de costes, por lo que podría estar terminado si no está en uso activo[cite: 1769].

## 🔒 Seguridad y Configuración

* [cite_start]**Variables de Entorno:** El puerto se gestiona dinámicamente (`SERVER_PORT`) para compatibilidad con el proxy inverso de AWS (Nginx)[cite: 953].
* [cite_start]**Gestión de Secretos:** Las credenciales de AWS (`AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`) nunca se exponen en el código, se inyectan mediante GitHub Secrets durante el tiempo de ejecución del pipeline[cite: 1499].
* [cite_start]**Procfile:** Archivo de configuración que indica a Elastic Beanstalk cómo iniciar la aplicación Java correctamente[cite: 1010].

---
*Este proyecto fue desarrollado como parte de un programa avanzado de Arquitectura en la Nube.*
