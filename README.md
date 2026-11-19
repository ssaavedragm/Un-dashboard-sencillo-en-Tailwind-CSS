# 📊 InfluMetrics: un dashboard sencillo en Tailwind CSS

Dashboard de reporte para una influencer que promociona productos de marcas en **Instagram, TikTok y YouTube**. Reúne en una sola página los datos de todas sus redes para responder rápido a preguntas como:

- ¿Cuánto dinero estoy generando en comisiones?
- ¿Qué productos generan más ingresos?
- ¿Qué tan bien convierten mis anuncios (conversiones / alcance)?
- ¿Qué plataformas dan mejor retorno (ingresos / costes)?
- ¿Cuál es el engagement rate por plataforma y por producto?

**Contexto del negocio:** promociona 3 productos (A: 50 €, B: 120 €, C: 80 €) y recibe un **15% de comisión** por cada venta. Los datos del dashboard son de ejemplo.

## 🛠️ Tecnologías

- **HTML5**
- **Tailwind CSS v4**, cargado desde el CDN oficial para navegador:

```html
<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
```

Todo el diseño se hace con clases utility, sin JavaScript y sin CSS personalizado. Los colores de marca (`instagram`, `tiktok`, `youtube`, `brand`) se definen con la directiva `@theme` de Tailwind v4 en un bloque `<style type="text/tailwindcss">`.

## 🧱 Estructura del dashboard

### 1️⃣ Bloque superior: KPIs
Seis indicadores principales: comisiones generadas, ventas totales, tasa de conversión, retorno (ingresos/costes), engagement rate y precio medio de venta. Cada uno muestra su variación respecto al periodo anterior.

### 2️⃣ Bloque intermedio: drivers
- Evolución mensual de comisiones (gráfico de barras)
- Funnel de conversión: alcance → interacciones → clics → carrito → compra
- Reparto de comisiones y ROI por plataforma (gráfico de donut con `conic-gradient`)
- Rendimiento por producto (comisión y conversión)
- Engagement por plataforma (me gusta, comentarios, compartidos y guardados)
- Actividad publicada (posts, stories, reels, vídeos y shorts)

### 3️⃣ Bloque inferior: detalles operacionales
- **Tabla de productos:** precio, ventas, comisión, conversión y ROI
- **Tabla de plataformas:** alcance, engagement, conversiones y ROI, con 🏆 en la mejor plataforma de cada métrica
- **Tabla de campañas:** fechas, producto, plataforma, resultados y rendimiento
- **Alertas:** caídas de conversión, picos y anomalías
- **Rankings con filtros:** top productos, top plataformas, top campañas y oportunidades de mejora. Los filtros funcionan solo con CSS (radios + variantes `has-checked:` y `group-has-[…]:`)

## 📱 Diseño responsive (mobile-first)

El diseño parte de una sola columna en móvil y se amplía con los breakpoints de Tailwind:

| Breakpoint | Ancho | Cambios principales |
|---|---|---|
| base | < 640px | 1 columna, menú hamburguesa (checkbox + `peer-checked:`) |
| `sm` | ≥ 640px | KPIs en 2 columnas |
| `md` | ≥ 768px | Drivers en 2 columnas, cabecera en fila |
| `lg` | ≥ 1024px | Barra lateral fija, KPIs en 3 columnas |
| `xl` | ≥ 1280px | Drivers en 3 columnas, tablas lado a lado |
| `2xl` | ≥ 1536px | Los 6 KPIs en una sola fila |

Las tablas hacen scroll horizontal dentro de su tarjeta, así la página nunca se desborda en pantallas pequeñas.

## 🚀 Cómo verlo

Abre `index.html` en el navegador o levanta el servidor incluido:

```bash
pip3 install flask && python3 server.py
```

## 📁 Archivos

```
├── index.html   # Dashboard completo (HTML + clases de Tailwind CSS v4)
├── server.py    # Servidor local de la plantilla de 4Geeks
└── README.md
```

---

Proyecto realizado para [4Geeks Academy](https://4geeksacademy.com/es) a partir de la plantilla [html-hello](https://github.com/4GeeksAcademy/html-hello).
