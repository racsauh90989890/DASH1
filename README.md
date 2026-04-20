# CENGOB Bolivia — Sistema IAE v26
**Fichas Técnicas de Índice de Avance · Validación Ministerial · Dashboard Presidencial**

> Centro de Gobierno de Bolivia | Viceministerio de Coordinación y Modernización del Estado

---

## 🌐 Demo en vivo

**[→ Ver sistema en GitHub Pages](https://TU_USUARIO.github.io/TU_REPO/)**

---

## 📋 Descripción

Sistema web de seguimiento de intervenciones prioritarias del gobierno boliviano. Permite:

- **Seguimiento por ministerio** — fichas técnicas con etapas, estados y validación
- **Dashboard Ejecutivo** — visión consolidada por eje estratégico con gráficos
- **Dashboard Presidencial** — monitoreo de las 4 leyes prioritarias con:
  - Semáforo de etapas (avance vs. total)
  - Gráfico Gantt de línea programada vs. avance real
  - Índice de velocidad de ejecución
  - Riesgo de incumplimiento de plazo (proyección al cierre)
  - Dependencias interministeriales
  - Cuellos de botella identificados
  - Quick Wins (etapas de alto impacto / bajo esfuerzo)

---

## 🚀 Publicar en GitHub Pages

### Opción A — Repositorio directo (más simple)

```bash
# 1. Crear repo en GitHub (ej: cengob-iae)
# 2. Clonar y agregar el archivo
git clone https://github.com/TU_USUARIO/cengob-iae.git
cd cengob-iae
cp /ruta/a/index.html .
cp /ruta/a/README.md .

# 3. Subir
git add .
git commit -m "feat: CENGOB IAE v26 — Dashboard Presidencial"
git push origin main

# 4. Activar GitHub Pages
# → Settings → Pages → Source: Deploy from branch → main → / (root) → Save
# URL: https://TU_USUARIO.github.io/cengob-iae/
```

### Opción B — GitHub CLI (gh)

```bash
# Instalar gh si no lo tienes: https://cli.github.com/
gh auth login
gh repo create cengob-iae --public --description "CENGOB Bolivia IAE v26"
git init && git add . && git commit -m "feat: CENGOB IAE v26"
git remote add origin https://github.com/TU_USUARIO/cengob-iae.git
git push -u origin main
gh api repos/TU_USUARIO/cengob-iae/pages -X POST -f source='{"branch":"main","path":"/"}'
```

### Opción C — Drag & drop (sin comandos)

1. Ir a **github.com → New repository**
2. Nombre: `cengob-iae` · Visibility: **Public**
3. Click **"uploading an existing file"**
4. Arrastrar `index.html` y `README.md`
5. Commit: `"feat: CENGOB IAE v26"`
6. **Settings → Pages → Branch: main → Save**

---

## 🗂️ Estructura del repositorio

```
cengob-iae/
├── index.html        ← Sistema completo (autocontenido)
└── README.md         ← Esta documentación
```

El sistema es **100% autocontenido** en un único HTML. No requiere servidor, base de datos ni build process.

---

## 📦 Dependencias externas (CDN)

Todas se cargan desde CDN público — no requieren instalación:

| Librería | Versión | Uso |
|---|---|---|
| Bootstrap | 5.3.3 | Layout responsivo |
| Chart.js | 4.4.1 | Gráficos y visualizaciones |
| SheetJS (xlsx) | 0.18.5 | Exportar/importar Excel |
| Google Fonts | — | Barlow / Barlow Condensed |

---

## 💾 Persistencia de datos

El sistema guarda el estado (etapas completadas, validaciones, notas) en **localStorage** del navegador. Los datos persisten entre sesiones en el mismo dispositivo/navegador.

Para compartir el estado entre usuarios, usar la función **Exportar → JSON** e **Importar → JSON**.

---

## 🏛️ Intervenciones presidenciales monitoreadas

| ID | Ley | Ministerio |
|---|---|---|
| i.1 | Ley de Hidrocarburos | Min. Hidrocarburos y Energías |
| i.25 | Nueva Ley de Inversiones | Min. Planificación |
| i.26 | Nueva Ley de Energía | Min. Hidrocarburos y Energías |
| i.5a | Ley de Minería – ATEs→CAM | Min. Minería y Metalurgia |

---

## 📱 Responsividad

Compatible con escritorio, tablet y móvil. El panel lateral se convierte en drawer deslizante en pantallas < 992px.

---

## 🔒 Notas de seguridad

- No se envía ningún dato a servidores externos
- No hay tracking ni analytics
- Todos los datos se almacenan localmente en el navegador del usuario

---

*CENGOB Bolivia · Viceministerio de Coordinación y Modernización del Estado · Gestión 2026*
