<div align="center">

<img src="https://img.shields.io/badge/Microsoft%20Innovation%20Challenge-2026-0078D4?style=for-the-badge" />
<img src="https://img.shields.io/badge/Project-Lab%20Notebook%20AI%20Assistant-0A66C2?style=for-the-badge" />
<img src="https://img.shields.io/badge/Focus-Agentic%20AI%20%7C%20Safety%20%7C%20Explainability-111827?style=for-the-badge" />
<img src="https://img.shields.io/badge/Stack-React%2019%20%2B%20NestJS%20%2B%20MySQL-2563EB?style=for-the-badge" />
<img src="https://img.shields.io/badge/Azure%20OpenAI-Enabled-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20AI%20Foundry-Enabled-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Vision-Enabled-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Speech-Enabled-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Document%20Intelligence-Enabled-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Blob%20Storage-Enabled-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />

# Sapient Lab

### Lab Notebook AI Assistant

Plataforma para asistir a investigadores en el razonamiento experimental con agentes de IA,
sin reemplazar el juicio cientifico humano.

</div>

---

## Judge Quick Access

<div align="center">

[![Slides](https://img.shields.io/badge/Slides-Canva-00C4CC?style=for-the-badge&logo=canva&logoColor=white)](https://www.canva.com/design/DAHEuqnjrpc/6jHkQVtlXaC9SG2pfgArTg/edit?utm_content=DAHEuqnjrpc&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
[![Frontend](https://img.shields.io/badge/Frontend-React%20%2B%20Vite-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://github.com/Sapient-Lab/Frontend)
[![Backend](https://img.shields.io/badge/Backend-NestJS%20%2B%20OpenML-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)](https://github.com/Sapient-Lab/back_end)

</div>

---

## Project Description

Sapient Lab es un asistente de cuaderno de laboratorio basado en agentes que ayuda a equipos de investigacion a interpretar protocolos,
analizar resultados experimentales y proponer siguientes pasos explicados, manteniendo seguridad estricta y control humano en la decision final.

El sistema integra analisis multimodal (texto, CSV, imagen y voz), evidencia externa con OpenML y una arquitectura de IA responsable
orientada a transparencia, trazabilidad y limites de uso en escenarios sensibles.

---

## Challenge Statement

Los investigadores quieren ayuda para razonar sobre experimentos sin reemplazar el juicio cientifico.
El sistema debe interpretar protocolos, sugerir variaciones para siguientes pasos,
analizar resultados desde texto, CSV o imagenes y explicar claramente por que recomienda cada accion.

La solucion debe aplicar limites de seguridad estrictos en dominios biologicos/clinicos,
filtrado de contenido y control de asesoramiento no permitido.

---

## What We Built

**Sapient Lab** integra una experiencia de cuaderno cientifico asistido por agentes con:

- interpretacion de protocolos experimentales,
- analisis multimodal (texto, CSV, imagen, voz),
- recomendaciones explicadas para siguientes pasos,
- controles de seguridad y filtrado,
- soporte de evidencia externa con OpenML.

---

## Architecture Overview

```mermaid
flowchart LR
	R[Research Team] --> FE[Frontend: React + Vite]
	FE -->|/api| BE[Backend: NestJS]

	BE --> AO[Agent Orchestrator]
	AO --> PI[Protocol Interpreter]
	AO --> MA[Multimodal Analyzer]
	AO --> RV[Variation Recommender]
	AO --> SG[Safety Guardrails]
	AO --> EX[Explainability Composer]
	AO --> OM[OpenML Connector]

	OM --> OAPI[(OpenML API)]
	BE --> DB[(MySQL)]
	BE --> BLOB[(Azure Blob)]
```

---

## AI Agent Interaction (Judge View)

```mermaid
sequenceDiagram
	participant User as Researcher
	participant UI as Frontend Notebook
	participant API as Backend Orchestrator
	participant PI as Protocol Agent
	participant MM as Multimodal Agent
	participant OM as OpenML Agent
	participant SG as Safety Agent
	participant EX as Explainability Agent

	User->>UI: Experimental question
	UI->>API: POST /api/ai/notebook/chat
	API->>PI: Interpret protocol context
	API->>MM: Analyze text/CSV/image
	API->>OM: Retrieve benchmark evidence
	PI-->>API: Protocol reasoning
	MM-->>API: Data findings
	OM-->>API: Comparable OpenML metadata
	API->>SG: Enforce safety and policy filters
	SG-->>API: Allowed response constraints
	API->>EX: Build justified recommendation
	EX-->>UI: Clear rationale + next steps
	UI-->>User: Human-in-the-loop decision support
```

---

## Technology Stack

| Layer | Technologies |
|---|---|
| Frontend | React 19, TypeScript, Vite, React Router, Framer Motion |
| Backend | NestJS, Node.js, TypeScript, class-validator |
| Data | MySQL, project context documents, experiment notes |
| AI Services | Azure OpenAI/Foundry, Azure Vision, Azure Speech, Azure Document Intelligence |
| External Benchmark | OpenML (`/api/openml/*`) |
| Storage | Azure Blob Storage |

## Azure Services In Use

<div align="center">

<img src="https://img.shields.io/badge/Azure%20OpenAI-LLM%20Reasoning-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20AI%20Foundry-Agent%20Orchestration-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Vision-Image%20Analysis-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Speech-Speech%20to%20Text-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Document%20Intelligence-Document%20Parsing-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Blob%20Storage-File%20Storage-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />

</div>

---

## Project Repositories (For Judges)

- Frontend: https://github.com/Sapient-Lab/Frontend
- Backend: https://github.com/Sapient-Lab/back_end
- API and technical docs (workspace reference): [back_end/data/Document](../../back_end/data/Document)

---

## Judge Evaluation Matrix (Semana del 30 de marzo de 2026)

| Criterio | Ponderacion | Como lo cumple Sapient Lab |
|---|---:|---|
| Rendimiento | 25% | Arquitectura frontend/backend separada con APIs dedicadas para chat, analisis y notebook; flujo de insercion limpia reduce ruido y acelera trabajo de laboratorio; soporte de contexto por proyecto para respuestas mas relevantes. |
| Innovacion | 25% | Asistente de notebook cientifico con arquitectura multiagente, razonamiento explicable, analisis multimodal y enriquecimiento con OpenML para evidencia comparativa en recomendaciones. |
| Amplitud de los servicios de Azure utilizados | 25% | Uso combinado de Azure OpenAI, Azure AI Foundry, Azure Vision, Azure Speech, Azure Document Intelligence y Azure Blob Storage en un flujo unico orientado a investigacion. |
| IA responsable | 25% | Guardrails y filtrado para contenido sensible, limites para evitar asesoramiento no permitido, explicaciones transparentes y enfoque human-in-the-loop para no reemplazar el juicio cientifico. |

### Evidencia tecnica para jueces

- Agentes IA y notebook: endpoints `/api/ai/*` en backend.
- Seguridad: modulo safety (`/api/safety/analyze`) y politicas de filtrado.
- OpenML: endpoints `/api/openml/*` para datasets, tareas, runs y evaluaciones.
- Frontend de evaluacion: flujo `/app/lab`, `/app/protocolos`, `/app/docs`, `/app/equipo`.

---

## Demo Material

- Slides: https://www.canva.com/design/DAHEuqnjrpc/6jHkQVtlXaC9SG2pfgArTg/edit?utm_content=DAHEuqnjrpc&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton
- Video: En preparacion

---

## Team

| Member | Role |
|---|---|
| Franco Mario Ayala Quispe | AI / Backend / Integration |
| Alex David Tola Julian | Frontend / UX / Product Flow |
| Maya Celina Cadiz Quispe | Product / Research / Presentation |
| Jhamil Calixto Mamani Quea | Data / Validation / Testing |
| Alexander Jonathan Villarroel Torrico | Architecture / Platform / Delivery |

---

## Contact

Para evaluacion tecnica y walkthrough, usar Issues o Discussions en este espacio de trabajo.


