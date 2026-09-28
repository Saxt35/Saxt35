# Prompt para Codex — Modernización del repositorio de perfil `Saxt35`

## Contexto

Trabaja sobre el repositorio de perfil GitHub `Saxt35/Saxt35` de Noé Briones Pérez.

El objetivo NO es convertirlo en un README cargado de badges o marketing. Debe convertirse en un portfolio técnico de arquitectura coherente con el posicionamiento profesional:

**AI Architect | Solution Architect**

Áreas principales:
- Generative AI
- RAG / GraphRAG
- Data & Knowledge Platforms
- Knowledge Graphs / RDF / SPARQL / Apache Jena
- Java Enterprise / Spring / Jakarta EE
- Data Engineering / Spark / Airflow / Kyuubi
- Cloud / Azure / Docker / Kubernetes/OpenShift
- Security, observability, resilience and governance

El perfil debe distinguir estrictamente entre capacidades demostradas y tecnologías en proceso de aprendizaje/experimentación. No inventes experiencia, métricas, clientes, certificaciones, resultados ni tecnologías no respaldadas por los repositorios.

## Objetivo

Modernizar el repositorio `Saxt35` para que funcione como landing page profesional y conecte:

LinkedIn → GitHub profile → Featured repositories → Architecture evidence.

Debe comunicar en menos de 30 segundos:

1. quién es Noé;
2. cuál es su posicionamiento;
3. qué capacidades técnicas demuestra;
4. cuáles son sus tres proyectos principales;
5. dónde está la evidencia arquitectónica;
6. qué está construyendo/aprendiendo actualmente.

## Repositorios principales

### `ai-knowledge-platform-graphrag`
Presentarlo como evidencia de AI Architecture / Knowledge Architecture. Revisar el repositorio real antes de afirmar tecnologías o resultados. Debe destacar problema, arquitectura, RAG/GraphRAG, Knowledge Graph, provenance, evaluación, ADRs y limitaciones reales.

### `kyuubi-troubleshooting`
Presentarlo como evidencia de Platform Engineering / Big Data Operations / RCA. Revisar contenido real antes de afirmar métricas. Destacar diagnóstico, runbooks, recuperación, observabilidad y lecciones aprendidas.

### `natural-health-agentic-ai`
Si existe, presentarlo explícitamente como **Academic / Portfolio AI Architecture Lab — Work in Progress** hasta que su implementación demuestre lo contrario.

Su propósito es experimentar y medir:
- specialized agents;
- orchestrator / capability routing;
- intent preservation;
- semantic drift;
- reinterpretation;
- context dispersion;
- structured agent contracts;
- RAG / GraphRAG / hybrid retrieval;
- resilience & recovery;
- evaluation;
- guardrails;
- observability;
- AI governance.

No afirmar dominio práctico de LangGraph, MCP u otra tecnología hasta que exista implementación verificable en el repositorio.

## Cambios requeridos

1. Reemplazar el README principal por una versión limpia y profesional basada en `README.md` entregado con este paquete.
2. Corregir inconsistencias de terminología y errores tipográficos, incluyendo referencias a `Tree.js` si en realidad corresponden a `Three.js`; verificar antes de modificar.
3. Eliminar o reformular afirmaciones que no puedan verificarse en los repositorios.
4. Mantener métricas sólo si existe evidencia reproducible/documentada; si una métrica es de PoC, etiquetarla explícitamente como tal.
5. Añadir enlace visible a LinkedIn.
6. Mantener GitHub como evidencia técnica, no como copia textual del CV.
7. Crear `docs/PORTFOLIO-EVIDENCE-MAP.md` con columnas:
   - LinkedIn/CV claim
   - Repository
   - Evidence
   - Status: DEMONSTRATED / POC / LAB / PLANNED
   - Verification path
8. Crear `docs/REPOSITORY-STANDARD.md` definiendo que cada repo destacado debe aspirar a contener:
   - problem statement;
   - scope;
   - architecture diagram;
   - ADRs;
   - implementation/run instructions;
   - tests;
   - evaluation;
   - security;
   - resilience/failure modes;
   - limitations;
   - roadmap.
9. Crear `docs/PROFILE-ROADMAP.md` con backlog priorizado para elevar la calidad del portfolio.
10. No modificar los repositorios externos desde este repo. Sólo documentar las mejoras recomendadas.

## Criterios de calidad

- Sin exageraciones.
- Sin experiencia inventada.
- Sin listas interminables de tecnologías sin contexto.
- Arquitectura y resultados antes que badges.
- Inglés técnico correcto en títulos/keywords; explicación puede combinar inglés y español sólo cuando mejore claridad.
- Navegación simple.
- Mobile friendly en GitHub.
- No incluir información confidencial.
- No incluir datos internos de clientes/organizaciones.
- No incluir secretos, hosts, usuarios ni archivos privados.

## Resultado esperado

Al terminar, entregar un reporte con:

- `RESULT`: PASS / PARTIAL / FAIL
- `FILES_CHANGED`
- `CLAIMS_VERIFIED`
- `CLAIMS_REWORDED`
- `CLAIMS_REMOVED`
- `INCONSISTENCIES_FOUND`
- `REPOSITORY_RECOMMENDATIONS`
- `NEXT_ACTIONS`

No realices commits ni push automáticamente salvo que se solicite explícitamente.
