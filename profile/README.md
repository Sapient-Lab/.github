<div align="center">

<img src="https://img.shields.io/badge/Microsoft%20Innovation%20Challenge-2026-0078D4?style=for-the-badge" />
<img src="https://img.shields.io/badge/Project-Lab%20Notebook%20AI%20Assistant-0A66C2?style=for-the-badge" />
<img src="https://img.shields.io/badge/Focus-Agentic%20AI%20%7C%20Safety%20%7C%20Explainability-111827?style=for-the-badge" />
<img src="https://img.shields.io/badge/Stack-React%2019%20%2B%20NestJS%20%2B%20MySQL-2563EB?style=for-the-badge" />

# Sapient Lab

### Lab Notebook AI Assistant

Plataforma para asistir a investigadores en el razonamiento experimental con agentes de IA,
sin reemplazar el juicio cientifico humano.

</div>

---

## Judge Quick Access

<div align="center">

[![Slides](https://img.shields.io/badge/Slides-Canva-00C4CC?style=for-the-badge&logo=canva&logoColor=white)](https://www.canva.com/design/DAHEuqnjrpc/6jHkQVtlXaC9SG2pfgArTg/edit?utm_content=DAHEuqnjrpc&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
[![Frontend](https://img.shields.io/badge/Frontend-React%20%2B%20Vite-61DAFB?style=for-the-badge&logo=react&logoColor=black)](../../Frontend)
[![Backend](https://img.shields.io/badge/Backend-NestJS%20%2B%20OpenML-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)](../../back_end)

</div>

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

---

## Project Repositories (Current Workspace)

- Frontend: [Frontend](../../Frontend)
- Backend: [back_end](../../back_end)
- API and technical docs: [back_end/data/Document](../../back_end/data/Document)

---

## Evaluation Alignment

| Criterion | Implementation Evidence |
|---|---|
| Explainability | Recomendaciones con justificacion visible en notebook y flujo de insercion limpia (`extract-insertable`). |
| Safe agent design | Capas de safety y filtrado para dominios sensibles; backend con endpoints de analisis de seguridad. |
| Data/model orchestration | Orquestacion de agentes + contexto de proyecto + documentos + OpenML. |
| Human-in-the-loop | El sistema asiste, no reemplaza; la decision final queda en el investigador. |

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
| Jhamil Calixto Mamani Quea | Data / Validation / Testing |
| Alexander Jonathan Villarroel Torrico | Architecture / Platform / Delivery |

---

## Contact

Para evaluacion tecnica y walkthrough, usar Issues o Discussions en este espacio de trabajo.


