# 📋 Planificación Semanal de Desarrollos
**ARTICA Creative Studio — Departamento de Tecnología**

Herramienta interna para planificar, registrar y reportar los desarrollos de software semanales del equipo. Genera un resumen visual interactivo y lo exporta en PDF listo para presentar a gerencia.

---

## ✨ Características

### 🗂 Desarrollos en curso
- Agrega múltiples proyectos/desarrollos de la semana
- Barra de progreso + slider para actualizar el avance (0–100%)
- Estado configurable: `En progreso` · `Completado` · `Pausado` · `Bloqueado`
- Cada desarrollo tiene **dos secciones de actividades independientes**:
  - ✅ **Actividades realizadas** — lo que se completó en la semana
  - ⚠️ **Implementaciones / mejoras restantes** — lo que queda pendiente

### ⚡ Carga rápida de actividades
- **Una por una:** escribe en el campo inferior y pulsa `↵` para agregar
- **Lista completa:** botón "Pegar lista" → pega texto con formato `- ítem` y se crean todos de golpe
- `Ctrl + Enter` confirma la lista desde el textarea
- `Backspace` en campo vacío elimina el ítem y sube el foco
- Soporte de prefijos: `-` `*` `•` `·` o líneas sin prefijo

### 📅 Semana de trabajo
- Selector de fechas de inicio y fin de la semana
- Calendario visual con los días laborales resaltando el día actual

### 📝 Secciones de texto libre
- **Resumen & Objetivos de la Semana** — síntesis ejecutiva para gerencia
- **Notas & Decisiones** — acuerdos del equipo, reuniones, contexto

### 🚨 Pendientes & Riesgos
- Lista de pendientes/riesgos con prioridad: `Alta` · `Media` · `Baja`
- Contador de ítems en el encabezado
- Código de color por prioridad (rojo / ámbar / verde)

### 📄 Exportación a PDF
- Genera un documento PDF profesional con:
  - Encabezado con logo y fechas
  - Bloque por cada desarrollo con estado y actividades de ambas secciones
  - Calendario de la semana
  - Resumen ejecutivo, notas y pendientes
- Nombre del archivo automático: `Planificacion-ARTICA_YYYY-MM-DD_YYYY-MM-DD.pdf`

### 💾 Persistencia automática
- Los datos se guardan automáticamente en `localStorage` al escribir
- Botón **Guardar** para confirmación manual con toast de notificación
- Los datos se restauran al recargar la página

---

## 🚀 Uso

El proyecto es un **único archivo HTML** sin dependencias locales ni proceso de build.

```bash
# Opción 1 — Abrir directamente en el navegador
Doble click en index.html

# Opción 2 — Servir con un servidor local (recomendado)
npx serve .
# o
python -m http.server 8080
```

> ⚠️ Abrir directamente como `file://` funciona, pero algunos navegadores pueden bloquear fuentes o el export PDF. Se recomienda usar un servidor local.

---

## 📁 Estructura del proyecto

```
planificacion-desarrollos/
├── index.html          # App completa (HTML + CSS + JS en un solo archivo)
├── README.md           # Este archivo
└── img/
    ├── logo-artica-blanco.png   # Logo del header y PDF
    └── icon.avif                # Favicon
```

---

## 🛠 Stack técnico

| Tecnología | Uso |
|---|---|
| **HTML5 / CSS3 / JS vanilla** | App completa sin frameworks |
| **CSS Grid & Flexbox** | Layout responsive |
| **localStorage** | Persistencia de datos en el navegador |
| [**html2pdf.js**](https://github.com/eKoopmans/html2pdf.js) `v0.10.1` | Generación del PDF desde el DOM |
| [**Google Fonts — Poppins**](https://fonts.google.com/specimen/Poppins) | Tipografía |

---

## 📱 Responsive

Diseño adaptado a todos los tamaños de pantalla:

| Breakpoint | Comportamiento |
|---|---|
| `> 900px` | Layout completo de escritorio |
| `≤ 900px` | Sección de desarrollos ocupa ancho completo |
| `≤ 760px` | Header en 2 filas · dev-summary en 2 filas · grids apilados |
| `≤ 480px` | Botones apilados · prevención de zoom en iOS · días de semana 2 col |
| `≤ 360px` | Modo ultra compacto para pantallas pequeñas |

---

## 💡 Flujo de trabajo sugerido

1. **Lunes** — abrir la app, configurar las fechas de la semana y agregar los desarrollos activos
2. **Durante la semana** — ir añadiendo actividades realizadas a medida que se completan
3. **Viernes** — completar el resumen ejecutivo, notas y pendientes
4. **Exportar PDF** — enviar el reporte semanal a gerencia

---

## 🗃 Modelo de datos (localStorage)

```json
{
  "devs": [
    {
      "name": "Articademy.us",
      "pct": "75",
      "status": "En progreso",
      "actividades": ["Implementación módulo login", "Corrección bug de registro"],
      "pendientes":  ["Migrar a React 19", "Notificaciones push"]
    }
  ],
  "pendings": [
    { "text": "Definir arquitectura del nuevo módulo", "prio": "alta" }
  ],
  "summary":   "Síntesis ejecutiva de la semana...",
  "notes":     "Decisiones tomadas en la reunión del martes...",
  "dept":      "Departamento de Tecnología",
  "dateStart": "2026-05-18",
  "dateEnd":   "2026-05-23"
}
```

---

## ✏️ Personalización rápida

- **Nombre del departamento** — editable directo en el header (campo contenteditable)
- **Logo** — reemplazar `img/logo-artica-blanco.png` por el logo deseado (altura referencia: 40px)
- **Colores** — modificar los tokens CSS en `:root` al inicio del `<style>`

---

*Desarrollado internamente por ARTICA Creative Studio · 2026*
