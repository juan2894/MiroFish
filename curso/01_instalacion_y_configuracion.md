# Módulo 1: Instalación y Configuración del Entorno

En este módulo aprenderás a preparar y configurar el entorno de ejecución para MiroFish. Cubriremos los requisitos previos, la configuración de variables de entorno y los dos métodos de despliegue: **por código fuente** (recomendado para desarrollo) y **mediante Docker** (recomendado para despliegue rápido).

---

## 1. Requisitos Previos del Sistema

Antes de comenzar, asegúrate de tener instaladas las siguientes herramientas en tu sistema:

| Herramienta | Versión Requerida | Propósito | Verificación de Instalación |
| :--- | :--- | :--- | :--- |
| **Node.js** | 18+ (con npm) | Ejecución del frontend React | `node -v` |
| **Python** | ≥ 3.11 y ≤ 3.12 | Ejecución del backend FastAPI | `python --version` o `python3 --version` |
| **uv** | Última versión | Gestor ultra-rápido de paquetes Python | `uv --version` |
| **Docker / Docker Compose** *(Opcional)* | Última versión | Despliegue en contenedores aislados | `docker --version` y `docker compose version` |

> 💡 **Nota sobre Python**: MiroFish requiere Python entre las versiones 3.11 y 3.12. Si tienes varias versiones instaladas, la herramienta `uv` se encargará de gestionar el entorno virtual adecuado.

---

## 2. Configuración de Variables de Entorno (`.env`)

MiroFish requiere claves de API externas para conectarse a modelos de lenguaje (LLM) y al servicio de memoria Zep Cloud.

### Paso 2.1: Copiar el archivo de plantilla
En la raíz del proyecto, copia el archivo de ejemplo `.env.example` para crear tu archivo `.env`:

```bash
cp .env.example .env
```

### Paso 2.2: Configurar las claves en el `.env`
Abre el archivo `.env` recién creado en tu editor e introduce las credenciales requeridas:

```env
# =====================================================================
# Configuración del Modelo de Lenguaje (LLM API)
# Compatible con la API de OpenAI SDK (OpenAI, Qwen/Alibaba, DeepSeek, etc.)
# =====================================================================
LLM_API_KEY=tu_clave_api_aqui
LLM_BASE_URL=https://dashscope.aliyuncs.com/compatible-mode/v1
LLM_MODEL_NAME=qwen-plus

# =====================================================================
# Configuración de Zep Cloud (Memoria a Largo Plazo)
# Registro gratuito con cuota mensual disponible en: https://app.getzep.com/
# =====================================================================
ZEP_API_KEY=tu_clave_zep_api_aqui
```

#### Recomendaciones sobre el modelo LLM:
- **Alibaba Qwen (Bailian Platform)**: Es el proveedor recomendado por el equipo oficial (`qwen-plus` o `qwen-max`). Ofrece un rendimiento óptimo en la extracción de entidades y simulaciones conversacionales.
- **OpenAI**: Puedes usar `https://api.openai.com/v1` con el modelo `gpt-4o` o `gpt-4o-mini`.

---

## 3. Opción 1: Despliegue por Código Fuente (Recomendado)

### Paso 3.1: Instalación de Dependencias
MiroFish incluye scripts automatizados en `package.json` para facilitar la instalación de dependencias de frontend y backend con un solo comando:

```bash
# Instalación global automatizada (Raíz + Frontend + Backend)
npm run setup:all
```

Si prefieres realizar la instalación paso a paso:

```bash
# 1. Instalar dependencias de Node.js (Raíz y Frontend)
npm run setup

# 2. Instalar dependencias de Python para el Backend (crea entorno virtual con uv)
npm run setup:backend
```

### Paso 3.2: Iniciar los Servicios
Para lanzar la aplicación completa en modo de desarrollo:

```bash
npm run dev
```

Este comando iniciará concurrentemente:
- **Frontend (Vite/React)**: Accesible en `http://localhost:3000`
- **Backend (FastAPI)**: Accesible en `http://localhost:5001`

Si deseas iniciar cada servicio de manera independiente en terminales separadas:

```bash
# Terminal 1: Solo Backend
npm run backend

# Terminal 2: Solo Frontend
npm run frontend
```

---

## 4. Opción 2: Despliegue con Docker

Si prefieres usar Docker para evitar instalar Node.js o Python en tu máquina local:

### Paso 4.1: Asegurar la presencia de `.env`
Asegúrate de haber creado y configurado el archivo `.env` en la raíz del proyecto según se explicó en la Sección 2.

### Paso 4.2: Construir e Iniciar el Contenedor
Ejecuta el siguiente comando en la raíz del repositorio:

```bash
docker compose up -d
```

Docker Compose se encargará de:
1. Construir la imagen del frontend y servirlos en el puerto `3000`.
2. Construir la imagen del backend y levantar la API en el puerto `5001`.

Para verificar el estado de los contenedores en ejecución:

```bash
docker compose ps
```

Para ver los logs de la aplicación en tiempo real:

```bash
docker compose logs -f
```

---

## 📝 Desafío Práctico del Módulo 1

1. Verifica las versiones de tus herramientas locales (`node -v`, `python --version`, `uv --version`).
2. Crea tu archivo `.env` e ingresa credenciales válidas (puedes obtener una API key gratuita de prueba en Zep Cloud).
3. Inicia la aplicación utilizando `npm run dev` o `docker compose up -d` y abre el navegador en `http://localhost:3000`.

---

## ✅ Lista de Verificación (Checklist)
- [ ] Archivo `.env` creado a partir de `.env.example`.
- [ ] Claves `LLM_API_KEY` y `ZEP_API_KEY` configuradas correctamente.
- [ ] Dependencias de frontend y backend instaladas con éxito.
- [ ] Frontend accesible en `http://localhost:3000` y Backend respondiendo en `http://localhost:5001`.

---

▶️ **Siguiente paso:** Ve al [Módulo 2: Backend y Flujo de Simulación](./02_backend_y_simulacion.md).
