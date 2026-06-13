# Definición de Requisitos del Sistema
**Proyecto:** Editor de Procesos Standalone según ISO/IEC/IEEE 24774
**Procesos aplicados:** ISO/IEC/IEEE 15288 / 12207 (Cláusulas 6.4.2 y 6.4.3)
**Metodología de Desarrollo:** Cascada (Waterfall)
 
---
 
## PARTE I: Stakeholder Needs and Requirements Definition (6.4.2)
 
### 1.1 Identificación de Stakeholders
| Stakeholder | Interés |
| :--- | :--- |
| La Empresa (Consultora) | Levantar varios procesos estandarizados para múltiples clientes de forma simultánea |
| Diseñador de procesos | Crear y mantener descripciones de procesos estructuradas |
| Analista de procesos / Auditor | Revisar la consistencia, completitud y cumplimiento legal de los procesos |
| Equipo de desarrollo | Implementar y mantener el producto independiente de integraciones externas |
| Cliente Final | Recibir exportables de procesos validados y con formato corporativo (PDF) |
 
### 1.2 Contexto Operacional
El sistema será utilizado desde un navegador web y permitirá crear, editar, guardar, cargar, imprimir y exportar descripciones de procesos alineadas con ISO/IEC/IEEE 24774. El usuario no necesitará conocimientos sobre JSON ni estructuras internas de almacenamiento.
 
### 1.3 Necesidades de los Stakeholders
*   **N1.** Crear descripciones de procesos de forma estructurada.
*   **N2.** Almacenar procesos para reutilización futura.
*   **N3.** Cargar procesos previamente creados.
*   **N4.** Validar la completitud de una descripción.
*   **N5.** Reorganizar actividades y tareas.
*   **N6.** Imprimir y exportar procesos a PDF.
*   **N7.** Utilizar una interfaz sencilla e intuitiva.
*   **N8.** Mantener relaciones coherentes entre elementos del proceso.
 
### 1.4 Requerimientos de Stakeholders
*   **REQ-STK-01:** Permitir crear una descripción de proceso con nombre, propósito y resultados esperados.
*   **REQ-STK-02:** Permitir agregar elementos definidos por ISO/IEC/IEEE 24774.
*   **REQ-STK-03:** Permitir guardar una descripción en un archivo `.pro`.
*   **REQ-STK-04:** Permitir cargar archivos `.pro`.
*   **REQ-STK-05:** Permitir modificar, eliminar y reorganizar elementos.
*   **REQ-STK-06:** Validar elementos obligatorios antes del guardado.
*   **REQ-STK-07:** Mostrar mensajes claros de validación.
*   **REQ-STK-08:** Generar una vista previa para impresión.
*   **REQ-STK-09:** Exportar la descripción a PDF.
*   **REQ-STK-10:** Mantener la estructura jerárquica del proceso.
 
---
 
## PARTE II: System Requirements Definition Process (6.4.3)
 
### Verificación de Salidas del Proceso (Outcomes Checklist - 6.4.3.2)
Como resultado de la ejecución de este proceso, se asegura y documenta el cumplimiento de las salidas exigidas por la norma:
- `[x]` **a)** La descripción del sistema, incluyendo interfaces, funciones y límites, está definida. *(Ref: Actividad a.1 y Requisitos Funcionales)*
- `[x]` **b)** Los requisitos del sistema (funcionales, rendimiento, proceso, no funcionales) y restricciones están definidos. *(Ref: Sección 2.1 y 2.2)*
- `[x]` **c)** Las medidas críticas de rendimiento (CPM) están definidas. *(Ref: Actividad c.2 mediante el RNF-03)*
- `[x]` **d)** Los requisitos del sistema han sido analizados. *(Ref: Actividad c.1)*
- `[x]` **e)** Los sistemas habilitadores/servicios para la definición de requisitos están disponibles. *(Ref: Actividad a.3)*
- `[x]` **f)** La trazabilidad desde los requisitos del sistema hacia los requerimientos de los stakeholders está desarrollada. *(Ref: Actividad d.2 - Matriz)*
 
---
 
Para dar cumplimiento formal a la norma, la transformación de las necesidades de los stakeholders a requisitos del sistema se ejecutó a través de las siguientes cuatro actividades (6.4.3.3):
 
