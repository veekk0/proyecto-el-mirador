# Sistema Integrado de Gestión de Gastos Comunes "El Mirador" 🏢✨

Este repositorio contiene el código fuente y la documentación técnica del ecosistema digital diseñado para el edificio comercial y residencial **"El Mirador"** (comunidad de 160 unidades)[cite: 6]. La plataforma automatiza el ciclo completo de cobro de gastos comunes, reduce los índices de morosidad mediante alertas automáticas y centraliza los flujos operativos de conserjería[cite: 6].

---

## 🚀 Prototipo Interactivo en Vivo

Para validar la usabilidad y los flujos de interacción con los usuarios antes de la integración final con la base de datos persistente, hemos desplegado un **Prototipo de Alta Fidelidad Interactivo** en la nube:

👉 **[Acceder al Prototipo - El Mirador](http://prototipo-el-mirador.vercel.app/)**

### 💻 Flujos Disponibles para Pruebas:
*   **Portal del Residente:** Panel de autogestión para revisar el estado de cuenta y el desglose de la colilla mensual[cite: 6].
*   **Simulación de Pago Express (3 Clics):** Flujo interactivo que emula la interacción y confirmación segura de una pasarela de pagos[cite: 6].
*   **Módulo de Conserjería / Soporte:** Interfaz responsiva para registrar y gestionar de forma móvil los tickets de mantenimiento de áreas comunes[cite: 6].

---

## 🏗️ Principios de Diseño Aplicados (Calidad del Código)

La construcción de los componentes de software en este repositorio se rige estrictamente por los siguientes pilares de la ingeniería de software:

*   **Alta Cohesión:** Los servicios están fuertemente especializados[cite: 6]. Por ejemplo, `GastoComunService` calcula exclusivamente los prorrateos por $mt^2$, delegando los pagos a `PagoService`.
*   **Bajo Acoplamiento:** Implementamos una arquitectura orientada a **API REST** y el **Patrón Repositorio**[cite: 6]. Esto aísla por completo la interfaz visual (Frontend en Vercel) de la capa persistente (PostgreSQL)[cite: 6].
*   **Encapsulamiento Robusto:** Las entidades críticas (`Pago`, `GastoComun`) protegen sus atributos financieros financieros mediante métodos controlados, impidiendo alteraciones arbitrarias de saldos[cite: 6].
*   **Abstracción de Terceros:** El procesamiento bancario se aísla mediante la interfaz abstracta `PaymentGateway`, ocultando la complejidad de las llamadas de red externas (Transbank / Webpay Plus).
*   **Modularidad Física:** El repositorio está segmentado en paquetes lógicos independientes (Residentes, Finanzas, Mantención) para permitir el desarrollo paralelo sin conflictos de código[cite: 6].

---

## 🧪 Evaluación de Usabilidad (Heurísticas de Nielsen)

El prototipo web desplegado en Vercel fue auditado bajo los 10 principios de usabilidad de Jakob Nielsen, garantizando una curva de aprendizaje mínima para la población mixta del condominio:

| Heurística Evaluada | Aplicación Práctica en el Prototipo | Estado |
| :--- | :--- | :--- |
| **#1: Visibilidad del estado** | Indicadores de carga (*spinners*) activos durante las transacciones y descargas. | ✅ Cumplido |
| **#2: Lenguaje real** | Uso de términos cotidianos del edificio ("Colilla", "Conserje", "Prorrateo")[cite: 6]. | ✅ Cumplido |
| **#3: Libertad del usuario** | Botones explícitos de "Cancelar" y "Volver atrás" en todos los formularios[cite: 6]. | ✅ Cumplido |
| **#4: Consistencia** | Paleta de colores, tipografías y botones de acción financiera totalmente estandarizados. | ✅ Cumplido |
| **#5: Prevención de errores** | Validación en tiempo real en los campos de formularios (RUT, correos, montos)[cite: 6]. | ✅ Cumplido |
| **#6: Reconocimiento** | Datos de la unidad y deudas precargados en el dashboard para evitar memorizar cifras[cite: 6]. | ✅ Cumplido |
| **#7: Flexibilidad y eficiencia** | Interfaz 100% *responsive* optimizada para celulares de conserjes y PCs de administradores. | ✅ Cumplido |
| **#8: Estética minimalista** | Pantallas limpias, enfocadas exclusivamente en la tarea actual y libres de ruido visual. | ✅ Cumplido |
| **#9: Recuperación de errores** | Mensajes de alerta claros ante fallas simuladas (ej: "Fondos insuficientes") en lugar de códigos crudos. | ✅ Cumplido |
| **#10: Ayuda** | Sección integrada de Preguntas Frecuentes e instructivos de lectura de cobros. | ✅ Cumplido |

> 📊 **Métrica de Eficiencia Destacada:** Las pruebas con usuarios en el entorno real de Vercel demostraron que la consulta y el pago completo del gasto común se ejecuta con un promedio de **3 clics** y un tiempo total menor a **35 segundos**.

---

## 🔧 Gobernanza y Control de Versiones

Para asegurar la trazabilidad del código y la estabilidad de los despliegues continuos, el equipo utiliza las siguientes herramientas y metodologías:

### 🏷️ Versionamiento Semántico (SemVer 2.0.0)
El proyecto se etiqueta bajo el formato estricto `X.Y.Z` (Mayor.Minor.Patch)[cite: 6]:
*   **X (Mayor):** Hitos institucionales o cambios de arquitectura estructurales que rompen compatibilidad[cite: 6].
*   **Y (Minor):** Nuevas funcionalidades o flujos de interfaz completamente compatibles[cite: 6].
*   **Z (Patch):** Corrección de bugs menores, parches de seguridad o ajustes tipográficos[cite: 6].

### 🛠️ Flujo de Trabajo en el Repositorio
1.  **Git:** Utilizado de forma distribuida para el aislamiento del trabajo mediante ramas de características (`feature/`)[cite: 6].
2.  **GitHub:** Actúa como el nodo central de gobernanza[cite: 6]. Se aplican *Pull Requests* obligatorios con revisión cruzada de código antes de fusionar cambios a la rama principal (`main`)[cite: 6].
3.  **Integración con Vercel:** Cada vez que se crea un *Pull Request* en GitHub, Vercel genera de manera automatizada una **Preview URL** independiente. Esto permite testear la usabilidad de las nuevas interfaces en vivo antes de pasarlas a producción.

---

## 🛠️ Stack Tecnológico Utilizado

*   **Frontend (Prototipo):** HTML5, CSS3, JavaScript (React / Next.js)
*   **Diseño UI:** Figma
*   **Despliegue e Infraestructura Cloud:** Vercel
*   **Control de Versiones:** Git & GitHub[cite: 6]
