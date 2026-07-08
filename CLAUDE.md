# CLAUDE.md — A13I Accelerator

Este repositorio contiene el sitio para el programa DWY (Do-With-You) evergreen de A13I (A13I Accelerator), además de hospedar los lead magnets principales migrados desde `a13i-partner`.

## 🏁 Visión General del Proyecto
- **Rol:** Plataforma de entrenamiento y funnel del programa DWY.
- **Tecnología:** Sitios estáticos HTML/CSS/JS puros. Sin compilación, sin empaquetadores, sin frameworks. Desplegado en Vercel.
- **Contexto Global:** Las reglas de negocio (ICP, marca, voz, decisiones) viven en la raíz global en `../01-estrategia.md` hasta `../05-decisiones.md`. Debes leerlos antes de tocar copy o lógica comercial.

---

## 📂 Estructura del Repositorio y Rutas

```
a13i-accelerator/
├── index.html                  # Home del sitio (pendiente de reescritura total)
├── business.html               # Estructura de referencia para dueños de negocio (ICP único)
├── client-wins.html            # Casos de éxito con atribución honesta (UBA, HolaVeggie, etc.)
├── calculadora.html            # Lead Magnet: Calculadora de Costo Operativo (migrado desde partner)
├── ops-canvas.html             # Lead Magnet: Ops Canvas interactivo (migrado desde partner)
├── quick-wins-ai.html          # Lead Magnet: Formulario calificador y redirección (migrado desde partner)
├── wa-redirect.html            # Redirección WhatsApp / Envío de webhook a n8n
├── arquitectura-sitio.md       # Estado verificado de producción y rutas
├── assets/                     # Imágenes, avatares y recursos estáticos
├── vercel.json                 # Configuración de despliegue en Vercel (cleanUrls: true)
└── README.md
```

---

## ⚙️ Arquitectura Técnica y Convenciones

1. **Single-File Pattern:** Cada archivo HTML es autocontenido. Estilos en `<style>` dentro del `<head>`, lógica JS en `<script>` al final del `<body>`.
2. **Transferencia de Datos:** Handoff de leads mediante `sessionStorage` (prefijo `a13i_*`). Evitar usar query params en URLs.
3. **Estilo y Diseño:**
   - Tipografía: Inter para textos y JetBrains Mono para datos, códigos y métricas.
   - Utilizar variables de CSS para colores.
   - Respetar el "Filtro anti-IA" de `../03-marca-y-voz.md` en cualquier cambio de copy.
4. **Despliegue:** Push a `main` desencadena auto-deploy en Vercel.

---

## 🎯 Plan de Reconversión (DWY de 1 solo camino)
De acuerdo a las decisiones estratégicas (`../05-decisiones.md`):
- El "Camino A" (para agencias) queda obsoleto y se elimina.
- La nueva Home (`/`) debe reconstruirse usando la estructura de `business.html` pero en español rioplatense y tono Axel.
- El flujo final de agendamiento (`/book`) debe redirigir al calificador tipo Pymbú.
