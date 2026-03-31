# Muelle85 · Landing Inmersiva & Sistema de Gestión (CRA + GSAP + Apps Script)

Landing site **mobile‑first** y de **alto impacto visual** para Muelle85. Combina una narrativa premium con un sistema robusto de gestión de datos mediante Google Sheets. Incluye **Hero en video**, **animaciones GSAP**, **render 3D interactivo** y tracking avanzado de leads.

---

## 📝 1) Descripción & Visión

Desarrollé la landing de **Muelle85**, una marca de campers y trailers premium concebida como una propuesta de estilo de vida, aventura e identidad. El objetivo principal fue construir una experiencia web inmersiva que transmitiera robustez, diseño e ingeniería, combinando narrativa emocional con llamadas a la acción orientadas a conversión.

### Características Clave:
- **Navegación Fluida**: Animaciones de scroll mediante **GSAP** y **ScrollTrigger**.
- **Visuales Premium**: Integración de video optimizado y un **render 3D interactivo** del producto que rota con el scroll.
- **Header Glass**: Estética moderna con efecto de refracción y menú hamburguesa animado.
- **Optimización Media**: Equilibrio entre impacto visual y rendimiento, reduciendo el peso de assets sin comprometer la percepción de marca.

---

## 🚀 2) Objetivos & Alcance

- **Mobile‑First**: Experiencia optimizada para dispositivos móviles (foco principal de tráfico).
- **Catálogo Dinámico**: Gestión de **Gamas** desde **Google Sheets** (vía Google Apps Script).
- **Medición & Tracking**: Seguimiento de UTMs, referrer y `session_id` anónimo.
- **Conversión Directa**: Punto de contacto estratégico mediante registro de **leads por WhatsApp**.

---

## 🛠️ 3) Pila Tecnológica

- **Frontend**: Create React App (React 18+), **SCSS** con `@use` (arquitectura modular).
- **Animaciones**: **GSAP** + **ScrollTrigger** para transiciones ligadas al scroll.
- **UI interna**: Context API para **Toasts** y **Modales** (sin dependencias externas).
- **Backend (Serverless)**: **Google Apps Script** sobre **Google Sheets**.
- **Tracking**: UTMs persistentes + `session_id` en `localStorage`.

---

## 📁 4) Estructura del Proyecto

```bash
src/
  assets/               # Imágenes y videos optimizados
  components/
    about/              # Secciones narrativas y efectos especiales (FX)
    ui/                 # Componentes de interfaz (Modal, Toast, GlassRefraction)
    Header.jsx          # Header glass + menú animado
    Hero.jsx            # Video de impacto inicial
    Gamas.jsx           # Listado consumido desde Apps Script
    WhatsAppButton.jsx  # CTA con registro de lead
  context/              # Manejo de estado global (Modal, Toast)
  hooks/                # Custom hooks (GSAP Context, etc.)
  lib/                  # Configuración de librerías externas (GSAP setup)
  services/             # appscript.js (Fetch GET/POST form-urlencoded)
  styles/               # SCSS Modular (_variables, _mixins, base, components)
  utils/                # session.js (ID anónimo), utm.js (Parseo de parámetros)
  App.jsx               # Punto de entrada de rutas y lógica global
```

---

## 📊 5) Modelo de Datos & Endpoints (Apps Script)

### Pestañas en Google Sheets:
- **Sesiones**: Tracking de tráfico (`utm_source`, `utm_medium`, `url_entrada`, etc.).
- **Leads_WhatsApp**: Registro de intenciones de compra y contacto.
- **Gamas**: Gestión de productos (`id_gama`, `nombre`, `estado` "publicado/borrador").

### Endpoints:
- **GET** `?action=getGamas` → Devuelve gamas publicadas.
- **POST** `action=registrarSesion` → Inicializa tracking de visita.
- **POST** `action=agregarLeadWA` → Registra conversión antes de abrir WhatsApp.

---

## ⚙️ 6) Configuración Local

1. **Variables de entorno** (`.env`):
    ```env
    REACT_APP_APPS_SCRIPT_URL=https://script.google.com/macros/s/XXX/exec
    REACT_APP_WA_PHONE=54911XXXXXXXX
    ```

2. **Instalación & Correr:**
    ```bash
    npm i
    npm start
    ```

3. **Producción:**
    ```bash
    npm run build
    ```

---

## ✨ 7) Calidad & Accesibilidad

- **A11y**: Atributos ARIA en navegación y modales; cierre por `Escape` y gestión de foco.
- **Performance**: Carga de video por `ScrollScrub` y Lazy Loading de assets pesados.
- **Estilos**: Tipografías fluidas con `clamp()` y arquitectura de diseño CSS Moderno.

---

## 🗺️ 8) Roadmap

- [ ] CTA "Obtén tu viaje de prueba" (Glassmorphism style).
- [ ] Implementación de `section_view` events para mapa de calor interno.
- [ ] Skeletons de carga para el listado de Gamas.
- [ ] SEO Avanzado (OpenGraph, Sitemap).

---

## 📜 9) Licencia

MIT © Muelle85 / Desarrollado por **Enzo Pinotti** & **Fedes Consultora**
