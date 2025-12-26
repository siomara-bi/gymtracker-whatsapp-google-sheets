
# GymTracker — Automatización de registro de entrenamientos vía WhatsApp y Twilio

Este proyecto implementa un sistema automatizado para registrar datos de entrenamiento enviados mediante mensajes de WhatsApp.
Los mensajes son procesados a través de la API de WhatsApp Business de Twilio y enviados a un backend desarrollado en Google Apps Script, el cual estructura la información y la almacena en Google Sheets para su posterior análisis y generación de reportes.

El proyecto se encuentra actualmente en operación utilizando datos reales de entrenamiento.

---

## Arquitectura del sistema

```
WhatsApp → Twilio API → Webhook (Google Apps Script) → Google Sheets → Dashboards
```

---

## Tecnologías utilizadas

* Twilio WhatsApp Business API
* Google Apps Script (backend sin servidor)
* Google Sheets (almacenamiento y reporte de datos)
* Webhooks
* Tablas dinámicas para análisis

---

## Ejemplo de mensaje de entrada

Un mensaje típico enviado desde WhatsApp sigue la estructura:

```
26/12 prensa 20kg pierna B 10 9 8 rir 2
```

El backend procesa automáticamente el texto y extrae los siguientes campos:

| Campo            | Descripción |
| ---------------- | ----------- |
| Fecha            | 26/12       |
| Ejercicio        | Prensa      |
| Grupo muscular   | Cuádriceps  |
| Tipo de sesión   | B           |
| Número de series | 3           |
| Repeticiones     | 10-9-8      |
| RIR              | 2           |

Además, el sistema calcula indicadores como:

* Volumen por sesión
* Volumen semanal acumulado
* Distribución de carga por grupo muscular

Toda la información se registra automáticamente en Google Sheets.

---

## Dashboards y análisis

El sistema se encuentra actualmente en fase de recopilación de datos reales.
Se están desarrollando dashboards para evaluar tendencias tales como:

* Volumen semanal de entrenamiento
* Volumen por grupo muscular
* Comparación entre sesiones
* Equilibrio de carga

No se utilizan datos simulados ni artificiales.

---

## Objetivos del proyecto

* Automatizar el registro de entrenamientos, evitando la carga manual
* Reducir errores humanos hasta en un 100% en la gestión de información
* Mantener un historial estructurado de entrenamientos
* Aplicar integración de APIs y automatización en un caso real
* Facilitar análisis posteriores mediante herramientas de Business Intelligence

---

## Principales aprendizajes técnicos

* Consumo de APIs REST mediante Twilio
* Gestión de comunicación basada en Webhooks
* Desarrollo backend sin servidor en Google Apps Script
* Procesamiento y limpieza de texto
* Modelado de datos para análisis
* Construcción de dashboards en hojas de cálculo

---

## Seguridad

Este repositorio no contiene claves API, tokens de autenticación ni credenciales confidenciales.
Las credenciales de Twilio se almacenan de manera segura y se rotan cuando es necesario.
Quien desee replicar el proyecto deberá configurar sus propias credenciales.

---

## Estado actual

| Componente                           | Estado       |
| ------------------------------------ | ------------ |
| Integración WhatsApp → Twilio        | Operativa    |
| Webhook y procesamiento backend      | Operativo    |
| Registro automático en Google Sheets | Operativo    |
| Desarrollo de dashboards             | En progreso  |
| Análisis adicionales                 | Planificados |

---

## Mejoras previstas

* Generación automática de resúmenes semanales
* Exportación de dashboards analíticos a PDF
* Funcionalidades de notificación o alerta
* Seguimiento basado en RIR
* Métricas de balance de carga muscular

---

## Licencia

Este proyecto se publica bajo la licencia MIT.

---

## Nota final

Este proyecto fue creado para soportar un flujo real de registro de entrenamientos personales.
Los datos se irán acumulando progresivamente y las funcionalidades de análisis crecerán a medida que avance la actividad de entrenamiento.


