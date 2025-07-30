# 🤖 WhatsApp Bot con Transferencia Humana

## 🎥 Video Demostración

[![WhatsApp Bot con Transferencia Humana - Video Tutorial](https://img.youtube.com/vi/xKtVkRx3-5I/maxresdefault.jpg)](https://youtu.be/xKtVkRx3-5I)

**👆 Haz clic en la imagen para ver el video tutorial completo**

## 📋 Descripción

Este es un bot inteligente de WhatsApp que combina el poder de la inteligencia artificial con la capacidad de transferir conversaciones a operadores humanos cuando es necesario. El bot utiliza Evolution API v2.2.3 para procesar múltiples tipos de contenido y ofrece un sistema fluido de handoff (transferencia) entre IA y agentes humanos.

## ✨ Características Principales

### 🎯 Procesamiento Multimodal

- **📝 Mensajes de texto**: Procesamiento directo de consultas en español
- **🎙️ Mensajes de audio**: Transcripción y análisis automático
- **🖼️ Imágenes**: Análisis visual de contenido
- **📄 Documentos**: Extracción y procesamiento de texto
- **🎬 Videos**: Procesamiento de contenido multimedia

## 🛠️ Implementación Técnica

### Arquitectura

El workflow está construido en **n8n** con integración completa de Evolution API:

```
Webhook WhatsApp → Switch (Tipo de mensaje) → Verificación Estado → IA/Humano → Respuesta
```

### Sistema de Handoff

```
Usuario → Bot IA → [Trigger Pausa] → Redis → Operador Humano → [Reanudar] → Bot IA
```

### Servicios Integrados

| Servicio          | Propósito                  | API/Tecnología           |
| ----------------- | -------------------------- | ------------------------ |
| **Evolution API** | Interfaz WhatsApp          | v2.2.3                   |
| **Google Gemini** | Motor principal de IA      | Gemini 2.5 Flash         |
| **Redis**         | Gestión de estado y pausas | Base de datos en memoria |
| **n8n**           | Orquestación del workflow  | Automation platform      |

### Tipos de Mensaje Soportados

- `conversation` - Mensajes de texto
- `audioMessage` - Mensajes de voz
- `imageMessage` - Imágenes
- `documentMessage` - Documentos
- `videoMessage` - Videos

---

**Nota**: Este sistema está diseñado para brindar soporte automatizado inteligente con la capacidad de escalación humana cuando sea necesario, garantizando una experiencia de usuario fluida y profesional.
