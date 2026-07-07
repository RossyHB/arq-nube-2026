# 🎓 Trabajo Práctico Final — Arquitectura de Nube 2026

El TP es **individual**. Cada alumna crea su propia carpeta dentro de `Entregables/` con su `nombre-apellido` y sube su entrega en una rama propia.

El paso a paso para clonar el repo, crear tu rama y hacer el push está en el [README principal](../README.md).

---

## Sobre el uso de IA

Podés usar herramientas de IA (ChatGPT, Claude, Copilot, etc.) para ayudarte con el código, los diagramas o la redacción.

**Lo que sí o sí tiene que ser tuyo:**
- La idea de la app y el problema que resuelve
- La selección de servicios AWS
- Las justificaciones de cada decisión

Necesitamos saber que entendiste el material del curso, no que lo entendió la IA por vos. Si la justificación suena genérica o copiada, lo vamos a notar.

---

## 🗂️ Estructura de tu carpeta

Antes de empezar, mirá la carpeta [`ejemplo/`](./ejemplo/) — es una entrega completa de referencia.

```
Entregables/
├── README.md                        ← este archivo
├── ejemplo/                         ← entrega de referencia completa (leerla antes de empezar)
└── tu-nombre-apellido/              ← la creás vos, con tu nombre real
    ├── docs/
    │   ├── 01-descripcion.md        ← qué es la app y para quién
    │   ├── 02-arquitectura-local.md ← cómo corre localmente con Docker
    │   ├── 03-arquitectura-aws.md   ← propuesta de infraestructura en AWS
    │   ├── 04-well-architected.md   ← pilares que abordás y cómo
    │   ├── 05-costos.md             ← estimación y decisiones de costo
    │   └── 06-disaster-recovery.md  ← plan ante desastres
    ├── app/
    │   ├── Dockerfile
    │   ├── docker-compose.yml
    │   └── (código de la app)
    ├── diagrams/
    │   ├── arquitectura-local.png
    │   └── arquitectura-aws.png
    └── evidence/
        ├── app-running.png
        └── linkedin-post.png
```

---

## 📦 Entregables detallados

### `docs/01-descripcion.md` — La app

**La app no necesita ser innovadora.** Puede ser una réplica de algo existente o incluso solo una sección de una app conocida. Por ejemplo:

- Un chat entre usuarios
- Un catálogo de productos
- Una plataforma de streaming (lista de películas + reproductor)
- Un juego online simple
- Una intranet para compartir archivos entre puestos de trabajo
- Un sistema de turnos, reservas o pedidos

Lo importante es que elijas algo que te permita pensar como arquitecta.

**Qué incluir:**
- ¿Qué hace la app?
- ¿Por qué la elegiste?
- ¿Quiénes son los usuarios? (empleados internos, clientes, público general, etc.)
- Si usás base de datos: qué tipo elegiste y por qué. Si no necesitás base de datos, explicá por qué no.

---

### `docs/02-arquitectura-local.md` — Arquitectura local

- Cómo corre la app con Docker (servicios, puertos, volúmenes)
- Instrucciones para levantarla: `docker compose up`
- Diagrama simple de cómo se conectan los contenedores (puede ser ASCII o una imagen)

---

### `docs/03-arquitectura-aws.md` — Propuesta en AWS

- Qué servicios de AWS usarías para desplegar tu solución
- Justificación de cada servicio — **esta parte tiene que ser tuya**
- El diagrama de arquitectura va en `diagrams/arquitectura-aws.png`

> No es necesario desplegar nada en AWS. Alcanza con el diseño y la justificación.

---

### `docs/04-well-architected.md` — Well-Architected Framework

No es obligatorio cubrir los 6 pilares. Identificá **cuáles aplican a tu arquitectura** y explicá cómo los estás abordando.

| Pilar | Preguntas para pensar |
|-------|----------------------|
| **Excelencia Operativa** | ¿Cómo monitoreás? ¿Cómo desplegás cambios? |
| **Seguridad** | ¿Cómo protegés datos y secretos? ¿Quién puede acceder a qué? |
| **Fiabilidad** | ¿Qué pasa si un componente falla? ¿Hay redundancia? |
| **Eficiencia de Rendimiento** | ¿Cómo escala la solución ante picos de uso? |
| **Optimización de Costos** | ¿Cómo evitás gastos innecesarios? |
| **Sostenibilidad** | ¿Minimizás recursos ociosos? |

