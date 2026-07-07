# 03 — Propuesta de infraestructura AWS

## Diagrama

Ver: `diagrams/arquitectura-aws.png`

## Flujo de tráfico

```
Usuario
  │
  ▼
Route 53 (DNS)
  │
  ▼
CloudFront (CDN + TLS)
  │
  ▼
Application Load Balancer
  │
  ▼
ECS Fargate (contenedores de la app)
  │
  ├──► RDS PostgreSQL (Multi-AZ, subnet privada)
  ├──► Secrets Manager (credenciales)
  └──► CloudWatch (logs y métricas)

ECR ──► ECS Fargate (registro de imágenes Docker)
S3  ──► backups de RDS
```

## Servicios y justificación

| Servicio | Rol | Por qué |
|----------|-----|---------|
| **ECS Fargate** | Orquestación de contenedores | Sin gestión de servidores, escala automáticamente |
| **RDS PostgreSQL** | Base de datos gestionada | Multi-AZ, backups automáticos, PITR incluidos |
| **ALB** | Load balancer | Distribuye tráfico y hace health checks |
| **ECR** | Registro de imágenes Docker | Integrado con ECS, privado y versionado |
| **Route 53** | DNS | Failover automático entre regiones |
| **CloudFront** | CDN | Reduce latencia, termina TLS en el edge |
| **ACM** | Certificados TLS | Gratis, renovación automática |
| **Secrets Manager** | Credenciales de la DB | Las contraseñas nunca van al código |
| **CloudWatch** | Logs y métricas | Alertas automáticas si algo falla |
| **S3** | Backups | Almacenamiento de snapshots con lifecycle policies |
