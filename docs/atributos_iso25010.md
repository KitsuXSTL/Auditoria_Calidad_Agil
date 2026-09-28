# Bloque 1: problemas del caso y atributos ISO/IEC 25010:2023

Atributos: adecuación funcional, eficiencia de desempeño, compatibilidad, capacidad de interacción, fiabilidad, seguridad, mantenibilidad, flexibilidad, seguridad operacional (safety).

| Problema del caso | Atributo afectado | Subcaracterística | Métrica propuesta |
|---|---|---|---|
| Defectos que llegan a producción | Fiabilidad | Ausencia de fallos (faultlessness) | Tasa de defectos escapados = defectos detectados en producción / total de defectos del sprint × 100 (meta ≤ 10 %) |
| Pruebas solo manuales | Mantenibilidad | Capacidad de ser probado (testability) | Cobertura de pruebas automatizadas sobre `src` (meta ≥ 80 %, verificada en CI) |
| Despliegues los viernes sin control | Fiabilidad | Disponibilidad y capacidad de recuperación | Tasa de fallo de cambios (meta ≤ 15 %) y tiempo medio de recuperación, MTTR (meta ≤ 1 h) |
| Datos clínicos de pacientes sin controles de seguridad verificados | Seguridad | Confidencialidad | Número de vulnerabilidades críticas o altas abiertas según el análisis de dependencias y código (meta = 0 antes de desplegar) |

## Justificación

- **Defectos escapados:** que los fallos lleguen al usuario indica que el producto no opera sin fallos en condiciones normales, lo cual corresponde a la subcaracterística *ausencia de fallos* de la fiabilidad, renombrada así en la versión 2023 de la norma (antes *madurez*).
- **Pruebas manuales:** sin pruebas automatizadas, verificar cada cambio es lento y poco repetible; esto reduce la capacidad de ser probado, una subcaracterística de la mantenibilidad.
- **Despliegues de viernes:** desplegar sin una puerta de calidad y justo antes del fin de semana aumenta la probabilidad de fallos y alarga la recuperación, porque el equipo tiene menos disponibilidad para atender incidentes.
- **Datos clínicos:** una app de citas médicas maneja información sensible de salud, por lo que la confidencialidad es un atributo crítico aunque el caso no lo mencione explícitamente.