### a) Preparación para la definición de requisitos del sistema
1.  **Límite funcional del sistema (Functional Boundary):** El sistema es una aplicación aislada (*standalone*). Sus límites (fronteras) están contenidos en el navegador del usuario. Sus entradas se limitan a archivos físicos locales `.pro` e interacción mediante teclado/ratón. Sus salidas son la alteración de la vista web, exportación a `.pro` y renderización de documentos PDF.
2.  **Estrategia de definición:** Al enmarcarse en un modelo de **Cascada**, la estrategia exige una elicitación y definición total de los requisitos de forma exhaustiva antes de avanzar al diseño. El documento de requisitos será objeto de un acuerdo de congelamiento (baseline).
3.  **Sistemas habilitadores:** Se requiere acceso a repositorios de código y a herramientas de modelado JSON Schema para validar los requisitos de las estructuras de datos antes del diseño.
 
### b) Definición de los requisitos del sistema
Esta actividad transforma operativamente los requisitos de los stakeholders (1.4) en las características explícitas y medibles que el sistema debe poseer.
 
#### 2.1 Requisitos Funcionales (Funciones requeridas)
*   **RF-01** Crear una nueva descripción de proceso.
*   **RF-02** Registrar nombre, propósito y resultados esperados.
*   **RF-03** Crear, modificar y eliminar elementos del proceso.
*   **RF-04** Asociar actividades al proceso.
*   **RF-05** Asociar tareas a actividades.
*   **RF-06** Reorganizar actividades y tareas.
*   **RF-07** Guardar archivos `.pro` basados en JSON.
*   **RF-08** Cargar archivos `.pro` y reconstruir la estructura.
*   **RF-09** Impedir guardar procesos incompletos.
*   **RF-10** Generar vista previa del proceso.
*   **RF-11** Permitir impresión.
*   **RF-12** Exportar a PDF.
*   **RF-13** Seleccionar orientación vertical u horizontal.
 
#### 2.2 Requisitos No Funcionales (Restricciones y características de calidad)
*   **RNF-01** El sistema deberá ser usable sin conocimientos de JSON.
*   **RNF-02** Compatibilidad con Chrome, Edge y Firefox.
*   **RNF-03** Tiempo de respuesta menor a 2 segundos para operaciones de edición.
*   **RNF-04** Conservación íntegra de la información almacenada.
*   **RNF-05** Portabilidad de archivos `.pro` entre instalaciones.
*   **RNF-06** Facilidad de mantenimiento y ampliación.
 
### c) Análisis de los requisitos del sistema
1.  **Análisis de atributos de calidad:** El conjunto de requisitos funcionales y no funcionales fue revisado y categorizado de modo que no dicte la implementación profunda, sea factible, verificable (ej. prueba de compatibilidad de navegadores RNF-02) y singular.
2.  **Medidas críticas de rendimiento (Critical Performance Measures):** Se establece formalmente el **RNF-03** (Tiempo de respuesta < 2s) como una MOP (Measure of Performance) crítica que el proceso de Arquitectura debe garantizar en sus análisis de *trade-off*.
3.  **Resolución de conflictos y restricciones:** El conflicto inicial entre "no exigir conocimientos técnicos de JSON" (RNF-01) y "generar archivos .pro basados en JSON" (RF-07) queda resuelto dictaminando que la GUI debe fungir como una barrera de abstracción total.
 
### d) Gestión de los requisitos del sistema
1.  **Establecimiento de Acuerdos y Línea Base:** Este conjunto unificado de RFs y RNFs constituye la versión formal a firmar por los *Stakeholders* para crear el Baseline.
2.  **Mantenimiento de Trazabilidad Bidireccional:** A continuación se evidencia cómo los requisitos del sistema satisfacen directa y exclusivamente las necesidades elicitadas de los stakeholders (Requisito 6.4.3.3.d.3 de la norma):
 
| Necesidad (6.4.2) | Requisito Stakeholder (6.4.2) | Requisito Sistema (6.4.3) Asignado |
| :--- | :--- | :--- |
| **N1** | REQ-STK-01 | RF-01, RF-02 |
| **N2** | REQ-STK-03 | RF-07 |
| **N3** | REQ-STK-04 | RF-08 |
| **N4** | REQ-STK-06 | RF-09 |
| **N5** | REQ-STK-05 | RF-06 |
| **N6** | REQ-STK-08, REQ-STK-09 | RF-10, RF-11, RF-12 |
| **N7** | REQ-STK-07 | RNF-01 |
| **N8** | REQ-STK-10 | RF-04, RF-05, RF-03 |
