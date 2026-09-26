# Noe Briones | AI Architect • MDM Lead • Staff Data Engineer
### De resolver caídas de 79.7GB a diseñar GraphRAG 0.91

📍 México · GitHub: [@Saxt35](https://github.com/Saxt35)

Arquitecto y operador hands-on de plataformas de datos e IA en contexto enterprise/gobierno (HASSERV / COMIMSA), con foco en diseño de arquitectura, RCA en producción y gobierno de datos MDM.

---

## Flujo end-to-end (texto)
**Ingesta → Lake → Compute → Governance → Knowledge → Portal**

```text
Oracle/Postgres/MySQL/Excel/PDF
  → Airflow
  → HDFS HA + Hive
  → Spark + YARN + Kyuubi (jdbc:hive2://<HOST>:10009)
  → Metabase (RBAC por perfil)
  → Jena Fuseki + pgvector + ClickHouse + NER enrichments
  → Next.js + Node middleware
  → SPARQL + Vector + OLAP + Three.js 3D
```

## Repos estrella (Architecture + Operations)

| Repo | Rol | Qué demuestra | Impacto |
|---|---|---|---|
| [ai-knowledge-platform-graphrag](https://github.com/Saxt35/ai-knowledge-platform-graphrag) | Architecture & AI | Diseño de arquitectura GraphRAG en 5 capas, ADRs, integración SPARQL + vector + OLAP | **Faithfulness 0.91 (RAGAS)**, reducción de hallucination, blueprint reutilizable |
| [kyuubi-troubleshooting](https://github.com/Saxt35/kyuubi-troubleshooting) | Operations & RCA / Troubleshooting | RCA de caída en cascada multi-componente con runbook ejecutable y gobernanza operativa | **79.7GB limpiados**, recuperación de servicio en clúster de **4 nodes**, **3 componentes** restablecidos |

---

## Caso Estrella: RCA 79.7GB (Operations)

**Situación**: crecimiento en `/tmp/hive/<USER>/staging` hasta **79.7GB** → HDFS >90% → YARN sin espacio → Kyuubi (10009) no disponible → Livy/Zeppelin degradados.  
**Tarea**: recuperar servicio y estabilizar operación.  
**Acción**: diagnóstico por capas + limpieza controlada + runbook preventivo.  
**Resultado**: restauración de conectividad JDBC y continuidad operativa; documentación operativa en **17 guías**.

```bash
hdfs dfs -du -s -h /tmp/hive/<USER>/staging
hdfs dfsadmin -report
yarn node -list
docker top kyuubi
netstat -tulpn | grep 10009
ps aux | grep kyuubi
curl http://<HOST>:8998/sessions
nc -vz <HOST> 10009
hdfs dfs -rm -r -skipTrash /tmp/hive/<USER>/staging/*
```

Referencia: [kyuubi-troubleshooting](https://github.com/Saxt35/kyuubi-troubleshooting)  
Artefactos clave: `diagrams/architecture_anon.png`, `runbook/runbook.sh` (anonimizado con `<HOST>`, `<PORT>`, `<USER>`).

## Caso Estrella: GraphRAG 0.91 (Architecture)

**5 capas de arquitectura**:
1. **Ingesta**: Oracle/Postgres/MySQL/Excel/PDF → Airflow → HDFS HA + Hive  
2. **Compute**: Spark + YARN + Kyuubi (`jdbc:hive2://<HOST>:10009`)  
3. **Governance**: Metabase con permisos por perfil  
4. **Knowledge**: Jena Fuseki + pgvector + ClickHouse + NER enrichments  
5. **Portal**: Next.js + Node filter middleware → SPARQL + Vector + OLAP → Three.js 3D

Métrica estrella: **Faithfulness 0.91 (RAGAS)** con reducción de respuestas alucinadas y trazabilidad técnica vía ADRs + diagrama anonimizado.

Referencia: [ai-knowledge-platform-graphrag](https://github.com/Saxt35/ai-knowledge-platform-graphrag)

---

## Stack técnico (agrupado)

- **Big Data**: HDFS, Hive, Spark, YARN, Kyuubi, Livy, Kafka  
- **AI/RAG**: Jena Fuseki, pgvector, ClickHouse, GNN/HUG, PyTorch, Spark NLP/ML  
- **Gobernanza**: Metabase (RBAC), catálogo transversal MDM  
- **Portal**: Next.js, Node.js, PostgreSQL, Three.js 3D  
- **Infra & Tools**: Docker, Docker Compose, Airflow, Celery, Zeppelin, Hue

## Estructura de trabajo HASSERV / COMIMSA

- **Diagnóstico**: Red, Contenedor, HDFS, YARN, Kyuubi, Livy/Zeppelin  
- **Integración**: Airflow+Hive+Kyuubi, Zeppelin, JDBC validada, caso 79.7GB  
- **Gobernanza**: Runbook, Lessons Learned, Handbook, Metabase, consultas complejas en Next.js, MDM

Modelo de datos MDM transversal: **Oracle/Postgres/MySQL/Excel/PDF → catálogos compartidos** para consistencia entre dominios.

## Seguridad y buenas prácticas

- Sanitización y anonimización operativa: `<HOST>`, `<PORT>`, `<USER>` en documentación y scripts  
- Control de exposición por `.gitignore`: `private/`, `*.pdf`, `*.xlsx`

---

## CTA

**Busco roles donde se valore GraphRAG + Operación Big Data + Gobernanza MDM + Portal.**  
Si tu equipo necesita arquitectura con métricas, troubleshooting real en producción y ejecución hands-on end-to-end, conversemos.
