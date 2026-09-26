# Noe Briones | AI Architect • MDM Lead • Staff Data Engineer

> **Big Data Platform → GraphRAG Platform → AI Governance**
> De resolver caídas de producción de 79.7 GB en HDFS a diseñar plataformas de conocimiento con faithfulness 0.91

📍 México | HASSERV / COMIMSA Experience | Gobierno & Enterprise
🔗 [ai-knowledge-platform-graphrag](https://github.com/Saxt35/ai-knowledge-platform-graphrag) | [kyuubi-troubleshooting](https://github.com/Saxt35/kyuubi-troubleshooting)

---

## 🏗️ Lo que construyo

Diseño y opero plataformas de datos de extremo a extremo: desde la ingesta cruda (Oracle/Postgres/MySQL/Excel/PDF) hasta el portal de consumo con RAG y gobernanza.

```
Ingesta (Airflow) → Lake (HDFS HA + Hive) → Compute (Spark+YARN+Kyuubi) → Governance (Metabase+MDM) → Knowledge (Jena Fuseki+pgvector+ClickHouse) → Portal (Next.js+Tree.js)
```

### 2 Repos que cuentan la historia completa

| Repo | Rol | Qué demuestra | Impacto |
| :--- | :--- | :--- | :--- |
| **[ai-knowledge-platform-graphrag](https://github.com/Saxt35/ai-knowledge-platform-graphrag)** | **Architecture & AI** | GraphRAG con Jena Fuseki + pgvector + ClickHouse, enrichments, evaluation pipeline, ADRs | Faithfulness 0.91, Hallucinations ↓ |
| **[kyuubi-troubleshooting](https://github.com/Saxt35/kyuubi-troubleshooting)** | **Operations & RCA** | Troubleshooting de plataforma productiva, 17 runbooks, diagnóstico de red/contenedor/HDFS/YARN | 79.7GB RCA resuelto, 3 componentes restaurados |

Juntos: **Diseño (Architect) + Operación (SRE/DataOps)**

---

## 🎯 Caso Estrella - RCA 79.7 GB (Kyuubi)

**Problema:** `/tmp/hive/<USER>/staging` con 79.7 GB sin limpieza → HDFS >90% → YARN sin espacio → Kyuubi (10009) caído → Livy sessions `dead` → Zeppelin caído.

**Diagnóstico:**
```bash
hdfs dfs -du -s -h /tmp/hive
hdfs dfsadmin -report
yarn node -list  # Total Nodes:4
nc -vz <KYUUBI_HOST> 10009
docker top kyuubi / netstat -tulpn
curl http://<LIVY_HOST>:8998/sessions | grep -E "dead|idle"
```

**Solución:** Runbook preventivo + limpieza `hdfs dfs -rm -r -skipTrash` + monitoreo HDFS/YARN. Plataforma restaurada.

Ver detalle: [`kyuubi-troubleshooting/docs/14_Caso_Real_Spark_Staging.md`](https://github.com/Saxt35/kyuubi-troubleshooting)

---

## 🧠 Caso Estrella - GraphRAG 0.91 Faithfulness

**Problema:** Consultas complejas sin trazabilidad, alucinaciones en LLM.

**Solución:** Arquitectura GraphRAG de 5 capas:
1. **Ingestion:** Oracle/Postgres/MySQL/Excel/PDF → Airflow → HDFS
2. **Staging:** Hive External + Parquet
3. **Enrichment:** NER, embeddings (pgvector), ontología (Jena Fuseki)
4. **Retrieval:** Node filter middleware (Next.js API) → SPARQL (Jena) + Vector Search (pgvector) + OLAP (ClickHouse)
5. **Consumption:** Next.js + Tree.js 3D + Metabase governance

**Resultado:** Faithfulness 0.91, evaluado con RAGAS, con ADRs y diagrama anon.

Ver: [`ai-knowledge-platform-graphrag`](https://github.com/Saxt35/ai-knowledge-platform-graphrag)

---

## 🛠️ Stack

**Big Data:** Apache Spark, Kyuubi, Hadoop HDFS, YARN, Hive, Livy, Airflow, Zeppelin, Kafka
**AI / RAG:** Apache Jena Fuseki, pgvector, ClickHouse, GNN/HUG, PyTorch, Spark NLP/ML
**Gobernanza:** MDM (Oracle/Postgres/MySQL/Excel/PDF → catálogos transversales), Metabase (permisos por perfil/intereses), Handbook
**Portal:** Next.js, Node.js, Tree.js, PostgreSQL, OLAP ClickHouse
**Infra & Tools:** Docker/Compose, Celery, Hue, Kafka Control Center/Connect

---

## 📚 Estructura de mi trabajo

```
HASSERV/COMIMSA Experience
├── Fase 1 - Diagnóstico (Red, Contenedor, HDFS, YARN, Kyuubi, Livy/Zeppelin)
├── Fase 2 - Integración (Airflow+Hive+Kyuubi, Zeppelin, JDBC validada)
└── Fase 3 - Gobernanza & Portal (Runbook, Lessons Learned, Metabase, Next.js, MDM)
    └── RCA: 79.7GB staging (estrella)
```

---

## 🔒 Seguridad & Anonimización

Todo mi portafolio está anonimizado: `<HOST>`, `<PORT>`, `<USER>`, `<KYUUBI_HOST>`. Sin datos de gobierno. `.gitignore` bloquea `private/`, `*.pdf`, `*.xlsx`, `*.csv`. Ver `architecture_anon.png`.

---

## 📫 Contacto

- GitHub: [@Saxt35](https://github.com/Saxt35)
- Repos: [GraphRAG Platform](https://github.com/Saxt35/ai-knowledge-platform-graphrag) + [Troubleshooting](https://github.com/Saxt35/kyuubi-troubleshooting)
- Rol objetivo: AI Architect / Staff Data Engineer / MDM Lead

> **Busco roles donde se valore: Diseño de GraphRAG + Operación de Big Data + Gobernanza MDM + Portal de consumo.**

---

*Última actualización: Sept 2026 - 2 repos activos, 28 docs, 2 diagramas anonimizados, faithfulness 0.91, RCA 79.7GB resuelto.*
