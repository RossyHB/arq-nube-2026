# Arquitectura de Computación en la Nube 2026

Repositorio oficial del curso de arquitectura de computación en la nube — **AWS Women in Cloud Buenos Aires, Clase 2026**.

---

## 📁 Contenido del repositorio

| Carpeta | Descripción |
|---------|-------------|
| [`Entregables/`](./Entregables/README.md) | Trabajo Práctico Final — instrucciones y carpetas de entrega individuales |

---

## 🎓 Requisitos para graduarse

Para completar el curso necesitás cumplir **los dos requisitos**:

1. **Examen en AWS Academy** — Rendir y aprobar la evaluación **"Academy Cloud Architecting"** dentro de la plataforma AWS Academy
2. **Entregar el TP Final** — Subir tu entrega a este repositorio siguiendo los pasos de abajo

> ¿Dudas o preguntas? Escribí al grupo de **WhatsApp** del curso.

---

## 🚀 Cómo entregar tu TP

### Paso 1 — Hacer el fork del repositorio (solo una vez, desde el navegador)

Ir a [github.com/aws-wic-ba/arq-nube-2026](https://github.com/aws-wic-ba/arq-nube-2026) y hacer clic en **Fork** → **Create fork**

### Paso 2 — Clonar tu fork en la computadora

Reemplazá `tu-usuario` con tu usuario de GitHub:

```bash
git clone https://github.com/tu-usuario/arq-nube-2026.git
cd arq-nube-2026
```

### Paso 3 — Agregar el repositorio original como upstream

```bash
git remote add upstream https://github.com/aws-wic-ba/arq-nube-2026.git
```

### Paso 4 — Crear tu rama de trabajo

Reemplazá `nombre-apellido` con tu nombre y apellido en minúsculas y sin espacios (ej: `maria-gomez`):

```bash
git checkout -b entrega/nombre-apellido
```

### Paso 5 — Crear tu carpeta dentro de Entregables

```bash
mkdir -p Entregables/nombre-apellido/docs
mkdir -p Entregables/nombre-apellido/app
mkdir -p Entregables/nombre-apellido/diagrams
mkdir -p Entregables/nombre-apellido/evidence
```

### Paso 6 — Completar los archivos

Completá cada archivo en `docs/` siguiendo las instrucciones de [`Entregables/README.md`](./Entregables/README.md). Podés ver la carpeta [`Entregables/ejemplo/`](./Entregables/ejemplo/) como referencia.

### Paso 7 — Commitear los cambios

```bash
git add Entregables/nombre-apellido/
git commit -m "TP Final: nombre-apellido"
```

### Paso 8 — Subir tu rama a tu fork

```bash
git push origin entrega/nombre-apellido
```

### Paso 9 — Abrir un Pull Request

Ir a [github.com/aws-wic-ba/arq-nube-2026](https://github.com/aws-wic-ba/arq-nube-2026), hacer clic en **Compare & pull request** e indicar:
- Tu nombre completo
- Nombre y descripción breve de tu app

> **¿Necesitás sincronizar con los últimos cambios del repo original?**
> ```bash
> git fetch upstream
> git merge upstream/main
> ```

---

> **AWS Women in Cloud — Buenos Aires | Clase 2026**
