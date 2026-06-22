# Sistema Integrado de Gestión de Gastos Comunes "El Mirador"

![Versión](https://img.shields.io/badge/version-2.0-blue)
![Estado](https://img.shields.io/badge/estado-en%20reestructuraci%C3%B3n-orange)
![Nota E2](https://img.shields.io/badge/Nota%20E2-5.5-green)

Este repositorio alberga el diseño de arquitectura y los artefactos de software del **Sistema Integrado de Gestión de Gastos Comunes "El Mirador"**. La plataforma automatiza los flujos financieros y operacionales para una comunidad de 160 departamentos, atacando problemas críticos de morosidad, falta de transparencia y gestión manual ineficiente.

---

## 👥 Integrantes y Mantenedores
* **Benjamín Arellano**
* **Agustín Vásquez**
* **Nicolás Ruiz**

*Institución:* Duoc UC — Ingeniería de Software (Sección 001D / 002D)

---

## 🎯 Alcance del Sistema

La solución tecnológica abarca de forma centralizada los siguientes componentes:
* **Módulo de Gestión de Residentes:** Registro detallado de copropietarios y arrendatarios vinculados a las 160 unidades habitacionales.
* **Módulo de Finanzas:** Algoritmia para el cálculo automatizado y emisión de cuotas de gastos comunes basado en prorrateo indexado por metros cuadrados (`mt2_prorrateo`).
* **Módulo de Pagos:** Registro de transacciones con pasarela electrónica externa y generación de recibos individuales en formato PDF.
* **Módulo de Mantención:** Centralización de solicitudes de mantenimiento de áreas comunes y gestión de quejas administrado por conserjería.

### 🚫 Exclusiones Formales
* No incluye el cálculo de remuneraciones ni control de asistencia para los 2 conserjes y 3 personas de mantención.
* No incluye integraciones con sistemas físicos de control de acceso (barreras o cámaras).

---

## 🏗️ Resumen de la Arquitectura (Modelo 4+1)

El sistema se rige bajo los lineamientos del **Documento de Arquitectura de Software (DAS)** del proyecto:
* **Estilo Arquitectónico:** Arquitectura Basada en Capas (*Layered Architecture*) segregando estrictamente la Presentación (Frontend), Lógica de Negocio (Core) y Acceso a Datos.
* **Patrón MVC (Modelo-Vista-Controlador):** Implementado para independizar las interfaces de los usuarios de las reglas lógicas financieras complejos.
* **Patrón Repositorio:** Responsable exclusivo del mapeo objeto-relacional y la inyección de consultas limpias para asegurar el desacoplamiento.
* **Ecosistema Tecnológico:** Frontend liviano Web UI (SPA), Backend con arquitectura API REST, persistencia relacional estricta bajo el motor **PostgreSQL** (aislado en una VPC privada) e integración Server-to-Server mediante API REST con **Transbank / Webpay Plus**.

---

## 🚦 Reglas y Criterios de Evaluación de Calidad

Cada entrega de software es auditada rigurosamente bajo las siguientes métricas cuantitativas fijadas en el diseño:

| Atributo de Calidad | Criterio de Aceptación Formal | Mecanismo de Verificación |
| :--- | :--- | :--- |
| **Rendimiento bajo Estrés** | Latencia máxima < 3 segundos en la descarga de recibos PDF, sosteniendo una carga concurrente simulada de 160 usuarios simultáneos. | Pruebas de inyección de carga ejecutadas con **Apache JMeter** en ambiente de QA. |
| **Seguridad de Datos** | Cero (0) vulnerabilidades de nivel crítico o alto expuestas en la API. Uso imperativo de tokens **JWT** para validación de sesiones seguras. | Análisis estático automático del código fuente mediante **SonarQube** en el pipeline CI/CD. |
| **Disponibilidad (SLA)** | Disponibilidad operativa continua del 99.9% de uptime mensual de los servicios web centrales. | Telemetría y monitoreo automatizado con alertas configuradas en **AWS CloudWatch**. |
| **Usabilidad** | Un residente sin capacitación previa debe poder consultar y pagar su Gasto Común de manera fluida en un **máximo de 3 clics** desde la pantalla de inicio. | Test de usuarios (*User Testing*) con perfiles reales sumado a una **Evaluación Heurística de Nielsen**. |
