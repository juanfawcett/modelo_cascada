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


# ENTREGABLES DEL PROCESO DE DEFINICIÓN DE REQUERIMIENTOS Y NECESIDADES DE LOS INTERESADOS 6.4.2. ISO/IEC/IEEE
## Stakeholder Needs and Requirements Definition
### ISO/IEC/IEEE 12207:2017 — Cláusula 6.4.2

---

| Campo | Valor |
| :--- | :--- |
| **Proyecto** | Editor de Procesos Standalone según ISO/IEC/IEEE 24774 |
| **Metodología** | Cascada (Waterfall) |
| **Norma aplicada** | ISO/IEC/IEEE 12207:2017, ISO/IEC/IEEE 15288:2015 |
| **Proceso** | 6.4.2 — Stakeholder Needs and Requirements Definition |
| **Versión** | 1.0 — Baseline (Congelado) |
| **Estado** | Aprobado para baseline |

---

## 1. Introducción y Propósito del Proceso

El proceso 6.4.2 — Stakeholder Needs and Requirements Definition — de la norma ISO/IEC/IEEE 12207:2017 tiene como propósito identificar a los stakeholders que interactúan con el sistema a lo largo de su ciclo de vida, y definir sus necesidades, expectativas y restricciones, transformándolas en un conjunto de requisitos verificables que el sistema debe satisfacer.

Este documento reúne el conjunto completo de entregables exigidos por dicho proceso para el proyecto "Editor de Procesos Standalone", constituyendo la línea base (baseline) de necesidades y requisitos de stakeholders conforme a la metodología Cascada adoptada.

### 1.1 Resultados esperados del proceso (Outcomes 6.4.2.2)

La norma define los siguientes resultados que este proceso debe producir:

- **(a)** Se identifican los stakeholders que tienen interés en el sistema de software a lo largo de su ciclo de vida.
- **(b)** Se define un conjunto de requisitos de stakeholders respecto a su contexto, incluyendo restricciones operacionales y del entorno.
- **(c)** Se identifican y priorizan las necesidades, expectativas, restricciones e interfaces de los stakeholders.
- **(d)** Se define el concepto de operación (ConOps) y los escenarios de uso del sistema.
- **(e)** Se define el concepto de uso del sistema a lo largo de su ciclo de vida (incluyendo retiro).
- **(f)** Los requisitos de stakeholders se analizan para detectar inconsistencias, omisiones y conflictos.
- **(g)** Se establece la trazabilidad entre los requisitos de stakeholders y las necesidades elicitadas.
- **(h)** Los requisitos de stakeholders son aprobados y se establece una línea base.

---

## ENTREGABLE 1: Registro de Stakeholders

> **Outcome cubierto: (a) — Identificación de partes interesadas.**

Este entregable documenta formalmente a todos los stakeholders identificados para el proyecto, su categoría, interés principal en el sistema, nivel de influencia y modo de participación durante el proceso de definición de requisitos.

*Tabla 1.1 — Registro completo de stakeholders*

| ID | Stakeholder | Categoría | Interés principal | Influencia | Modo de participación |
| :---: | :--- | :--- | :--- | :--- | :--- |
| **STK-01** | Diseñador de Procesos | Usuario primario | Crear y mantener descripciones de procesos estructuradas según ISO/IEC/IEEE 24774 | Alta — define los flujos de trabajo principales | Elicitación directa, validación de prototipos |
| **STK-02** | Analista de Procesos | Usuario primario | Revisar consistencia y completitud de las descripciones generadas | Alta — criterio de calidad del output | Revisión de outputs, feedback de validación |
| **STK-03** | Docente | Usuario secundario | Utilizar la herramienta como recurso didáctico en cursos de ingeniería | Media — requisitos de usabilidad pedagógica | Elicitación de necesidades de enseñanza |
| **STK-04** | Consultor | Usuario secundario | Modelar procesos organizacionales y entregarlos como documentos formales | Media — requisitos de exportación y portabilidad | Workshops, revisión de casos de uso |
| **STK-05** | Evaluador / Auditor | Usuario externo | Revisar documentación de procesos para auditoría o certificación | Alta — define requisitos de trazabilidad y conformidad normativa | Revisión de entregables, checklist de conformidad |
| **STK-06** | Equipo de Desarrollo | Proveedor / Interno | Implementar y mantener el sistema conforme a los requisitos definidos | Alta — factibilidad técnica y viabilidad de implementación | Autor del producto, gestión de baseline |
| **STK-07** | Usuario Final Genérico | Usuario primario | Guardar, cargar, editar e imprimir descripciones de procesos sin conocimientos técnicos de JSON | Alta — determina requisitos de usabilidad (RNF-01) | Pruebas de usabilidad, observación directa |

