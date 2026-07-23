# AMAKAIK · Sistema Financiero Ganadero

Organización paralela a IMPROLUX. Mismo sistema, base de datos propia, identidad borravino.
La hacienda se administra en **ADE** (Angus del Este); acá solo se valoriza.

## Qué es cada archivo

| Archivo | Dónde vive | Para qué |
|---|---|---|
| `server.js` | Railway (`amakaik-bot`) | Backend + base de datos |
| `amakaik_v4.html` | GitHub Pages | El panel (lo que se usa) |
| `index.html` | GitHub Pages | Entrada, redirige al panel |
| `package.json` | Railway | Dependencias |

## Deploy

**Backend (Railway)**
1. Proyecto `amakaik-bot`, base propia (NO compartir con improlux-bot).
2. Subir `server.js` + `package.json`.
3. Verificar la raíz: debe responder `AMAKAIK Bot activo 🟢`.

**Panel (GitHub Pages)**
1. Subir `amakaik_v4.html` + `index.html`.
2. Si la URL de Railway no es `amakaik-bot-production.up.railway.app`,
   corregir la constante `RAILWAY_URL` en `amakaik_v4.html` (está marcada con ⚠️).

## Variables de entorno (Railway)

| Variable | Para qué |
|---|---|
| `ANTHROPIC_API_KEY` | Asistente / lectura de comprobantes |
| `TWILIO_ACCOUNT_SID` / `TWILIO_AUTH_TOKEN` | WhatsApp |
| `ADE_URL` | Traer el rodeo desde ADE (`https://angus-del-este-production.up.railway.app`) |
| `COPERNICUS_CLIENT_ID` / `COPERNICUS_CLIENT_SECRET` | NDVI satelital de los potreros |
| `DB_PATH` | Ruta de la base en el volumen persistente |

## Notas

- La clave de acceso del panel está en `amakaik_v4.html` (`const CLAVE`). Cambiarla.
  Es un candado básico: el código es público, no es seguridad real.
- Las claves de navegador (`amakaik_auth`, `amakaik_campo`) van separadas de las de
  IMPROLUX a propósito: ambos paneles comparten dominio en GitHub Pages y se pisarían.
- Ciclo productivo: marzo a febrero.
