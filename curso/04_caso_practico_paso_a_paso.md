# Módulo 4: Caso Práctico Paso a Paso: Simulación de Políticas de IA

En este módulo realizaremos un **ejemplo práctico guiado de principio a fin**. Aprenderás a estructurar un documento semilla, construir el grafo de conocimiento, configurar la simulación, observar el comportamiento de los agentes en tiempo real e interactuar con el informe final.

---

## 🎯 Escenario de Ejemplo: "Ley de Auditoría Obligatoria de Algoritmos"

**Contexto**: El Ministerio de Tecnología de un país anuncia un borrador de ley que exige a todas las startups de Inteligencia Artificial auditar públicamente el código y datos de entrenamiento de sus modelos antes de comercializarlos.

---

## Paso 1: Redacción del Texto Semilla

Abre la aplicación MiroFish en tu navegador (`http://localhost:3000`) y dirígete al panel de **Carga de Materiales**.

Copia y pega el siguiente texto en el área de entrada:

```markdown
# Borrador de Ley de Transparencia y Auditoría de Algoritmos de IA

El Ministerio de Tecnología ha presentado el proyecto de ley "IA Transparente 2025".
La normativa establece que toda empresa o startup que despliegue modelos de IA en el país deberá someter sus algoritmos a una auditoría gubernamental antes de salir al mercado.

Reacciones iniciales:
- **Asociación de Startups Tecnológicas**: Declara que la medida estrangulará la innovación y causará la fuga de talentos e inversores hacia otros países.
- **Colectivo de Protección al Consumidor**: Celebra la iniciativa afirmando que protegerá a los ciudadanos contra la discriminación algorítmica y los sesgos.
- **Fondo de Inversión RiskCap**: Muestra preocupación por la privacidad del código fuente y evalúa congelar rondas de financiamiento para startups locales.
- **Ministerio de Tecnología**: Mantiene que la ley es innegociable para garantizar la seguridad nacional.
```

Haz clic en el botón **"Construir Grafo de Conocimiento"**.

---

## Paso 2: Verificación del Grafo Generado

Una vez finalizado el procesamiento por GraphRAG:
1. Explora el grafo interactivo generado en pantalla.
2. Identifica los nodos clave: `Ministerio de Tecnología`, `Asociación de Startups`, `Colectivo de Consumidores`, `Fondo RiskCap`, `Proyecto IA Transparente 2025`.
3. Haz clic en un nodo para comprobar las relaciones detectadas (ej. *Asociación de Startups* -> *Se opone a* -> *Proyecto IA Transparente 2025*).

---

## Paso 3: Configuración e Inicio de la Simulación

Avanza a la pantalla de **Configuración de Simulación**:

1. **Requerimiento de Predicción (Prompt)**:
   > *"Predecir si las startups organizarán una protesta digital o migrarán sus operaciones, y cómo reaccionarán los inversores en las próximas 30 rondas."*
2. **Número de Agentes**: `50`
3. **Rondas / Ticks de Simulación**: `30`
4. Haz clic en **"Iniciar Simulación"**.

---

## Paso 4: Monitoreo en Tiempo Real y Muro Social

Mientras se ejecuta la simulación:
1. Observa el **Feed Social**: Verás publicaciones creadas autónomamente por agentes representando a programadores, inversores, periodistas y funcionarios públicos.
2. **Inyección de Variable Dinámica (Opcional)**: En la ronda 15, envía el siguiente evento simulado:
   > *"Noticia de última hora: Un país vecino anuncia exenciones fiscales y cero auditorías para startups de IA."*
3. Observa cómo cambia drásticamente la conversación en el muro social.

---

## Paso 5: Análisis del Informe e Interacción Profunda

Cuando la simulación complete las 30 rondas:

1. Lee el **Informe Predictivo** generado por el `ReportAgent`.
2. Dirígete a la pestaña de **Chat de Interacción Profunda**.
3. Envía una consulta al `ReportAgent`:
   > *"¿Qué porcentaje de inversores decidió retirar sus fondos según la simulación?"*
4. Inicia un chat individual con el agente `Representante de Startups` y pregúntale:
   > *"¿Cuál es tu principal motivo para no aceptar la ley?"*

---

## 📝 Desafío Práctico del Módulo 4

Crea tu propio escenario personalizado (por ejemplo, el lanzamiento de un nuevo videojuego, la aprobación de una ley ambiental o el anuncio de un vehículo eléctrico económico) y ejecuta un flujo completo de simulación en MiroFish siguiendo los 5 pasos descritos.

---

## ✅ Lista de Verificación (Checklist)
- [ ] Logré cargar el texto semilla y construir el grafo.
- [ ] Pude configurar los parámetros de la simulación y lanzar el experimento.
- [ ] Visualicé la interacción entre agentes en el muro social en tiempo real.
- [ ] Utilicé el chat para consultar al `ReportAgent` e interactuar con agentes individuales.

---

▶️ **Siguiente paso:** Ve al [Módulo 5: Configuración Avanzada y Solución de Problemas](./05_configuracion_avanzada_y_solucion_de_problemas.md).