---

## ENTREGABLE 2: Concepto de Operaciones (ConOps)

> **Outcomes cubiertos: (b)(d)(e) — Contexto operacional, escenarios de uso y concepto de ciclo de vida.**

El Concepto de Operaciones (ConOps) describe cómo el sistema será utilizado por los stakeholders en su entorno real. Es la descripción narrativa del sistema desde la perspectiva del usuario, antes de definir la arquitectura técnica.

### 2.1 Contexto Operacional

El sistema opera como una aplicación web estática (standalone) ejecutada íntegramente en el navegador del usuario, sin requerir conexión a servidores externos ni bases de datos remotas. El entorno de despliegue es el propio equipo del usuario.

*Tabla 2.1 — Límites del sistema (Functional Boundary)*

| Dimensión | Descripción | Implicación de diseño |
| :--- | :--- | :--- |
| Entorno de ejecución | Navegadores Chrome, Edge y Firefox en escritorio | No se requiere servidor; compatibilidad cross-browser obligatoria (RNF-02) |
| Entradas | Archivos locales `.pro` (JSON) e interacción de teclado y ratón | La GUI debe abstraer completamente la estructura JSON al usuario (RNF-01) |
| Salidas | Vista web interactiva, archivos `.pro` exportados y documentos PDF | El módulo de exportación debe soportar orientación vertical y horizontal (RF-13) |
| Interfaz de usuario | Formularios, listas jerárquicas y controles de interacción visual | Usable sin formación técnica en formatos de datos estructurados |
| Almacenamiento | Sistema de archivos local del usuario mediante diálogos de descarga/carga del navegador | La portabilidad de los archivos `.pro` entre instalaciones es requisito (RNF-05) |

### 2.2 Escenarios de Uso Principales

#### Escenario A — Creación de un proceso desde cero

- El usuario inicia la aplicación en su navegador web.
- Crea una nueva descripción de proceso e ingresa: nombre, propósito y resultados esperados (RF-01, RF-02).
- Añade actividades y, dentro de cada una, añade tareas (RF-04, RF-05).
- Reorganiza la estructura mediante arrastre o controles de orden (RF-06).
- El sistema valida la completitud antes del guardado (RF-09) y muestra mensajes claros (REQ-STK-07).
- El usuario guarda el proceso como archivo `.pro` en su equipo (RF-07).

#### Escenario B — Carga y modificación de un proceso existente

- El usuario carga un archivo `.pro` previamente guardado (RF-08).
- El sistema reconstruye la estructura jerárquica completa en la interfaz (REQ-STK-10).
- El usuario modifica, elimina o reorganiza elementos existentes (RF-03, RF-05, RF-06).
- Guarda los cambios generando una nueva versión del archivo `.pro`.

#### Escenario C — Exportación e impresión

- El usuario solicita la vista previa del proceso (RF-10).
- Selecciona orientación del documento (vertical u horizontal) (RF-13).
- Genera el PDF o envía a impresión (RF-11, RF-12).

### 2.3 Concepto de Ciclo de Vida del Sistema

*Tabla 2.2 — Etapas del ciclo de vida del sistema*

