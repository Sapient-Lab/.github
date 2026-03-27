<div align="center">

<img src="https://img.shields.io/badge/Microsoft%20Innovation%20Challenge-2026-0078D4?style=for-the-badge" />
<img src="https://img.shields.io/badge/Project-Lab%20Notebook%20AI%20Assistant-0A66C2?style=for-the-badge" />
<img src="https://img.shields.io/badge/Focus-Agentic%20AI%20%7C%20Safety%20%7C%20Explainability-111827?style=for-the-badge" />
<img src="https://img.shields.io/badge/Stack-React%2019%20%2B%20NestJS%20%2B%20MySQL-2563EB?style=for-the-badge" />
<br/>
<img src="https://img.shields.io/badge/Azure%20OpenAI-LLM-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20AI%20Foundry-Orchestration-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Vision-Image%20AI-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<br/>
<img src="https://img.shields.io/badge/Azure%20Speech-STT%2FTTS-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Document%20Intelligence-Docs%20AI-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Blob%20Storage-Files-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />

# Sapient Lab

### Lab Notebook AI Assistant

Plataforma para asistir a investigadores en el razonamiento experimental con agentes de IA,
sin reemplazar el juicio cientifico humano.

</div>

---

## Acceso Rapido para Jurados

<div align="center">

[![Slides](https://img.shields.io/badge/Slides-Canva-00C4CC?style=for-the-badge&logo=canva&logoColor=white)](https://www.canva.com/design/DAHEuqnjrpc/6jHkQVtlXaC9SG2pfgArTg/edit?utm_content=DAHEuqnjrpc&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
[![Frontend](https://img.shields.io/badge/Frontend-React%20%2B%20Vite-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://github.com/Sapient-Lab/Frontend)
[![Backend](https://img.shields.io/badge/Backend-NestJS%20%2B%20OpenML-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)](https://github.com/Sapient-Lab/back_end)

</div>

---

## Descripcion del Proyecto

Sapient Lab es un asistente de cuaderno de laboratorio basado en agentes que ayuda a equipos de investigacion a interpretar protocolos,
analizar resultados experimentales y proponer siguientes pasos explicados, manteniendo seguridad estricta y control humano en la decision final.

El sistema integra analisis multimodal (texto, CSV, imagen y voz), evidencia externa con OpenML y una arquitectura de IA responsable
orientada a transparencia, trazabilidad y limites de uso en escenarios sensibles.

---

## Enunciado del Reto

Los investigadores quieren ayuda para razonar sobre experimentos sin reemplazar el juicio cientifico.
El sistema debe interpretar protocolos, sugerir variaciones para siguientes pasos,
analizar resultados desde texto, CSV o imagenes y explicar claramente por que recomienda cada accion.

La solucion debe aplicar limites de seguridad estrictos en dominios biologicos/clinicos,
filtrado de contenido y control de asesoramiento no permitido.

---

## Que Construimos

**Sapient Lab** integra una experiencia de cuaderno cientifico asistido por agentes con:

- interpretacion de protocolos experimentales,
- analisis multimodal (texto, CSV, imagen, voz),
- recomendaciones explicadas para siguientes pasos,
- controles de seguridad y filtrado,
- soporte de evidencia externa con OpenML.

---

## Arquitectura General

```mermaid
flowchart LR
	R[Equipo de Investigacion] --> FE[Frontend: React + Vite]
	FE -->|/api| BE[Backend: NestJS]

	BE --> AO[Orquestador de Agentes]
	AO --> PI[Interprete de Protocolos]
	AO --> MA[Analizador Multimodal]
	AO --> RV[Recomendador de Variaciones]
	AO --> SG[Guardrails de Seguridad]
	AO --> EX[Compositor de Explicabilidad]
	AO --> OM[Conector OpenML]

	OM --> OAPI[(OpenML API)]
	BE --> DB[(MySQL)]
	BE --> BLOB[(Azure Blob)]
```

---

## Interaccion de Agentes de IA (Vista para Jurados)

```mermaid
sequenceDiagram
	participant User as Investigador
	participant UI as Frontend Notebook
	participant API as Orquestador Backend
	participant PI as Agente de Protocolo
	participant MM as Agente Multimodal
	participant OM as Agente OpenML
	participant SG as Agente de Seguridad
	participant EX as Agente de Explicabilidad

	User->>UI: Pregunta experimental
	UI->>API: POST /api/ai/notebook/chat
	API->>PI: Interpretar contexto del protocolo
	API->>MM: Analizar texto/CSV/imagen
	API->>OM: Recuperar evidencia de benchmark
	PI-->>API: Razonamiento del protocolo
	MM-->>API: Hallazgos de datos
	OM-->>API: Metadata comparable de OpenML
	API->>SG: Aplicar filtros de seguridad y politicas
	SG-->>API: Restricciones de respuesta permitida
	API->>EX: Construir recomendacion justificada
	EX-->>UI: Razonamiento claro + siguientes pasos
	UI-->>User: Soporte a la decision human-in-the-loop
```

---

## Stack Tecnologico

| Capa | Tecnologias |
|---|---|
| Frontend | React 19, TypeScript, Vite, React Router, Framer Motion |
| Backend | NestJS, Node.js, TypeScript, class-validator |
| Datos | MySQL, documentos de contexto de proyecto, notas de experimento |
| Servicios de IA | Azure OpenAI/Foundry, Azure Vision, Azure Speech, Azure Document Intelligence |
| Benchmark externo | OpenML (`/api/openml/*`) |
| Almacenamiento | Azure Blob Storage |

## Servicios de Azure en Uso

<div align="center">

<img src="https://img.shields.io/badge/Azure%20OpenAI-Razonamiento%20LLM-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20AI%20Foundry-Orquestacion%20de%20Agentes-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Vision-Analisis%20de%20Imagen-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Speech-Voz%20a%20Texto-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Document%20Intelligence-Analisis%20Documental-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />
<img src="https://img.shields.io/badge/Azure%20Blob%20Storage-Almacenamiento%20de%20Archivos-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white" />

</div>

---

## Repositorios del Proyecto (Para Jurados)

- Frontend: https://github.com/Sapient-Lab/Frontend
- Backend: https://github.com/Sapient-Lab/back_end

---

## Matriz de Evaluacion para Jurados (Semana del 30 de marzo de 2026)

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

## Material de Demo

- Slides: https://www.canva.com/design/DAHEuqnjrpc/6jHkQVtlXaC9SG2pfgArTg/edit?utm_content=DAHEuqnjrpc&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton
- Video: En preparacion

---

## Equipo

| Integrante | Rol |
|---|---|
| Franco Mario Ayala Quispe | AI / Backend / Integration |
| Alex David Tola Julian | Frontend / UX / Product Flow |
| Maya Celina Cadiz Quispe | Product / Research / Presentation |
| Jhamil Calixto Mamani Quea | Data / Validation / Testing |
| Alexander Jonathan Villarroel Torrico | Architecture / Platform / Delivery |

---

## Contacto

Para evaluacion tecnica y walkthrough, usar Issues o Discussions en este espacio de trabajo.


