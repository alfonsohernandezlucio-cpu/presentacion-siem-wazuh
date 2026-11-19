# Producto final · Operación del SIEM (Wazuh)

Evidencias del proyecto **implementación y operación de un SIEM con Wazuh**, organizadas por fase: de la instalación del servidor a la detección y el análisis de incidentes.

- **Estudiante:** Alfonso Hernández Lucio
- **Asignatura:** Tecnología para la Gestión de la Información y Eventos de Seguridad
- **Docente:** Mtro. Gustavo Valencia Beltran
- Universidad del País Innova · Tampico, Tamps. · Noviembre de 2026

## Contenido del repositorio

| Carpeta | Entrega | Qué contiene | Relación con el SIEM |
|---|---|---|---|
| [`fase-1/`](fase-1/) | Fase 1 · 30/10/2026 | Reporte de **construcción y arquitectura del SIEM**: entorno de laboratorio, instalación de Wazuh 4.14 All-in-One en Ubuntu Server 24.04 (VMware), acceso a la consola web, diagrama de arquitectura y flujo de la información. | **Implementación:** deja instalados el Manager, el Indexer y el Dashboard, que son la base sobre la que opera todo lo demás. |
| [`fase-2/`](fase-2/) | Fase 2 · 06/11/2026 | Reporte de **integración de infraestructura y gestión de logs**: instalación de los agentes en Windows 11 y Ubuntu Desktop, evidencia de conexión, eventos generados (inicio de sesión fallido, creación de usuario y escalada de privilegios), ejemplos de logs, integridad, retención y trazabilidad, y diagrama actualizado. | **Recolección:** el SIEM empieza a recibir eventos reales de dos fuentes, y se demuestra que los registros son íntegros, se conservan y se pueden rastrear. |
| [`fase-3/`](fase-3/) | Fase 3 · 13/11/2026 | Reporte de **correlación, detección y análisis de eventos**: tres escenarios controlados, alertas obtenidas, las 14 reglas de detección, relación entre eventos, análisis de casos, patrones, un falso positivo y el apoyo de inteligencia artificial contrastado con Wazuh. | **Detección y análisis:** el SIEM convierte los eventos en alertas priorizadas y, al correlacionarlas, permite interpretar el comportamiento. |
| [`final/`](final/) | Producto final | **Presentación ejecutiva** en PowerPoint que integra las tres fases: evolución del proyecto, arquitectura, gestión de logs, reglas, métricas interpretadas, hallazgos con decisión recomendada y conclusiones. | **Operación y resultados:** resume cómo opera el SIEM y qué decisiones permite tomar. |

**Versión web interactiva de la presentación** (mismo contenido que el PPTX, en la raíz del repositorio como `index.html`): https://alfonsohernandezlucio-cpu.github.io/presentacion-siem-wazuh/
(Controles: ← → para avanzar, F para pantalla completa y clic en una captura para ampliarla).

## Resumen del laboratorio

| Componente | Detalle |
|---|---|
| Servidor Wazuh | Ubuntu Server 24.04 en VMware · 192.168.46.137 · 4 vCPU · 8 GB RAM · 200 GB SSD · Wazuh 4.14 (Manager, Indexer y Dashboard) |
| Agente 1 | Compu_desktop (ID 001) · Ubuntu Desktop 26.04.1 LTS · 192.168.46.138 · fuentes: PAM, sudo y SCA |
| Agente 2 | PcWindows11 (ID 002) · Windows 11 Pro · 192.168.46.139 · fuentes: canal Security (también Application y System) y SCA |
| Escenarios | 1) Intentos fallidos de autenticación · 2) Cuenta nueva y escalada de privilegios · 3) Ejecución de procesos |
| Detección | 14 reglas distintas en 4 niveles de severidad (3, 5, 8 y 12); la alerta de mayor prioridad fue la 60154 (Administrators Group Changed, nivel 12) |

Todas las pruebas se realizaron en un entorno de laboratorio aislado y autorizado.
