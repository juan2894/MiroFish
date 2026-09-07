# Módulo 0: Introducción y Arquitectura de MiroFish

¡Bienvenido al **Módulo 0**! En esta lección aprenderás qué es MiroFish, la visión detrás de la simulación de inteligencia de enjambre (*swarm intelligence*) y cómo interactúan las distintas tecnologías que componen la plataforma.

---

## 1. ¿Qué es MiroFish?

**MiroFish** es un motor de predicción de inteligencia artificial de nueva generación basado en tecnología multi-agente. Su objetivo principal es tomar **materiales o datos semilla del mundo real** (noticias, borradores de políticas, informes financieros o incluso relatos literarios) y construir un **mundo digital paralelo de alta fidelidad**.

En este mundo digital interactúan cientos o miles de **agentes inteligentes autónomos**. Cada agente cuenta con:
- Una personalidad propia (*persona*).
- Memoria individual y colectiva a largo plazo.
- Lógica de comportamiento y toma de decisiones.

A través de la interacción libre entre estos agentes, emergen comportamientos sociales y tendencias colectivas. Como usuario, puedes observar la simulación desde una **"Vista de Dios"** e inyectar variables dinámicas para predecir futuros escenarios.

---

## 2. Conceptos Clave

### A. Inteligencia de Enjambre (*Swarm Intelligence*)
A diferencia de un LLM tradicional que predice la siguiente palabra de forma aislada, la inteligencia de enjambre simula cómo decisiones individuales interactúan en un entorno social complejo. La suma de micro-interacciones genera un comportamiento macro (opinión pública, tendencias del mercado, dinámicas de grupo).

### B. Espejo Digital / Sandbox
Es un entorno seguro e interactivo donde puedes poner a prueba hipótesis ("¿Qué pasaría si...?"). Permite evaluar el impacto de medidas o eventos a riesgo cero antes de tomar decisiones en la vida real.

---

## 3. Stack Tecnológico y Componentes Principales

MiroFish integra varias tecnologías avanzadas en un flujo coherente:

```
+-----------------------------------------------------------------------+
|                            MiroFish Frontend                          |
|                             (React + Vite)                            |
+-----------------------------------------------------------------------+
                                   | API HTTP / WebSockets
+-----------------------------------------------------------------------+
|                            MiroFish Backend                           |
|                             (Python FastAPI)                          |
|                                                                       |
|  +--------------------+   +-------------------+   +----------------+  |
|  | GraphRAG Engine    |   | OASIS Engine      |   | Zep Cloud      |  |
|  | (Grafo Conocimiento)|  | (Simulación Social)|  | (Memoria Agente|  |
|  +--------------------+   +-------------------+   +----------------+  |
|                                                                       |
|  +-----------------------------------------------------------------+  |
|  | ReportAgent (Generador e interactuador de informes)              |  |
|  +-----------------------------------------------------------------+  |
+-----------------------------------------------------------------------+
```

1. **OASIS Engine (*Open Agent Social Interaction Simulations*)**:
   - Desarrollado por el equipo de CAMEL-AI. Es el motor principal que orquesta el bucle de simulación social y la comunicación entre agentes en tiempo real.
2. **GraphRAG (Retrieval-Augmented Generation con Grafos)**:
   - Extrae entidades (personas, organizaciones, conceptos) y sus relaciones a partir de los documentos semilla. Esto permite estructurar el conocimiento del mundo antes de iniciar la simulación.
3. **Zep Cloud**:
   - Plataforma de almacenamiento de memoria a largo plazo. Permite a los agentes recordar interacciones pasadas, recuperar contexto relevante y evolucionar con el tiempo.
4. **ReportAgent**:
   - Un agente especializado equipado con herramientas para analizar el registro histórico de la simulación y generar informes analíticos profundos en lenguaje natural.

---

## 4. Flujo de Trabajo en 5 Pasos de MiroFish

1. **Construcción del Grafo (*Graph Building*)**: Extracción de entidades y relaciones de los documentos fuente + Inyección de memoria.
2. **Configuración del Entorno (*Environment Setup*)**: Generación de *personas* (perfiles de agentes) y parametrización de la red social/simulada.
3. **Ejecución de la Simulación (*Simulation*)**: Corrida temporal en paralelo, actualización continua de memorias y ejecución de interacciones entre agentes.
4. **Generación de Reportes (*Report Generation*)**: El `ReportAgent` examina los resultados y sintetiza un informe predictivo detallado.
5. **Interacción Profunda (*Deep Interaction*)**: Conversa con cualquier agente del mundo simulado o chatea con el `ReportAgent` para explorar escenarios alternativos.

---

## 📝 Desafío Práctico del Módulo 0

Reflexiona sobre las siguientes preguntas antes de pasar a la parte técnica de instalación:
1. Identifica un caso de uso real en tu área (ej. lanzamiento de un producto, gestión de crisis de marca, análisis de políticas públicas) que se beneficiaría de una simulación de enjambre.
2. ¿Por qué crees que un modelo LLM simple (como un solo chat) no es suficiente para predecir dinámicas de opinión pública comparado con un sistema multi-agente?

---

## ✅ Lista de Verificación (Checklist)
- [ ] Comprendo la diferencia entre una consulta a un LLM estándar y una simulación multi-agente.
- [ ] Entiendo la función de GraphRAG, OASIS y Zep Cloud dentro de MiroFish.
- [ ] Conozco las 5 fases del flujo de trabajo de MiroFish.

---

▶️ **Siguiente paso:** Ve al [Módulo 1: Instalación y Configuración del Entorno](./01_instalacion_y_configuracion.md).
