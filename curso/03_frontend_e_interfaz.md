# Módulo 3: Frontend e Interfaz de Usuario

En este módulo aprenderás a navegar y utilizar la interfaz web de MiroFish. Veremos cómo está estructurado el código del cliente en React/Vite y cómo utilizar cada una de las pantallas de la aplicación.

---

## 1. Arquitectura del Frontend

El frontend de MiroFish está desarrollado con **React**, **Vite** y **Tailwind CSS**, ofreciendo una interfaz reactiva de alta velocidad.

Ubicación del código fuente: `frontend/src/`

```
frontend/src/
├── components/       # Componentes de UI reutilizables (Botones, Modales, Contenedores)
├── pages/            # Páginas principales (Grafo, Simulación, Reporte, Chat)
├── services/         # Clientes de API para conectarse con el Backend FastAPI
├── styles/           # Estilos CSS globales y Tailwind CSS
├── App.jsx           # Enrutamiento principal y layout global
└── main.jsx          # Punto de entrada de React
```

---

## 2. Pantallas Principales de la Aplicación Web

La interfaz de MiroFish está dividida en 4 visiones principales que reflejan el flujo de trabajo:

```
┌────────────────────────────────────────────────────────────────────────┐
|  [ 1. Carga & Grafo ] ──► [ 2. Config. Simulación ] ──► [ 3. Reporte ]|
|                                                                        |
|  ┌─────────────────────────────────┐   ┌────────────────────────────┐  |
|  |   Visualización de Red / Grafo   |   |   Feed Social en Vivo      |  |
|  |   (Nodos = Agentes / Entidades) |   |   (Publicaciones y Reacciones) |  |
|  └─────────────────────────────────┘   └────────────────────────────┘  |
|                                                                        |
|  ┌──────────────────────────────────────────────────────────────────┐  |
|  |   Panel de Interacción Profunda (Chat con Agentes / ReportAgent) |  |
|  └──────────────────────────────────────────────────────────────────┘  |
└────────────────────────────────────────────────────────────────────────┘
```

---

### A. Pantalla 1: Carga de Materiales y Visualizador del Grafo
- **Entrada de Texto**: Permite pegar un texto, informe o noticia en formato de texto plano o Markdown.
- **Botón "Construir Grafo"**: Inicia el proceso de extracción en el backend.
- **Grafo Interactivo**: Muestra una red visual interactiva con nodos (entidades) y aristas (relaciones). Puedes hacer clic en un nodo para ver sus detalles y conexiones.

### B. Pantalla 2: Panel de Control de Simulación
- **Configuración de Parámetros**:
  - *Número de Rondas / Ticks*: Cuántos pasos temporales avanzará la simulación.
  - *Límite de Agentes*: Tamaño de la población de la simulación.
  - *Requerimiento de Predicción*: Descripción en lenguaje natural del aspecto que deseas evaluar (ej. "¿Cómo reaccionará la opinión pública ante la subida de impuestos?").
- **Muro Social en Tiempo Real**: Durante la simulación, verás un muro de noticias o feed interactivo similar a una red social donde los agentes publican, dan *likes*, comparten y comentan de forma autónoma.

### C. Pantalla 3: Informe Predictivo Final
- Muestra el documento analítico generado por el `ReportAgent`.
- Incluye gráficos de sentimiento, distribución de opinión, eventos clave sucedidos en la simulación y conclusiones sintetizadas.

### D. Pantalla 4: Interacción Profunda (*Deep Interaction Chat*)
- **Chat con ReportAgent**: Haz preguntas sobre el informe (ej. "¿Cuál fue el factor determinante para la reacción negativa del Agente X?").
- **Chat Directo con Agentes**: Selecciona cualquier agente de la simulación y entabla una conversación individual uno a uno para indagar sobre sus motivaciones.

---

## 3. Internacionalización (i18n)

MiroFish incluye soporte multilingüe integrado accesible desde la barra superior de la aplicación. Puedes alternar el idioma de la interfaz entre:
- Español / Inglés / Chino (`locales/`).

---

## 📝 Desafío Práctico del Módulo 3

1. Inicia el servidor de desarrollo (`npm run dev`) y abre `http://localhost:3000`.
2. Explora la barra de navegación superior y familiarízate con las distintas secciones.
3. Observa los componentes en `frontend/src/pages/` para entender cómo se conectan las vistas con los servicios de la API.

---

## ✅ Lista de Verificación (Checklist)
- [ ] Reconozco las 4 pantallas principales de la interfaz de usuario.
- [ ] Comprendo cómo visualizar el grafo de conocimiento interactivo.
- [ ] Sé cómo cambiar de idioma y cómo acceder al chat de interacción con agentes.

---

▶️ **Siguiente paso:** Ve al [Módulo 4: Caso Práctico Paso a Paso](./04_caso_practico_paso_a_paso.md).
