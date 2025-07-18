# 🤖 Bot de Telegram Humanizado

## 🎥 Video Demostración

[![Bot de Telegram Humanizado - Video Tutorial](https://img.youtube.com/vi/rWN_LS6cnXc/maxresdefault.jpg)](https://youtu.be/rWN_LS6cnXc)

**👆 Haz clic en la imagen para ver el video tutorial completo**

## 📋 Descripción

Este es un bot de Telegram avanzado que simula conversaciones humanas naturales mediante el uso de inteligencia artificial. El bot está diseñado para procesar múltiples tipos de contenido (texto, voz, imágenes y documentos) y responder de manera inteligente en español, con características humanizadas como delays de escritura y respuestas contextuales.

## ✨ Características Principales

### 🎯 Procesamiento Multimodal

- **📝 Mensajes de texto**: Procesamiento directo de consultas en español
- **🎙️ Mensajes de voz**: Transcripción automática usando OpenAI Whisper
- **🖼️ Imágenes**: Análisis visual con GPT-4o-mini para describir contenido
- **📄 Documentos**: Extracción y procesamiento de texto usando LlamaIndex

### 🧠 Inteligencia Artificial

- **Modelo**: Google Gemini 2.5 Flash Preview como modelo principal
- **Herramientas integradas**:
  - 🧮 Calculadora para operaciones matemáticas
  - 📚 Wikipedia para consultas informativas
- **Personalidad**: "Bob", asistente de 35 años con 5+ años de experiencia

### 🎭 Características Humanizadas

- **⏱️ Delays de escritura**: Simula tiempo real de escritura humana (80 palabras por minuto)
- **📤 Indicadores de actividad**: Muestra "escribiendo..." durante las respuestas
- **🔊 Respuestas de audio**: Genera audio cuando recibe mensajes de voz
- **📝 Respuestas por párrafos**: Divide respuestas largas en múltiples mensajes

### 💾 Gestión de Estado

- **Redis**: Almacenamiento temporal de conversaciones
- **Control de flujo**: Evita respuestas duplicadas y gestiona el estado de conversación
- **Contadores**: Seguimiento de progreso de escritura humanizada

## 🛠️ Implementación Técnica

### Arquitectura

El bot está construido como un workflow de **n8n** que integra múltiples servicios:

```
Telegram Trigger → Switch (Tipo de mensaje) → Procesamiento → IA → Respuesta Humanizada
```



### Servicios Integrados

| Servicio          | Propósito                                  | API/Modelo               |
| ----------------- | ------------------------------------------ | ------------------------ |
| **OpenAI**        | Transcripción de voz y generación de audio | Whisper + TTS            |
| **Google Gemini** | Modelo principal de IA                     | gemini-2.5-flash-preview |
| **LlamaIndex**    | Procesamiento de documentos                | Cloud API                |
| **Redis**         | Almacenamiento temporal                    | Base de datos en memoria |
| **Telegram**      | Interfaz del bot                           | Bot API                  |


---

**Nota**: Este bot está diseñado para simular conversaciones humanas naturales. Todos los delays y características de "humanización" están implementados para crear una experiencia de chat más realista y agradable.