Para cada pilar que incluyas: describí qué decisión tomaste y qué mejorarías con más tiempo o presupuesto.

---

### `docs/05-costos.md` — Estimación de costos

- Servicios más costosos de tu arquitectura
- Decisiones que tomaste para optimizar costos
- Qué evitarías o simplificarías en una primera versión

Podés usar la [AWS Pricing Calculator](https://calculator.aws/) para estimar.

---

### `docs/06-disaster-recovery.md` — Pensamiento arquitectónico y DR

Esta sección es la más importante del TP. Acá demostrás que pensaste como arquitecta.

**Pensá en tu app desde estas perspectivas:**

**Usuarios y disponibilidad**
- ¿Quiénes usan la app? ¿Empleados internos, clientes, público general?
- ¿En qué horarios la usan? → ¿Cuándo podés hacer mantenimiento sin impacto?
- ¿Qué pasa si la app cae en horario pico? ¿Cuál es el impacto real?

**Riesgos y reglas**
- ¿Qué reglas o regulaciones afectan a tu app? (privacidad de datos, compliance, etc.)
- ¿Qué riesgos técnicos o de negocio identificás?

**Plan de recuperación**
- Escenarios de falla contemplados (ej: caída de AZ, corrupción de datos, error humano)
- **RTO** (Recovery Time Objective): ¿cuánto tiempo podés estar caída?
- **RPO** (Recovery Point Objective): ¿cuántos datos podés perder?
- Estrategia de DR: Backup & Restore / Pilot Light / Warm Standby / Multi-Site
- ¿Cómo harías backups?

---

### `app/` — App dockerizada

La app debe tener al menos **1 o 2 páginas funcionales**. No hace falta que sea compleja.

```
app/
├── Dockerfile
├── docker-compose.yml
└── (código fuente — cualquier lenguaje)
```

---

### `diagrams/` — Diagramas

| Archivo | Contenido |
|---------|-----------|
| `arquitectura-local.png` | Cómo se conectan los contenedores localmente |
| `arquitectura-aws.png` | Infraestructura propuesta en AWS |

Formatos aceptados: `.png`, `.jpg`, `.pdf`

Herramientas recomendadas:
- [draw.io / diagrams.net](https://app.diagrams.net/) — gratis, online
- [Lucidchart](https://lucidchart.com/) — gratis con cuenta educativa
- Ambas tienen los íconos oficiales de AWS: [AWS Architecture Icons](https://aws.amazon.com/architecture/icons/)

---

### `evidence/` — Evidencias

| Archivo | Contenido |
|---------|-----------|
| `app-running.png` | Screenshot de la app corriendo con `docker compose up` |
| `linkedin-post.png` | Screenshot del post publicado en LinkedIn |

**Post de LinkedIn sugerido:**

> Terminé mi proyecto final del curso Arquitectura en la Nube 2026.  
> Arranqué con una app dockerizada corriendo localmente y diseñé una propuesta de infraestructura AWS aplicando Well-Architected principles, estimación de costos y plan de disaster recovery.  
> Esto me ayudó a entender cómo una app local puede evolucionar hacia una solución cloud escalable, segura y confiable.  
> #AWS #CloudArchitecture #WomenInCloud #WICBuenosAires

---

## ✅ Criterios de evaluación

| Criterio | Peso |
|----------|------|
| App dockerizada funcionando (con screenshot) | 20% |
| Diagrama de infraestructura AWS | 20% |
| Evaluación Well-Architected (pilares aplicables) | 20% |
| Pensamiento arquitectónico y plan de DR | 25% |
| Estimación y decisiones de costos | 10% |
| Post de LinkedIn | 5% |

---

## 📎 Recursos

- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [draw.io / diagrams.net](https://app.diagrams.net/)
- [Lucidchart](https://lucidchart.com/)
- [AWS Architecture Icons](https://aws.amazon.com/architecture/icons/)
- [AWS Pricing Calculator](https://calculator.aws/)
- [Docker Docs](https://docs.docker.com/)

---

## ❓ Dudas

Abrir un **Issue** en el repositorio o escribir al canal del curso.

---

> **AWS Women in Cloud — Buenos Aires | Clase 2026**
