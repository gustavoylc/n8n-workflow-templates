# 🔄 Migración de Servidor n8n

## 🎥 Video Demostración

[![Migración de Servidor n8n - Video Tutorial](https://img.youtube.com/vi/oJyWpDfHgXc/maxresdefault.jpg)](https://youtu.be/oJyWpDfHgXc)

**👆 Haz clic en la imagen para ver el video tutorial completo**

## 📋 Descripción

Este workflow automatizado permite migrar completamente workflows y tags de un servidor n8n a otro servidor n8n de manera eficiente y segura. La solución está diseñada para transferir no solo los workflows activos, sino también mantener la organización mediante tags, creando copias exactas en el servidor de destino.

## ✨ Características Principales

### 🏷️ Migración Completa de Tags

- **📥 Extracción de tags**: Obtiene todos los tags del servidor origen
- **📤 Creación en destino**: Crea automáticamente los tags en el servidor destino
- **🔄 Manejo de duplicados**: Evita errores al intentar crear tags que ya existen
- **🔗 Preservación de relaciones**: Mantiene las asociaciones entre workflows y tags

### 📋 Migración de Workflows

- **🎯 Filtrado inteligente**: Solo migra workflows activos (no archivados)
- **📝 Nomenclatura automática**: Añade sufijo "-copy" para evitar conflictos
- **⚙️ Preservación de configuración**: Mantiene nodes, conexiones y configuraciones
- **🏷️ Asignación de tags**: Restaura automáticamente los tags correspondientes

### 🔧 Configuración Flexible

- **🔑 API Keys separadas**: Configuración independiente para servidor origen y destino
- **🌐 URLs configurables**: Soporte para diferentes dominios y puertos
- **⚡ Procesamiento por lotes**: Manejo eficiente de múltiples workflows
- **🛡️ Manejo de errores**: Continúa la migración aunque algunos elementos fallen

### 🔄 Flujo de Trabajo Automatizado

- **🚀 Ejecución manual**: Inicia la migración con un solo clic
- **📊 Procesamiento secuencial**: Migra tags primero, luego workflows
- **🔍 Validación de estado**: Verifica que los workflows no estén archivados
- **✅ Confirmación de éxito**: Proceso completo de verificación

## 🛠️ Implementación Técnica

### Arquitectura

El workflow está construido como una solución completa de **n8n** que integra múltiples pasos:

```
Manual Trigger → Configuración → Migración de Tags → Obtención de Workflows → Migración de Workflows → Asignación de Tags
```

### Flujo de Migración

1. **Configuración inicial**: Define API keys y URLs de servidores origen y destino
2. **Migración de tags**: Extrae y crea todos los tags en el destino
3. **Obtención de workflows**: Recupera todos los workflows del servidor origen
4. **Filtrado**: Excluye workflows archivados de la migración
5. **Creación de workflows**: Genera copias en el servidor destino
6. **Asignación de tags**: Vincula los tags correspondientes a cada workflow