| Etapa | Descripción | Stakeholders activos |
| :--- | :--- | :--- |
| Concepto | Definición de necesidades y alcance del editor de procesos | STK-01, STK-02, STK-06 |
| Desarrollo | Diseño e implementación del editor conforme a RF y RNF | STK-06 |
| Producción | Distribución del sistema como aplicación web accesible | STK-01 a STK-05, STK-07 |
| Operación | Uso continuo para creación, edición y exportación de procesos | STK-01, STK-03, STK-04, STK-07 |
| Mantenimiento | Correcciones, ampliaciones y mejoras (RNF-06) | STK-06, STK-02, STK-05 |
| Retiro | Los archivos `.pro` son portables; el usuario conserva sus datos localmente (RNF-05) | STK-07 |

---

## ENTREGABLE 3: Registro de Necesidades de Stakeholders

> **Outcome cubierto: (c) — Identificación y priorización de necesidades, expectativas, restricciones e interfaces.**

Las necesidades expresan lo que los stakeholders esperan lograr con el sistema, en lenguaje de usuario, sin dictar implementación. Están clasificadas por prioridad y vinculadas al stakeholder que las origina.

*Tabla 3.1 — Necesidades de Stakeholders con prioridad y origen*

| ID | Necesidad | Prioridad | Tipo | Stakeholder(s) origen |
| :---: | :--- | :---: | :--- | :--- |
| **N1** | Crear descripciones de procesos de forma estructurada y alineada con la norma ISO/IEC/IEEE 24774 | Alta | Funcional | STK-01, STK-02 |
| **N2** | Almacenar procesos para reutilización futura sin pérdida de información | Alta | Funcional | STK-01, STK-04, STK-07 |
| **N3** | Cargar procesos previamente creados y recuperar su estructura completa | Alta | Funcional | STK-01, STK-04, STK-07 |
| **N4** | Validar la completitud de una descripción antes de considerarla finalizada | Media | Calidad | STK-02, STK-05 |
| **N5** | Reorganizar actividades y tareas de forma ágil sin reescribir la descripción completa | Media | Funcional | STK-01, STK-04 |
| **N6** | Imprimir y exportar procesos a PDF para compartirlos o archivarlos | Alta | Funcional | STK-03, STK-04, STK-05, STK-07 |
| **N7** | Utilizar una interfaz sencilla e intuitiva sin conocimientos técnicos de formatos de datos | Alta | Usabilidad | STK-03, STK-07 |
| **N8** | Mantener relaciones coherentes entre los elementos jerárquicos del proceso | Alta | Integridad | STK-01, STK-02, STK-05 |

### 3.1 Restricciones e interfaces externas identificadas

*Tabla 3.2 — Restricciones y condicionantes del entorno*

| ID | Tipo | Descripción | Impacto en el sistema |
| :---: | :--- | :--- | :--- |
| **CONS-01** | Tecnológica | El sistema debe funcionar en los navegadores Chrome, Edge y Firefox actualizados | La implementación debe usar APIs web estándar y evitar dependencias propietarias |
| **CONS-02** | De usuario | Los usuarios no tienen formación en estructuras JSON ni formatos de datos estructurados | La GUI debe ser una barrera de abstracción total sobre el formato interno de almacenamiento |
| **CONS-03** | Normativa | Los procesos creados deben alinearse con la estructura definida por ISO/IEC/IEEE 24774 | El modelo de datos interno debe reflejar fielmente los elementos de proceso de la norma |
| **CONS-04** | De rendimiento | Las operaciones de edición deben responder en menos de 2 segundos bajo condiciones normales | Determina la arquitectura de renderizado y gestión del DOM (MOP crítica: RNF-03) |
| **CONS-05** | De portabilidad | Los archivos `.pro` deben ser legibles en cualquier instalación del sistema sin conversión | El esquema JSON del archivo `.pro` debe ser versionado y retrocompatible |

---

## ENTREGABLE 4: Especificación de Requisitos de Stakeholders (StRS)

> **Outcomes cubiertos: (b)(f) — Definición del conjunto de requisitos, análisis de inconsistencias y conflictos.**

Este entregable transforma las necesidades de la Tabla 3.1 en requisitos formales verificables. Cada requisito indica su categoría, prioridad, verificabilidad y método de verificación propuesto.

*Tabla 4.1 — Especificación de Requisitos de Stakeholders*

