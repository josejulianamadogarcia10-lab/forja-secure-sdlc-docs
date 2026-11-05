# Documentación del proyecto Secure SDLC aplicado a FORJA

Proyecto del curso Seguridad de Sistemas Informáticos, Universidad del Valle de Guatemala (Campus Sur).
Catedrático: Ing. Chaly Monroy.

## Integrantes
- José Julián Amado García
- Jorge Luis de la Rosa Zamora
- Imri Gabriel Contreras Bautista

## Sistema analizado
FORJA: sistema web de generación y monitoreo de rutinas de entrenamiento (Laravel, Inertia/React, MySQL).
Código fuente: https://github.com/josejulianamadogarcia10-lab/forja

## Contenido del repositorio

| Carpeta | Contenido |
|---|---|
| `threat-model/` | Modelo de amenazas hecho con Microsoft Threat Modeling Tool: archivos `.tm7` de las versiones 1.0, 1.1 y 1.2 y reportes exportados |
| `sast/` | Resultados de Snyk (código y dependencias) antes y después de las correcciones |
| `dast/` | Reporte de OWASP ZAP después de las correcciones |
| `evidencias/` | Capturas de pantalla con fecha |
| `documento-final/` | Documento del proyecto en Word y PDF |

## Versiones del modelo de amenazas

| Versión | Contenido |
|---|---|
| 1.0 | Diagrama de flujo de datos y 61 amenazas generadas por la herramienta, sin atender |
| 1.1 | 12 amenazas mitigadas tras evaluar los controles existentes y las remediaciones SAST |
| 1.2 | 16 amenazas mitigadas tras el análisis DAST y la corrección de cabeceras de seguridad |

## Resumen de resultados

- **SAST (Snyk):** 31 hallazgos iniciales; 0 abiertos al final. Se actualizaron las dependencias vulnerables y se corrigió el atributo `Secure` de las cookies. Los 19 hallazgos restantes del análisis de código son falsos positivos, ignorados en Snyk con su justificación.
- **DAST (OWASP ZAP):** 0 alertas de riesgo alto. Se corrigieron las cabeceras de seguridad (CSP, X-Frame-Options, nosniff, X-Powered-By) mediante un middleware de Laravel.
- Los detalles están en el documento de la carpeta `documento-final/`.
