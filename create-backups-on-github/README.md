# 🔄 Respaldos Automáticos de n8n en GitHub

## 🎥 Video Demostración

[![Respaldos Automáticos de n8n en GitHub - Video Tutorial](https://img.youtube.com/vi/Pdla4GdmOfA/maxresdefault.jpg)](https://youtu.be/Pdla4GdmOfA)

**👆 Haz clic en la imagen para ver el video tutorial completo**

## 📋 Descripción

Este proyecto proporciona dos soluciones completas para crear respaldos automáticos de tus workflows y credenciales de n8n directamente en GitHub. Mantén tus automatizaciones seguras y versionadas con sistemas de backup que se ejecutan de forma programada y detectan cambios automáticamente.

## ✨ Características Principales

### 🔧 Dos Enfoques de Backup

#### 🖥️ **backup-with-git-commands**

- **Comandos Git nativos**: Utiliza comandos Git directamente para máximo control
- **Inicialización automática**: Crea repositorios Git desde cero si no existen
- **Exportación completa**: Incluye workflows y credenciales usando `npx n8n export`
- **Detección de cambios**: Solo realiza commits cuando hay modificaciones reales

#### 🌐 **backup-with-n8n-api**

- **API de n8n**: Utiliza la API oficial de n8n para obtener workflows
- **Sincronización inteligente**: Compara contenido y solo actualiza archivos modificados
- **Programación flexible**: Trigger por horario con ejecución batch de workflows
- **Procesamiento individual**: Maneja cada workflow por separado para mejor control

### 🎯 Funcionalidades Avanzadas

- **🔍 Detección de diferencias**: Compara contenido JSON ordenado para detectar cambios reales
- **📅 Backups programados**: Ejecución automática mediante Schedule Trigger
- **🏷️ Commits descriptivos**: Mensajes automáticos con timestamp y estado del archivo
- **⚡ Procesamiento eficiente**: Solo procesa y sube archivos que han cambiado
- **📁 Organización estructurada**: Mantiene workflows organizados en carpetas

### 🔒 Gestión de Seguridad

- **🔑 Credenciales protegidas**: Manejo seguro de tokens de GitHub y API de n8n
- **📝 .gitignore automático**: Excluye archivos sensibles del repositorio
- **🛡️ Configuración de Git**: Establece usuario y email para commits

## 🛠️ Implementación Técnica

### Arquitectura

Los workflows están construidos como automatizaciones de **n8n** con dos enfoques distintos:

#### Enfoque 1: Git Commands

```
Manual Trigger → Configuración → Verificar Repo → Inicializar/Continuar → Exportar → Git Add → Detectar Cambios → Commit & Push
```

#### Enfoque 2: n8n API

```
Schedule Trigger → Obtener Workflows → Loop → Procesar Individual → Comparar → Actualizar GitHub
```

### Servicios Integrados

| Servicio            | Propósito                                | Implementación  |
| ------------------- | ---------------------------------------- | --------------- |
| **GitHub API**      | Repositorio remoto y gestión de archivos | REST API v3     |
| **n8n API**         | Obtención de workflows y credenciales    | API Local/Cloud |
| **Git Commands**    | Control de versiones local               | CLI nativo      |
| **Execute Command** | Ejecución de comandos del sistema        | Node n8n nativo |

### Configuración Requerida

#### Para backup-with-git-commands:

- **username**: Tu nombre de usuario de GitHub
- **token**: Personal Access Token de GitHub
- **repository**: Nombre del repositorio (default: "n8n-backups")
- **email**: Email para configuración de Git

#### Para backup-with-n8n-api:

- **Credencial n8n API**: Acceso a tu instancia de n8n
- **Credencial GitHub API**: Token para gestión de repositorio
- **repoOwner**: Propietario del repositorio
- **repoName**: Nombre del repositorio (default: "n8n-backup")
- **repoPath**: Ruta dentro del repo (default: "workflows/")

## 📁 Estructura del Proyecto

```
create-backups-on-github/
├── backup-with-git-commands/
│   └── backup-git.json          # Workflow con comandos Git
└── backup-with-n8n-api/
    ├── backup.json              # Workflow principal de backup
    └── process-backup.json      # Workflow de procesamiento individual
```

---

**Nota**: Estos workflows están diseñados para mantener tus automatizaciones de n8n seguras y versionadas. La detección automática de cambios asegura que solo se realicen backups cuando sea necesario, optimizando el uso de recursos y manteniendo un historial limpio en GitHub.
