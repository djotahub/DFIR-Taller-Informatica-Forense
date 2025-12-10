![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Framework: MITRE ATT&CK](https://img.shields.io/badge/Framework-MITRE%20ATT&CK-red.svg)
![Standard: NIST SP 800--61](https://img.shields.io/badge/Standard-NIST%20SP%20800--61-blueviolet.svg)
![Enfoque: DFIR](https://img.shields.io/badge/Enfoque-DFIR-success.svg)
![Nivel: Intermedio](https://img.shields.io/badge/Nivel-Intermedio-orange.svg)

# Taller de Informática Forense y Respuesta a Incidentes (DFIR)

Repositorio oficial de recursos, documentación y laboratorios prácticos para el **Taller de Informática Forense y Respuesta a Incidentes**. Este espacio centraliza la evidencia digital y las guías técnicas necesarias para el desarrollo de las sesiones.

> **Nota:** Este material complementa las sesiones teóricas y prácticas. Se recomienda clonar el repositorio para tener acceso local a las herramientas y scripts.

## Objetivos del Entrenamiento

El objetivo de este taller es desarrollar capacidades analíticas para la identificación, preservación, análisis y correlación de evidencia digital en entornos comprometidos.

El participante aprenderá a:

* **[IDENTIFICAR]** y preservar evidencia volátil y persistente siguiendo protocolos estándar.

* **[ANALIZAR]** memoria RAM para detectar malware, hooks y técnicas *fileless*.

* **[EXAMINAR]** artefactos del sistema de archivos ($MFT) y Registro de Windows.

* **[CORRELACIONAR]** logs de eventos para reconstruir la línea de tiempo del ataque.

* **[GENERAR]** inteligencia de amenazas y reportes forenses técnicos.

## Estructura del Contenido

El repositorio está organizado según el cronograma del taller:

### [Módulo 1: Fundamentos y Adquisición](./Modulo_01_Fundamentos)

* Protocolos de Cadena de Custodia.
* Metodología de Preservación de Evidencia (RFC 3227).
* Herramientas de Triage y Adquisición (KAPE, FTK Imager).

### [Módulo 2: Memory Forensics](./Modulo_02_Memoria)

* Análisis de Memoria RAM con Volatility 3.
* Identificación de procesos maliciosos (`pslist`, `pstree`) y conexiones de red (`netscan`).
* Extracción de payloads y análisis de inyección de código.

### [Módulo 3: Disk Artifacts & Carving](./Modulo_03_Disco)

* Análisis de la Master File Table (`$MFT`).
* Artefactos de Registro (System, Software, NTUSER.DAT).
* Evidencia de Ejecución (Prefetch, ShimCache, AmCache).
* Recuperación de datos borrados (File Carving).

### [Módulo 4: Log Analysis & Hunting](./Modulo_04_Logs)

* Parsing de Event Logs de Windows (.evtx).
* Detección de Movimiento Lateral y Escalada de Privilegios.
* Uso de Sysmon para hunting avanzado.

### [Módulo 5: Timeline Analysis](./Modulo_05_Timeline)

* Creación de Super Timelines.
* Correlación de artefactos dispares.
* Mapeo de TTPs al framework MITRE ATT&CK.

### [Módulo 6: Reporte y Cierre](./Modulo_06_Reporte)

* Estrategias de Contención y Erradicación.
* Estructura de Reportes Forenses Ejecutivos y Técnicos.
* Simulacro final (Mini-CTF).

## ⚙️Requisitos del Laboratorio

Para realizar las prácticas, se requiere un entorno virtualizado aislado.

* **Virtualización:** VirtualBox o VMware Workstation/Player.
* **Máquina Virtual de Análisis:**
  * Recomendado: **FlareVM** (Windows 10) o **SIFT Workstation** (Linux).
  * Alternativa: Windows 10 estándar con herramientas instaladas manualmente.
* **Recursos:** Mínimo 8GB de RAM y 50GB de espacio en disco libre.

## Herramientas Principales

Durante el taller utilizaremos software estándar de la industria:

| Herramienta | Propósito |
| :--- | :--- |
| **KAPE** | Triage y recolección rápida de artefactos. |
| **FTK Imager** | Adquisición de imágenes de disco y memoria. |
| **Volatility 3** | Framework de análisis de memoria RAM. |
| **Eric Zimmerman's Tools** | Suite de análisis de artefactos de Windows (Registry Explorer, PECmd). |
| **Timeline Explorer** | Visualización y filtrado de CSVs masivos. |
| **Scalpel / PhotoRec** | Recuperación de archivos (File Carving). |

## ⚠️ Disclaimer

Este material ha sido desarrollado con fines **educativos y profesionales**. Los datasets de evidencia pueden contener simulación de malware real.

```bash
# ADVERTENCIA DE SEGURIDAD
NO ejecutar los binarios extraídos en sistemas de producción.
Realizar todos los análisis DENTRO de las Máquinas Virtuales designadas.
```

by __QB1t

© 2025 - DFIR Training Resources. Todos los derechos reservados.