| ID | Enunciado del Requisito | Prioridad | Tipo | Método de verificación |
| :---: | :--- | :---: | :--- | :--- |
| **REQ-STK-01** | Permitir crear una descripción de proceso con nombre, propósito y resultados esperados | Alta | Funcional | Prueba de aceptación con casos de uso |
| **REQ-STK-02** | Permitir agregar a la descripción todos los elementos definidos por ISO/IEC/IEEE 24774 | Alta | Funcional | Verificación de conformidad normativa |
| **REQ-STK-03** | Permitir guardar la descripción en un archivo `.pro` en el sistema de archivos local | Alta | Funcional | Prueba de guardado y recuperación |
| **REQ-STK-04** | Permitir cargar y reconstruir descripciones desde archivos `.pro` | Alta | Funcional | Prueba de carga y comparación de contenido |
| **REQ-STK-05** | Permitir modificar, eliminar y reorganizar cualquier elemento de la descripción | Media | Funcional | Prueba de edición integral |
| **REQ-STK-06** | Validar que todos los elementos obligatorios estén completos antes de permitir el guardado | Media | Calidad | Prueba de validación con procesos incompletos |
| **REQ-STK-07** | Mostrar mensajes de validación claros e informativos al usuario | Media | Usabilidad | Evaluación heurística de mensajes |
| **REQ-STK-08** | Generar una vista previa del proceso formateada para impresión | Alta | Funcional | Prueba de vista previa en navegador |
| **REQ-STK-09** | Exportar la descripción a formato PDF con orientación configurable | Alta | Funcional | Prueba de exportación y validación del PDF |
| **REQ-STK-10** | Mantener y visualizar la estructura jerárquica del proceso en todo momento | Alta | Integridad | Inspección de la interfaz y prueba de consistencia |

### 4.1 Análisis de conflictos y resoluciones (Outcome f)

Durante el análisis de los requisitos de stakeholders se identificó el siguiente conflicto potencial:

*Tabla 4.2 — Registro de conflictos entre requisitos*

| ID Conflicto | Requisitos en tensión | Descripción del conflicto | Resolución adoptada |
| :---: | :---: | :--- | :--- |
| **CF-01** | REQ-STK-07 vs. REQ-STK-03 | REQ-STK-07 exige que el usuario no necesite conocer JSON, pero REQ-STK-03 almacena los datos en un archivo `.pro` basado en JSON. Existe la posibilidad de que el usuario quiera ver o editar el archivo manualmente. | La GUI actúa como barrera de abstracción total. El archivo `.pro` es un artefacto interno que el usuario gestiona como archivo opaco. La interfaz nunca expone la estructura JSON directamente. Resuelto como RNF-01. |

---

## ENTREGABLE 5: Matriz de Trazabilidad Necesidades → Requisitos

> **Outcome cubierto: (g) — Trazabilidad bidireccional entre necesidades y requisitos de stakeholders.**

La trazabilidad bidireccional garantiza que cada necesidad de stakeholder queda cubierta por al menos un requisito, y que cada requisito puede justificarse en al menos una necesidad. Esto es condición de conformidad con la cláusula 6.4.2.

*Tabla 5.1 — Trazabilidad N → REQ-STK (Directa)*

| ID Need | Enunciado de la Necesidad | Requisito(s) STK asignados | Estado de cobertura |
| :---: | :--- | :---: | :---: |
| **N1** | Crear descripciones de procesos de forma estructurada | REQ-STK-01, REQ-STK-02 | ✅ Cubierta |
| **N2** | Almacenar procesos para reutilización futura | REQ-STK-03 | ✅ Cubierta |
| **N3** | Cargar procesos previamente creados | REQ-STK-04 | ✅ Cubierta |
| **N4** | Validar la completitud de una descripción | REQ-STK-06, REQ-STK-07 | ✅ Cubierta |
| **N5** | Reorganizar actividades y tareas de forma ágil | REQ-STK-05 | ✅ Cubierta |
| **N6** | Imprimir y exportar procesos a PDF | REQ-STK-08, REQ-STK-09 | ✅ Cubierta |
| **N7** | Interfaz sencilla e intuitiva sin conocimientos técnicos | REQ-STK-07 | ✅ Cubierta |
| **N8** | Mantener relaciones coherentes entre elementos del proceso | REQ-STK-10 | ✅ Cubierta |

