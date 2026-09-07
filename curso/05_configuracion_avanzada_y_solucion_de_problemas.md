# Módulo 5: Configuración Avanzada y Solución de Problemas (Troubleshooting)

En este último módulo aprenderás las mejores prácticas para optimizar el consumo de recursos, configurar modelos alternativos de LLM y solucionar los errores más comunes durante el despliegue y uso de MiroFish.

---

## 1. Solución de Problemas Frecuentes (Troubleshooting)

### A. Error: `Error 401 Unauthorized` o `Invalid API Key`
- **Causa**: La clave `LLM_API_KEY` o `ZEP_API_KEY` en el archivo `.env` es incorrecta o expiró.
- **Solución**:
  1. Abre el archivo `.env` en la raíz del proyecto.
  2. Verifica que no haya espacios en blanco innecesarios alrededor del signo `=`.
  3. Comprueba que tu cuenta de proveedor LLM (ej. Bailian/Alibaba Qwen u OpenAI) tenga saldo o cuota activa.

---

### B. Error: `Port 3000` o `Port 5001 already in use`
- **Causa**: Hay otra aplicación o una instancia anterior de MiroFish ocupando los puertos.
- **Solución**:
  - En Linux/macOS, libera los puertos con los siguientes comandos:
    ```bash
    kill $(lsof -t -i :3000) 2>/dev/null || true
    kill $(lsof -t -i :5001) 2>/dev/null || true
    ```
  - Luego vuelve a ejecutar `npm run dev`.

---

### C. Consumo elevado de Tokens / Lentitud en la simulación
- **Causa**: Ejecutar simulaciones con más de 100 agentes o más de 50 rondas genera miles de llamadas al LLM.
- **Recomendación para pruebas**:
  - Utiliza configuraciones ligeras para tus primeras pruebas: **10 a 30 agentes** y **10 a 20 rondas**.
  - Si usas el modelo `qwen-plus`, considera probar `qwen-turbo` o `gpt-4o-mini` para reducir la latencia durante la fase de desarrollo.

---

### D. Error de conexión con Zep Cloud (`Zep API Connection Failed`)
- **Causa**: Fallo de red o API key inválida de Zep Cloud.
- **Solución**:
  1. Verifica que la clave `ZEP_API_KEY` esté configurada en `.env`.
  2. Ingresa al panel de control de Zep Cloud (`https://app.getzep.com/`) para confirmar que tu proyecto esté activo.

---

## 2. Ajustes Avanzados de Configuración

### Cambio de Proveedor LLM
MiroFish utiliza el SDK oficial de OpenAI en el backend, por lo que puedes conectar cualquier proveedor compatible con la API de OpenAI.

Ejemplo para configurar **DeepSeek** o **OpenAI directo**:

```env
# Ejemplo para OpenAI
LLM_API_KEY=sk-proj-...
LLM_BASE_URL=https://api.openai.com/v1
LLM_MODEL_NAME=gpt-4o
```

---

## 3. Resumen Final del Curso y Próximos Pasos

¡Felicidades por completar el **Curso de MiroFish**! 🎉

Ahora posees los conocimientos necesarios para:
- Desplegar MiroFish localmente o en servidores usando Docker o código fuente.
- Generar mundos digitales y grafos de conocimiento a partir de cualquier fuente de información.
- Ejecutar simulaciones sociales con enjambres de agentes autónomos.
- Extraer conclusiones predictivas e interactuar con los agentes en un entorno seguro.

---

## 📝 Desafío Práctico Final

1. Experimenta cambiando el modelo LLM en tu archivo `.env` por otro proveedor compatible.
2. Realiza un reinicio del sistema asegurando que no queden procesos residuales en los puertos `3000` y `5001`.

---

## ✅ Lista de Verificación Final (Checklist)
- [ ] Sé cómo resolver errores de autenticación de claves API.
- [ ] Puedo liberar los puertos `3000` y `5001` si se encuentran bloqueados.
- [ ] Entiendo cómo optimizar el número de agentes y rondas para gestionar el gasto de tokens.
- [ ] He completado todos los módulos del curso MiroFish.

---

⏪ **Volver al índice del curso:** [Índice del Curso en README.md](./README.md)
