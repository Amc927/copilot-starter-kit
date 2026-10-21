# 🤖 AI Engineering Team Starter Kit

> Una organización de ingeniería de software gobernada por IA para GitHub Copilot.
> A governed AI software-engineering organization for GitHub Copilot.

![GitHub Copilot](https://img.shields.io/badge/GitHub%20Copilot-Engineering%20Team-8957E5?logo=githubcopilot&logoColor=white)
![Repository First](https://img.shields.io/badge/Approach-Repository%20First-0969DA)
![Governance](https://img.shields.io/badge/Governance-Evidence%20Based-1F883D)
![Quality Gates](https://img.shields.io/badge/Quality%20Gates-11%20Canonical-D1242F)
![Lifecycle](https://img.shields.io/badge/Lifecycle-Aware-FB8C00)

---

## 🌍 Idioma | Language

- [🇪🇸 Documentación en español](#-documentación-en-español)
- [🇬🇧 English documentation](#-english-documentation)

---

# 🇪🇸 Documentación en español

## 👋 ¿Qué es este Starter Kit?

**AI Engineering Team Starter Kit** convierte GitHub Copilot en un equipo coordinado de especialistas de ingeniería de software.

En lugar de utilizar un único asistente genérico para todo, organiza el trabajo mediante:

- 🧭 **Orchestrator**, que coordina la petición y produce la decisión final.
- 🏗️ **Solution Architect**, para decisiones de arquitectura material.
- ⚙️ **Backend Engineer**, para servicios, APIs, datos e integraciones.
- 🖥️ **Frontend Systems Engineer**, para interfaces y experiencia de usuario.
- 🔐 **Security Engineer**, para seguridad, identidad, permisos y datos sensibles.
- 🧪 **QA Engineer**, para criterios de aceptación y pruebas.
- 🔎 **Code Reviewer**, para calidad de implementación.
- 🚀 **DevOps Engineer**, para construcción, configuración y despliegue.
- 📈 **Performance Engineer**, para rendimiento, carga y capacidad.
- 📚 **Documentation Engineer**, para documentación materialmente necesaria.

También incluye skills de Python, Java, Angular, MCP, LLM y sistemas agentic; workflows; checklists; Quality Gates; governance y trazabilidad.

## 🎯 ¿Para qué sirve?

Puede ayudarte a:

- 🔍 Entender una aplicación existente.
- 🏗️ Diseñar una solución nueva.
- 🎯 Analizar una funcionalidad antes de desarrollarla.
- 🐛 Investigar errores sin modificar código prematuramente.
- 🔐 Revisar seguridad y permisos.
- ✅ Preparar una estrategia de pruebas.
- 🧠 Diseñar funciones con LLM o RAG.
- 🤖 Diseñar sistemas agentic con herramientas controladas.
- 🚀 Evaluar preparación para release.

El Starter Kit intenta impedir que Copilot invente tecnologías, requisitos, estándares corporativos, tests ejecutados, participación de especialistas, aprobaciones o resultados de Quality Gates.

## 🙋 ¿Necesito saber programar?

**No necesitas saber programar para empezar.**

La ruta más sencilla es:

1. Abrir la carpeta en Visual Studio Code.
2. Abrir GitHub Copilot Chat.
3. Crear un chat nuevo.
4. Seleccionar `Orchestrator`.
5. Explicar lo que quieres conseguir.
6. Leer el análisis, la información pendiente y la decisión final.

Para implementar, ejecutar o desplegar cambios reales seguirá siendo necesario disponer de los accesos y conocimientos autorizados para el proyecto.

---

# 🚀 Inicio rápido paso a paso

## 1️⃣ Requisitos

- [Visual Studio Code](https://code.visualstudio.com/)
- Extensión GitHub Copilot
- Acceso a GitHub Copilot Chat
- Una copia del Starter Kit
- Opcionalmente, la aplicación que quieres analizar

## 2️⃣ Descargar el repositorio

### Opción sencilla

1. Abre el repositorio en GitHub.
2. Pulsa **Code**.
3. Selecciona **Download ZIP**.
4. Descomprime el fichero.
5. Abre la carpeta resultante en Visual Studio Code.

### Opción con Git

```bash
git clone https://github.com/Amc927/copilot-starter-kit.git
cd copilot-starter-kit
```

## 3️⃣ Comprobar la estructura

Deberías ver al menos:

```text
.github/
PROJECT_BRIEF.md
README.md
```

La carpeta `.github` contiene los agentes, skills, workflows, checklists y reglas de governance.

## 4️⃣ Abrir Copilot Chat

1. Abre GitHub Copilot Chat.
2. Crea un chat nuevo.
3. Selecciona explícitamente `Orchestrator`.

> ⚠️ Un chat genérico puede no utilizar todas las reglas del Starter Kit.

## 5️⃣ Primera prueba

Copia y pega:

```text
Quiero comprobar que el Starter Kit está disponible.

Analiza el workspace actual y determina:
- qué repositorios o aplicaciones están disponibles;
- qué tecnologías puedes verificar;
- qué información no está disponible;
- qué especialistas serían necesarios;
- qué Quality Gates podrían ser aplicables.

No implementes ni modifiques nada.
No inventes información que no puedas verificar.
```

## 6️⃣ Cómo leer la respuesta

- **Resumen:** qué se está analizando.
- **Clasificación:** tipo de cambio, lifecycle, impacto y riesgo.
- **Arquitectura y tecnología:** evidencia encontrada.
- **Skills:** conocimientos técnicos aplicables.
- **Especialistas:** perfiles propuestos, no necesariamente ejecutados.
- **Quality Gates:** validaciones formales aplicables.
- **Riesgos:** problemas potenciales.
- **Información pendiente:** datos necesarios para continuar.
- **Decisión final:** `APPROVE`, `CONDITIONAL APPROVAL`, `BLOCK` o `NEEDS MORE INFO`.

## 7️⃣ Si aparece `NEEDS MORE INFO`

No es un fallo. Significa que falta información esencial.

Ejemplo:

```text
La entrada será un Excel con una hoja llamada Facturas.
Las columnas obligatorias son Identificador, Cliente, Importe y Estado.
Todavía no se ha decidido el formato de salida.

Actualiza el análisis sin implementar cambios.
```

## 8️⃣ Analizar una aplicación concreta

Puedes mantener el Starter Kit y una aplicación en el mismo workspace:

```text
workspace/
├── .github/
├── PROJECT_BRIEF.md
├── README.md
└── mi-aplicacion/
```

Prompt recomendado:

```text
Analiza la aplicación ubicada en la carpeta mi-aplicacion.

Determina:
- tecnologías verificadas;
- arquitectura y componentes principales;
- frontend, backend, datos e integraciones;
- autenticación y autorización;
- tests y despliegue;
- riesgos y deuda técnica;
- especialistas y Quality Gates aplicables.

Utiliza únicamente evidencia del repositorio.
No implementes ni modifiques nada.
```

Si existen varias aplicaciones, indica expresamente cuál es la aplicación objetivo.

---

# 📝 Guías de uso y ejemplos copiables

## 🔍 Entender una aplicación desconocida

```text
Analiza la aplicación disponible en este workspace.

Quiero entenderla antes de realizar cambios.
Distingue evidencia verificada, información declarada, suposiciones e información no disponible.

Explica tecnologías, arquitectura, frontend, backend, datos, integraciones, seguridad, tests, despliegue, riesgos y deuda técnica.

No implementes ni modifiques nada.
```

## 🎯 Analizar una funcionalidad

```text
Necesito añadir esta funcionalidad:

[DESCRIBE LA FUNCIONALIDAD]

Antes de implementar:
1. Revisa el repositorio.
2. Identifica componentes afectados.
3. Determina si existe una decisión de arquitectura material.
4. Selecciona solo los especialistas necesarios.
5. Identifica skills, riesgos, pruebas y Quality Gates.
6. Enumera la información pendiente.
7. Produce una decisión final.

Conserva la tecnología existente salvo justificación material.
```

## 🐛 Investigar un error

```text
Existe este problema:

[DESCRIBE EL ERROR]

Determina si puede reproducirse, la causa probable, la evidencia necesaria para confirmar la causa raíz, los componentes afectados, las pruebas de regresión y los Quality Gates aplicables.

No confundas causa probable con causa raíz confirmada.
No implementes todavía.
```

## 📊 Procesar Excel o datos

```text
Necesito recibir un Excel, validar estructura y reglas de negocio, mostrar errores y generar un fichero de salida.

Analiza el repositorio y determina:
- componentes reutilizables;
- tecnología existente;
- riesgos del procesamiento;
- integridad y sensibilidad de datos;
- casos de prueba;
- especialistas y Quality Gates.

No introduzcas librerías nuevas si ya existe una solución adecuada.
```

## 🐍 Aplicación Python

```text
Analiza esta aplicación Python mediante evidencia del repositorio.
Identifica versión, dependencias, frameworks, estructura, APIs, datos, tests, integraciones, seguridad y despliegue.

Aplica Python Engineering Skill solo donde Python esté establecido.
No introduzcas FastAPI, SQLAlchemy, pytest, Poetry o uv por preferencia.
```

## ☕ Aplicación Java

```text
Analiza la aplicación Java.
Determina versión, build, framework, capas, configuración, APIs, persistencia, errores, tests, seguridad, integración y despliegue.

Aplica Java Engineering Skill.
No asumas Spring Boot, Maven, Gradle, REST, OpenAPI, JPA o Hibernate sin evidencia.
```

## 🅰️ Aplicación Angular

```text
Analiza el frontend Angular.
Determina versión, Node.js, estructura, routing, componentes, formularios, servicios, HTTP, estado, guards, interceptores, tests, accesibilidad y librerías corporativas.

Aplica Endesa Corporate Angular Engineering Skill.
No inventes paquetes, componentes, temas, APIs o design tokens corporativos.
```

## 🖥️ Aplicación Streamlit

```text
Analiza la aplicación Streamlit.
Explica interfaz, lógica de negocio, estado, integraciones, autenticación, validación, seguridad y tests.

Conserva Streamlit si está establecido y satisface los requisitos.
No asumas que Streamlit implica PoC, UI desechable o futura migración a Angular.
```

## 🧪 Diseñar una PoC

```text
Necesito una PoC para validar:

[OBJETIVO]

Determina hipótesis, alcance mínimo, tecnología reutilizable, especialistas necesarios, riesgos, pruebas mínimas, información pendiente y Quality Gates.

No impongas toda la profundidad de producción.
No elimines controles críticos de seguridad o integridad.
No inventes un destino de producción.
```

## 🧠 Funcionalidad LLM

```text
Necesito evaluar esta funcionalidad LLM:

[DESCRIPCIÓN]

Determina si el LLM está justificado, alternativa determinista, datos, límites de confianza, seguridad, evaluación, especialistas, skills y Quality Gates.

No selecciones proveedor, modelo o framework sin evidencia.
No inventes datasets, porcentajes, repeticiones, latencias, costes o thresholds.
No asumas que LLM implica Agentic.
```

## 📚 RAG interno

```text
Necesito responder preguntas sobre documentación interna autorizada.

La solución debe respetar permisos, basarse en documentos recuperados, mostrar fuentes y abstenerse sin evidencia.

Analiza autorización, retrieval, grounding, citas, contenido no confiable, prompt injection indirecta, evaluación y Quality Gates.

No selecciones proveedor, embeddings, vector database, framework, chunk size, overlap o top-k sin evidencia.
No introduzcas Agentic si el flujo solo recupera y responde.
```

## 🤖 Sistema agentic con herramientas

```text
Necesito un asistente que seleccione dinámicamente herramientas autorizadas.

Analiza si Agentic está justificado, alternativas deterministas, herramientas, permisos, acciones prohibidas, autenticación, autorización, validación, prompt injection, bucles, condiciones de parada, aprobación humana, evaluación, skills y Quality Gates.

Usa el diseño menos autónomo posible.
No introduzcas múltiples agentes ni MCP sin necesidad material.
La seguridad no puede depender solo del prompt.
```

## 🔐 Revisión de seguridad

```text
Analiza la seguridad de este cambio:

[DESCRIPCIÓN]

Identifica activos, datos sensibles, trust boundaries, autenticación, autorización, permisos, secretos, entradas no confiables, fugas, integraciones, controles, evidencia faltante y Security Gate.

No inventes controles corporativos, ejecución de herramientas o aceptación formal del riesgo.
```

## ✅ Estrategia QA

```text
Define la validación del cambio:

[DESCRIPCIÓN]

Incluye criterios de aceptación, camino principal, casos límite, negativos, regresión, tests unitarios, integración, contrato, end-to-end y evaluaciones LLM/Agentic cuando apliquen.

Distingue TEST DEFINED, TEST EXECUTED, PASS, FAIL, NOT EXECUTED, NOT AVAILABLE y NOT APPLICABLE.
No inventes cobertura o thresholds.
```

---

# 🧠 Tecnologías y capacidades explicadas de forma sencilla

## 🐍 Python

Lenguaje utilizado para datos, automatización, backend, APIs, IA y aplicaciones internas.

```text
Python establecido
→ Python Engineering Skill
```

Python no implica automáticamente Streamlit, FastAPI, pandas, SQLAlchemy, pytest, Poetry, uv o MCP.

## ☕ Java

Lenguaje habitual en servicios y aplicaciones empresariales.

```text
Java establecido
→ Java Engineering Skill
```

Java no implica automáticamente Spring Boot, Maven, Gradle, REST, OpenAPI, JPA o Hibernate.

## 🅰️ Angular

Tecnología para interfaces web con componentes, rutas, formularios y servicios.

```text
Angular establecido
→ Endesa Corporate Angular Engineering Skill
```

Las librerías y componentes corporativos deben verificarse. Si faltan:

```text
Corporate information not available - validation required.
```

## 🖥️ Streamlit

Tecnología Python para interfaces de datos y aplicaciones internas.

```text
STREAMLIT != PROTOTYPE
STREAMLIT != DISPOSABLE UI
```

## 🔌 API

Contrato para intercambiar información entre sistemas. API no significa REST automáticamente.

## 🗄️ Base de datos

Almacena información persistente. No se debe introducir una nueva base de datos, cache, cola o vector database sin necesidad material.

## 🧠 LLM

Modelo de lenguaje para clasificación, extracción, resumen o generación.

```text
LLM != Agentic
```

## 📚 RAG

Busca información autorizada antes de generar una respuesta.

```text
Usuario → permisos → retrieval autorizado → LLM → respuesta + fuentes
```

RAG no significa Agentic.

## 🤖 Agentic

Comportamiento dinámico como selección de herramientas, planificación, delegación o ejecución iterativa.

```text
Agentic != Multi-agent obligatorio
Agentic != MCP obligatorio
```

## 🔌 MCP

Protocolo para exponer tools y resources a clientes de IA. No es obligatorio por utilizar IA o Agentic.

## 🔐 Autenticación y autorización

```text
Autenticación → ¿Quién eres?
Autorización  → ¿Qué puedes hacer?
```

Los permisos deben comprobarse fuera del LLM y también en el sistema destino.

## 🛡️ Prompt Injection

Intento directo o indirecto de alterar el comportamiento del modelo. Documentos y salidas de tools deben tratarse como contenido no confiable.

## 🔎 Grounding

Relaciona una respuesta con evidencia. Sin evidencia suficiente, el sistema debe abstenerse.

---

# 🚦 Quality Gates y decisiones

Los once Quality Gates canónicos son:

```text
Architecture Gate
Backend Gate
Frontend Gate
Security Gate
QA Gate
Code Review Gate
DevOps Gate
Performance Gate
Documentation Gate
LLM Gate
Agentic Gate
```

## Aplicabilidad

```text
APPLICABLE
NOT APPLICABLE
NOT DETERMINED
```

## Resultado

```text
PASSED
CONDITIONAL
FAILED
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Reglas esenciales:

```text
NOT EXECUTED != PASSED
NOT AVAILABLE != PASSED
NOT APPLICABLE != PASSED
```

Human Approval es governance, no un Quality Gate. Formal Risk Acceptance pertenece a la autoridad autorizada.

---

# 🛠️ Guía avanzada y referencia técnica

## 🗂️ Estructura

```text
copilot-starter-kit/
├── .github/
│   ├── agents/
│   ├── checklists/
│   ├── governance/
│   ├── observability/
│   ├── prompts/
│   ├── skills/
│   └── workflows/
├── .gitignore
├── PROJECT_BRIEF.md
└── README.md
```

## 🎯 Routing mínimo

```text
Cambio → dominios → lifecycle + riesgo + evidencia → autoridad → especialistas mínimos → gates
```

```text
Candidate Agent != Participating Agent
```

## 🏗️ Architecture Routing

Solution Architect participa ante decisiones materiales: nueva arquitectura, tecnología, migración, datastore, boundaries, integración, despliegue, MCP, LLM/Agentic material o transición real a producción.

```text
REPOSITORY AMBIGUITY
→ EVIDENCE FIRST
→ ARCHITECTURE ONLY IF MATERIAL DECISION REMAINS
```

## ✅ Checklist frente a gate

```text
Architecture Review Checklist → Architecture Gate
Backend Technical Review Checklist → Backend Gate
Frontend Technical Review Checklist → Frontend Gate
Security Review Checklist → Security Gate
QA Validation Checklist → QA Gate
```

```text
Checklist executed != Quality Gate passed
```

## 🚀 Release

```text
Specialist Quality Gates → Release Checklist → Release Gate → Release decision
```

Release Gate no es un duodécimo gate especialista.

## ⚖️ Autoridad por dominio

- Arquitectura → Solution Architect
- Backend → Backend Engineer
- Frontend → Frontend Systems Engineer
- Seguridad → Security Engineer
- Calidad funcional → QA Engineer
- Calidad de implementación → Code Reviewer
- Operaciones → DevOps Engineer
- Rendimiento → Performance Engineer
- Documentación → Documentation Engineer
- Decisión final → Orchestrator
- Aceptación formal de riesgo → autoridad de governance autorizada

No existe una jerarquía universal entre especialistas.

## 🔒 Valores numéricos

No inventar tamaños de dataset, repeticiones, porcentajes, límites, retries, timeouts, costes o latencias. Deben proceder de requisitos, configuración, baselines o governance verificados.

## 🧪 Smoke tests recomendados

1. Python + Streamlit PoC
2. Java + Angular Production
3. Quality Gates canónicos
4. RAG no Agentic
5. Agentic read-only

## ✅ Validación local

```bash
git status
git diff --check
git diff --cached --check
git diff --name-only --diff-filter=U
find .github -type f -empty -print
grep -RniE '^(<<<<<<<|=======|>>>>>>>)' .github PROJECT_BRIEF.md README.md
```

## 🔧 Extender el Starter Kit

- Añade una **Skill** para conocimiento técnico reutilizable.
- Añade un **Agent** solo para un nuevo dominio de responsabilidad y autoridad.
- Añade un **Workflow** para procesos repetibles con varias fases.
- Añade una **Checklist** para validaciones repetibles.
- Modifica **Governance** solo cuando cambien autoridad, gates, bloqueos, aprobación, riesgo o trazabilidad.

## ⚠️ Limitaciones conocidas

El routing puede ser conservador en Code Review, Documentation o Architecture. Es aceptable si no inventa participación, resultados, tecnología, arquitectura, aprobación o producción readiness.

---

# 🇬🇧 English documentation

## 👋 What is this Starter Kit?

**AI Engineering Team Starter Kit** turns GitHub Copilot into a coordinated software-engineering organization.

It provides:

- 🧭 An Orchestrator
- 🏗️ Architecture guidance
- ⚙️ Backend engineering
- 🖥️ Frontend engineering
- 🔐 Security analysis
- 🧪 QA and evaluation
- 🔎 Code review
- 🚀 DevOps
- 📈 Performance engineering
- 📚 Documentation engineering
- 🧠 Python, Java, Angular, MCP, LLM and Agentic skills
- 🔁 Workflows
- ✅ Checklists
- 🚦 Canonical Quality Gates
- ⚖️ Governance and traceability

## 🎯 What can it do?

- Analyze existing repositories
- Design new solutions
- Plan features and bug fixes
- Review security
- Prepare validation strategies
- Design LLM, RAG and Agentic capabilities
- Evaluate release readiness

## 🙋 Do I need programming experience?

No programming experience is required to start.

1. Open the folder in Visual Studio Code.
2. Open GitHub Copilot Chat.
3. Start a new chat.
4. Select `Orchestrator`.
5. Describe the goal in normal language.
6. Review the evidence, missing information, gates and final decision.

## 🚀 Quick start

```text
Analyze the current workspace.

Determine:
- available applications and repositories;
- verified technologies;
- unavailable information;
- required specialists;
- potentially applicable Quality Gates.

Do not implement or modify anything.
Do not invent unavailable evidence.
```

## 🔍 Analyze an existing application

```text
Analyze the application in the target-application folder.

Explain verified technologies, architecture, frontend, backend, data, integrations, identity, tests, deployment, risks and technical debt.

Separate verified evidence, user-provided information, assumptions and unavailable information.
Do not implement changes.
```

## 🎯 Analyze a feature

```text
I need this feature:

[DESCRIBE THE FEATURE]

Before implementation:
- inspect the repository;
- identify affected components;
- determine whether architecture is materially affected;
- select the minimum required specialists;
- identify skills, risks, tests and Quality Gates;
- list missing information;
- produce a final decision.
```

## 🐛 Analyze a bug

```text
The following problem exists:

[DESCRIBE THE BUG]

Determine reproduction evidence, probable cause, evidence required for confirmed root cause, affected components, regression tests and applicable Quality Gates.
Do not confuse probable cause with confirmed root cause.
```

## 🧠 LLM and RAG

```text
LLM != Agentic
RAG != Agentic
```

A RAG system should apply authorization before restricted content reaches the model, treat retrieved content as untrusted, validate citations and abstain when evidence is insufficient.

## 🤖 Agentic systems

Agentic behaviour includes dynamic tool selection, planning, delegation or iterative execution.

```text
Agentic != Multi-agent required
Agentic != MCP required
```

Use the least autonomous design that satisfies the requirement. Security must be enforced in deterministic code and target systems, not only in prompts.

## 🧠 Skill routing

```text
Python established → Python Engineering Skill
Java established → Java Engineering Skill
Angular established → Endesa Corporate Angular Engineering Skill
Material LLM functionality → LLM Engineering Skill
Material agentic behaviour → Agentic Systems Engineering Skill
Python + justified MCP → Python Engineering Skill + Python MCP Engineering Skill
```

Skill availability does not select technology.

## 🚦 Canonical Quality Gates

```text
Architecture Gate
Backend Gate
Frontend Gate
Security Gate
QA Gate
Code Review Gate
DevOps Gate
Performance Gate
Documentation Gate
LLM Gate
Agentic Gate
```

Applicability:

```text
APPLICABLE
NOT APPLICABLE
NOT DETERMINED
```

Results:

```text
PASSED
CONDITIONAL
FAILED
NOT EXECUTED
NOT AVAILABLE
NOT APPLICABLE
```

Mandatory distinctions:

```text
NOT EXECUTED != PASSED
NOT AVAILABLE != PASSED
NOT APPLICABLE != PASSED
AGENT DEFINED != AGENT PARTICIPATED
CHECKLIST EXECUTED != QUALITY GATE PASSED
```

Human approval is governance evidence, not a Quality Gate. Formal risk acceptance belongs to authorized governance.

## 🧭 Final decisions

```text
APPROVE
CONDITIONAL APPROVAL
BLOCK
NEEDS MORE INFO
```

`NEEDS MORE INFO` protects the organization from fabricated decisions when critical evidence is missing.

## 🗂️ Repository structure

```text
.github/agents/         Specialist agents and Orchestrator
.github/skills/         Reusable engineering guidance
.github/workflows/      Feature, bugfix and security workflows
.github/checklists/     Validation artifacts
.github/governance/     Authority and canonical gates
.github/prompts/        Reusable analysis frameworks
.github/observability/  Decision and traceability templates
PROJECT_BRIEF.md        Mission and operating model
README.md               User and maintainer documentation
```

## 🛠️ Maintenance principles

- Repository first
- Evidence before assertion
- Minimum necessary agent routing
- Preserve established technology
- Use closed canonical Quality Gate vocabulary
- Separate checklists from gates
- Separate LLM from Agentic
- Separate Agentic from Multi-agent
- Do not introduce MCP automatically
- Do not fabricate tests, execution, thresholds, approvals or formal risk acceptance

## 🧪 Recommended regression tests

1. Python + Streamlit PoC
2. Java + Angular Production
3. Canonical Quality Gate test
4. Non-agentic RAG
5. Read-only Agentic tool selection

## ✅ Local validation

```bash
git status
git diff --check
git diff --cached --check
git diff --name-only --diff-filter=U
find .github -type f -empty -print
grep -RniE '^(<<<<<<<|=======|>>>>>>>)' .github PROJECT_BRIEF.md README.md
```

---

# 📌 Project status

Current capabilities include:

- Repository-first orchestration
- Lifecycle-aware routing
- Python, Java and Angular engineering
- Streamlit support
- Python MCP engineering
- LLM and RAG engineering
- Agentic-systems engineering
- Adaptive feature, bugfix and security workflows
- Eleven canonical specialist Quality Gates
- Human-governance separation
- Decision logging and traceability

See `PROJECT_BRIEF.md` for the complete mission, authority model, execution model and Definition of Done.

---

# 📄 License and authorized use

Add or update the repository license according to the intended distribution and organizational policy.

Before sharing outside the authorized environment, review:

- Corporate references
- Internal governance
- Security requirements
- Endesa-specific Angular guidance
- Repository and documentation visibility
