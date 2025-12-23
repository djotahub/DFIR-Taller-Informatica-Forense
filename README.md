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

### [Módulo 1: Fundamentos y Preservación de Evidencia

_La base de la investigación. Cómo aseguramos la escena y los datos._

- Protocolos de Cadena de Custodia y RFC 3227.
    
- Metodología de Adquisición Forense: Imágenes de disco y volcados de memoria.
    
- Herramientas de preservación: **KAPE** y **FTK Imager**.
    

### [Módulo 2: Memory Forensics

_Análisis de lo volátil. Cazando procesos y conexiones en RAM._

- Uso de **Volatility 3** para inspección de memoria.
    
- Identificación de procesos maliciosos (`pslist`, `pstree`) e inyecciones de código.
    
- Análisis de conexiones de red (`netscan`) y sockets residuales.
    

### [Módulo 3: Disk Artifacts & System Internals 
_Análisis del rastro persistente en el sistema de archivos._

- Estructuras NTFS: Análisis de la **$MFT**.
    
- Artefactos de Registro: Hives SYSTEM, SOFTWARE y NTUSER.DAT.
    
- Evidencia de Ejecución: Prefetch, ShimCache y AmCache para reconstruir la línea de tiempo de ejecución.
    

### [Módulo 4: Browser & Email Forensics

_Perfilamiento digital y vectores de entrada._

- **Browser Forensics:** Análisis de bases de datos **SQLite** (`places.sqlite`, `History`) para reconstruir hábitos e intención (`search?q=`).
    
- **Email Forensics:** Trazabilidad de cabeceras SMTP (Headers) y detección de Spoofing (SPF/DKIM).
    
- Correlación de actividad de usuario con el incidente.
    



---

### [Módulo 5: Mobile Incident Response & Live Triage (Clase Extendida)](https://www.google.com/search?q=./Modulo_05_Mobile_IR)

_Investigación en dispositivos móviles corporativos y BYOD. Rompiendo el Sandbox._

- **Arquitectura Android:** Kernel, Sandbox de aplicaciones y gestión de permisos (`/data`).
    
- **Adquisición Táctica (Live Triage):**
    
    - Uso de **ADB (Android Debug Bridge)** para reconocimiento en vivo.
        
    - Control y proyección de pantalla con **Scrcpy**.
        
    - Extracción de paquetería y logs sin acceso root total.
        
- **Threat Hunting en Mensajería (WhatsApp):**
    
    - Extracción y descifrado de bases de datos `msgstore.db`.
        
    - **SQL Hunting:** Queries para detectar fuga de información sensible, malware compartido y exfiltración de datos.
        

### [Módulo 6: Reporting, IOCs & Containment](https://www.google.com/search?q=./Modulo_06_Reporte)

_Del análisis forense a la respuesta defensiva._

- **Generación de Inteligencia:** Conversión de evidencia (hallada en RAM/Disco/Móvil) en **IoCs** (Indicadores de Compromiso) accionables.
    
- **Estrategias de Contención:** Medidas de aislamiento y bloqueo basadas en los hallazgos del peritaje.
    
- **El Informe Pericial y de Incidente:**
    
    - Estructura técnica vs. ejecutiva.
        
    - Presentación de la línea de tiempo del ataque.
        
    - Simulacro de defensa de hallazgos.

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
