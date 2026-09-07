# Módulo 2: Backend y Flujo de Simulación

En este módulo exploraremos la arquitectura interna del backend de MiroFish, sus APIs principales y el pipeline paso a paso que transforma un documento de texto en un experimento de simulación social interactivo.

---

## 1. Estructura del Backend

El backend de MiroFish está desarrollado en **Python 3.11+** utilizando **FastAPI** por su alto rendimiento y soporte asíncrono nativo.

Ubicación del código fuente: `backend/app/`

```
backend/app/
├── api/              # Endpoints HTTP REST y WebSockets (rutas de la API)
├── models/           # Modelos de datos Pydantic y estructuras de dominio
├── services/         # Lógica de negocio (GraphRAG, OASIS, Zep, ReportAgent)
├── utils/            # Funciones auxiliares y configuraciones globales
├── config.py         # Carga de variables de entorno (.env)
└── run.py            # Punto de entrada para el servidor Uvicorn/FastAPI
```

---

## 2. El Pipeline de Procesamiento en 4 Etapas

El corazón de MiroFish procesa la información en 4 fases secuenciales:

```
[Documento Semilla]
       │
       ▼
 1. GraphRAG Engine ────► Extracción de Entidades y Grafo de Conocimiento
       │
       ▼
 2. Persona Generator ──► Perfiles de Agentes e Inyección de Memoria en Zep
       │
       ▼
 3. OASIS Engine ───────► Simulación Social Temporal en Paralelo
       │
       ▼
 4. ReportAgent ────────► Generación de Informe Predictivo e Interacción
```

---

### Etapa 1: Extracción y Construcción del Grafo (`GraphRAG`)
- **Proceso**: El texto ingresado (artículo de prensa, reporte, narrativa) se analiza mediante el LLM.
- **Resultado**: Se identifican entidades clave (Personas, Organizaciones, Eventos, Lugares) y las relaciones entre ellas, generando una estructura en grafo de conocimiento.

### Etapa 2: Generación de Personas e Inyección de Memoria
- **Proceso**: Con base en las entidades del grafo y el contexto del problema, el sistema genera automáticamente cientos de perfiles de agentes (*personas*).
- **Memoria Zep Cloud**: Cada agente recibe una biografía, posturas iniciales y un conjunto de recuerdos semillas que se almacenan en la API de Zep Cloud para su posterior recuperación semántica.

### Etapa 3: Motor de Simulación Social (`OASIS Engine`)
- **Proceso**: OASIS orquesta las rondas de interacción (*ticks* temporales).
- **Acciones del Agente**: En cada ronda, los agentes pueden publicar mensajes, responder a otros agentes, cambiar de postura o formar grupos de opinión.
- **Inyección de variables**: El usuario puede emitir un evento externo (ej. "Aparece una nueva noticia") y observar cómo reaccionan los agentes.

### Etapa 4: Análisis e Informes (`ReportAgent`)
- **Proceso**: Una vez completadas las rondas de simulación, el `ReportAgent` examina los registros de actividad.
- **Herramientas del ReportAgent**: Consulta el historial de conversaciones, mide el cambio de sentimiento colectivo y genera un reporte estructurado con conclusiones predictivas.

---

## 3. Endpoints Principales de la API HTTP

| Método | Endpoint | Descripción |
| :--- | :--- | :--- |
| `POST` | `/api/graph/build` | Recibe el texto semilla e inicia la construcción del grafo de conocimiento. |
| `GET` | `/api/graph/status` | Consulta el progreso de extracción del grafo. |
| `POST` | `/api/simulation/start` | Inicia una nueva simulación pasando parámetros (número de agentes, rondas, variables). |
| `GET` | `/api/simulation/stream` | Canal de transmisión en vivo (WebSocket / SSE) para monitorear el avance ronda a ronda. |
| `POST` | `/api/report/generate` | Genera el informe predictivo final usando el `ReportAgent`. |
| `POST` | `/api/report/chat` | Permite enviar preguntas al `ReportAgent` o chatear directamente con un agente del sistema. |

---

## 📝 Desafío Práctico del Módulo 2

1. Examina la carpeta `backend/app/config.py` para comprender cómo se leen las variables de entorno del archivo `.env`.
2. Explora los archivos en `backend/app/services/` para identificar dónde residen las clases principales de simulación.

---

## ✅ Lista de Verificación (Checklist)
- [ ] Entiendo las 4 etapas del pipeline de procesamiento de MiroFish.
- [ ] Conozco la responsabilidad de FastAPI en el manejo de peticiones REST y transmisiones en vivo.
- [ ] Identifico el rol de Zep Cloud en la persistencia de la memoria de los agentes.

---

▶️ **Siguiente paso:** Ve al [Módulo 3: Frontend e Interfaz de Usuario](./03_frontend_e_interfaz.md).