*Tabla 5.2 — Trazabilidad REQ-STK → N (Inversa — verificación de justificación)*

| REQ-STK | Enunciado del Requisito | Necesidad(es) origen | Justificación |
| :---: | :--- | :---: | :---: |
| **REQ-STK-01** | Crear descripción con nombre, propósito y resultados esperados | N1 | ✅ Justificado |
| **REQ-STK-02** | Agregar elementos definidos por ISO/IEC/IEEE 24774 | N1 | ✅ Justificado |
| **REQ-STK-03** | Guardar descripción en archivo `.pro` | N2 | ✅ Justificado |
| **REQ-STK-04** | Cargar archivos `.pro` | N3 | ✅ Justificado |
| **REQ-STK-05** | Modificar, eliminar y reorganizar elementos | N5 | ✅ Justificado |
| **REQ-STK-06** | Validar elementos obligatorios antes del guardado | N4 | ✅ Justificado |
| **REQ-STK-07** | Mostrar mensajes claros de validación | N4, N7 | ✅ Justificado |
| **REQ-STK-08** | Generar vista previa para impresión | N6 | ✅ Justificado |
| **REQ-STK-09** | Exportar a PDF | N6 | ✅ Justificado |
| **REQ-STK-10** | Mantener estructura jerárquica del proceso | N8 | ✅ Justificado |

> **Nota:** Todos los requisitos (REQ-STK-01 a REQ-STK-10) están justificados por al menos una necesidad. Todas las necesidades (N1–N8) están cubiertas por al menos un requisito. La trazabilidad es completa y sin huecos.

---

## ENTREGABLE 6: Registro de Aprobación y Establecimiento de Baseline

> **Outcome cubierto: (h) — Aprobación de requisitos y establecimiento de la línea base.**

Conforme a la metodología Cascada adoptada, este documento de requisitos es objeto de un acuerdo de congelamiento (baseline). Una vez firmado, cualquier cambio deberá tramitarse mediante el proceso de gestión de cambios formalmente definido.

### 6.1 Declaración de completitud del proceso 6.4.2

*Tabla 6.1 — Checklist de outcomes del proceso 6.4.2*

| Outcome | Descripción (ISO/IEC/IEEE 12207:2017 — 6.4.2.2) | Entregable | Estado |
| :---: | :--- | :---: | :---: |
| **(a)** | Stakeholders identificados a lo largo del ciclo de vida | Entregable 1 | ✅ |
| **(b)** | Requisitos de stakeholders definidos respecto al contexto operacional y restricciones | Entregables 3 y 4 | ✅ |
| **(c)** | Necesidades, expectativas, restricciones e interfaces identificadas y priorizadas | Entregable 3 | ✅ |
| **(d)** | ConOps y escenarios de uso definidos | Entregable 2 | ✅ |
| **(e)** | Concepto de ciclo de vida del sistema definido | Entregable 2 | ✅ |
| **(f)** | Requisitos analizados para detectar inconsistencias, omisiones y conflictos | Entregable 4 | ✅ |
| **(g)** | Trazabilidad entre requisitos y necesidades de stakeholders establecida | Entregable 5 | ✅ |
| **(h)** | Requisitos de stakeholders aprobados y línea base establecida | Entregable 6 | ✅ |

### 6.2 Firmas de Aprobación

Los abajo firmantes declaran haber revisado el contenido de este documento, estar de acuerdo con los requisitos de stakeholders documentados y autorizar el establecimiento de la versión 1.0 como Baseline oficial del proyecto.

| Rol | Nombre | Fecha | Firma |
| :--- | :--- | :---: | :---: |
| Responsable del Proyecto | | | |
| Diseñador de Procesos (STK-01) | | | |
| Analista de Procesos (STK-02) | | | |
| Evaluador / Auditor (STK-05) | | | |

---

*— Fin del documento de Entregables del Proceso 6.4.2 —*

*Confidencial — Uso Interno · Versión 1.0 Baseline*

