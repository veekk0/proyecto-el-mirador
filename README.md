# Sistema Integrado de Gestión de Gastos Comunes "El Mirador"

![Institución](https://img.shields.io/badge/Institución-Duoc%20UC-blue)
![Version](https://img.shields.io/badge/Versión-3.0.0-green)
![Despliegue](https://img.shields.io/badge/Despliegue-Vercel-black)

Este repositorio contiene la arquitectura de software, especificaciones técnicas y el prototipo funcional del **Sistema Integrado de Gestión de Gastos Comunes "El Mirador"**. La plataforma está diseñada para centralizar, automatizar y transparentar la administración operativa y financiera de la comunidad.

---

## 📋 Contexto del Problema

El edificio “El Mirador” cuenta con **160 departamentos** y una población mixta de propietarios y arrendatarios. Actualmente, enfrenta una problemática crítica derivada de una gestión administrativa y operativa mediante procesos manuales e ineficientes. La falta de digitalización ha derivado en:
* Altos índices de morosidad y escasez de liquidez para mantenciones esenciales.
* Una profunda crisis de confianza y falta de transparencia entre los residentes y la administración en relación al uso de fondos.

## 🚀 Alcance del Sistema (Módulos)

El sistema es una aplicación web y móvil centralizada y bifronte:
1. **Módulo de Gestión de Residentes:** Registro de la información de copropietarios, arrendatarios y la relación con los 160 departamentos.
2. **Módulo de Finanzas:** Cálculo automatizado y emisión de cuotas de gastos comunes basado en prorrateo.
3. **Módulo de Pagos:** Integración para el registro de pagos y generación de recibos digitales (PDF).
4. **Módulo de Mantención:** Sistema centralizado de tickets para solicitudes de mantenimiento de áreas comunes y gestión de quejas, administrado por el personal de conserjería.

---

## 🏗️ Arquitectura y Patrones

El sistema se fundamenta en el **Modelo de 4+1 Vistas** bajo un enfoque de **Arquitectura Basada en Capas** (Presentación, Aplicación/Negocio, Dominio y Persistencia).

### Patrones Aplicados:
* **Modelo-Vista-Controlador (MVC):** Separa la interfaz del residente de la lógica de negocio.
* **Patrón Repositorio:** Centraliza y estandariza las consultas hacia la base de datos de forma segura, aislando los errores.

---

## 🌐 Enlaces del Proyecto

* **Prototipo Funcional (Vercel):** [https://prototipo-el-mirador.vercel.app/](https://prototipo-el-mirador.vercel.app/)
* **Presentación (Canva):** [https://www.canva.com/design/DAHKnpnAzVI/iJ9Lk--olN-AOLqbMJkh4Q/edit](https://www.canva.com/design/DAHKnpnAzVI/iJ9Lk--olN-AOLqbMJkh4Q/edit)

---

## 📊 Requisitos No Funcionales Críticos

* **Rendimiento:** Tiempos de carga menores a 3 segundos, soportando los picos de tráfico de los 160 departamentos durante los primeros 5 días del mes.
* **Seguridad:** Protección rigurosa de datos mediante autenticación segura, limitando la visualización a la propia deuda.
* **Disponibilidad:** Acceso 24/7 para permitir la emisión de tickets de emergencia fuera de horario.
* **Usabilidad:** Interfaz sumamente intuitiva y fácil de aprender, permitiendo realizar el pago en un máximo de 3 clics (validado mediante Evaluación Heurística de Nielsen).

---

## ⚙️ Control de Versiones

* **Modelo de Versionamiento:** Versionamiento Semántico (SemVer). Comunica de forma explícita el impacto y la compatibilidad que contiene cada cambio en el repositorio.
* **Herramientas:** Se emplea **Git** para la alta eficiencia en la gestión de ramas locales y **GitHub** para la gobernanza del código en la nube (Reglas de Protección de Ramas y automatización CI/CD).

---

## 👥 Equipo de Desarrollo (Grupo 4)
* **Benjamin Arellano**
* **Agustin Vasquez**
* **Nicolas Ruiz**
