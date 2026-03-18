# Hash21 ⚡

Plataforma de arte soberano con pagos Lightning nativos. Galería, tienda, zaps y certificación on-chain — todo construido sobre Bitcoin.

**Live:** [hash21.studio](https://hash21.studio)

## ¿Qué es Hash21?

Hash21 es un hub de arte soberano donde cada obra queda vinculada a un bloque de Bitcoin. Los artistas exhiben, reciben zaps (propinas Lightning) y venden objetos de diseño — sin intermediarios, sin KYC, sin procesadores de pago tradicionales.

## Funcionalidades

### ⚡ Zap System (NIP-57)
- Zap (propina Lightning) en cada obra y cada artista
- Detección automática de pagos via **Nostr zap receipts** (NIP-57)
- Frontend escucha múltiples relays Nostr en tiempo real
- Confirmación visual instantánea al detectar el pago
- Montos predefinidos (21, 210, 2100, 21K sats) + monto personalizado
- Mensaje opcional del zapper

### 🛒 Shop — Objetos de Diseño
- Tienda de joyas y objetos inspirados en Bitcoin
- Checkout con **LNURL-pay** via Lightning Address
- QR code generado client-side
- Opciones post-pago: envío sin KYC (Telegram) o con dirección
- Bilingüe ES/EN

### 🖼️ Galería / Colección
- Carousel horizontal + grilla expandible
- Lightbox con detalle de obra
- Obras de múltiples artistas (Lai⚡️, Roxy, Martu, Guadis)

### 👥 Creadores
- Perfiles de artistas con avatar, bio y links
- Panel expandible con galería de obras por artista
- Zap directo al artista

### 📜 Certificación On-Chain
- Certificados de registro vinculados a un bloque de Bitcoin (OpenTimestamps)
- Prueba de existencia en el tiempo, permanente e incensurable
- Verificación pública en hash21.studio/verify

## Stack Técnico

- **Frontend:** HTML/CSS/JS puro (zero frameworks, zero build tools)
- **Pagos:** LNURL-pay + NIP-57 (Nostr zaps)
- **Detección de pagos:** WebSocket a relays Nostr (kind 9735)
- **QR:** qrcode@1.5.1 (client-side)
- **Certificación:** OpenTimestamps (Bitcoin blockchain)
- **Hosting:** GitHub Pages
- **Wallet:** Wallet of Satoshi (Lightning Address con soporte NIP-57)
- **i18n:** ES/EN completo

## Flow de Pago (NIP-57)

```
Usuario → Click ⚡ Zap → Elige monto
  → Frontend crea zap request (kind 9734)
  → Fetch LNURL-pay + envía nostr zap request
  → WoS devuelve invoice Lightning
  → Muestra QR (bolt11)
  → Frontend escucha relays Nostr (WebSocket)
  → WoS publica zap receipt (kind 9735)
  → Frontend detecta pago → ✅ Confirmación instantánea
```

## Correr Localmente

```bash
git clone https://github.com/warrior-lai/hash21-shop.git
cd hash21-shop
python3 -m http.server 8000
```

Abrir http://localhost:8000

## Productos (Shop)

| Pieza | Material | Sats |
|---|---|---|
| Stay Humble and Stack Sats | Plata 925 | 278,000 |
| Fix the Money, Fix the World | Plata 925 | 278,000 |
| Proof of Work, Proof of Soul | Plata 925 | 278,000 |
| Bloque 21 | Plata 925 | 359,000 |
| Dije Rayo ⚡ | Plata 925 | 157,000 |

## Por qué Lightning

- **Sin intermediarios:** Pago directo del comprador al artista/vendedor
- **Sin fees absurdos:** Fracciones de centavo vs 3-5% de procesadores tradicionales
- **Sin KYC:** No necesitás cuenta, email ni datos personales
- **Instantáneo:** Confirmación en segundos
- **Global:** Cualquier persona del mundo puede comprar o zapear
- **Verificable:** NIP-57 publica prueba de pago en Nostr

## Sobre Hash21

[Hash21](https://hash21.studio) es una galería de arte curada en Bitcoin. Permanencia para la obra. Soberanía para el artista.

## Hackathon

Proyecto presentado en **Lightning Hackathons 2026 — FOUNDATIONS** de [La Crypta](https://lacrypta.ar).

Tema: Lightning Payments Basics.

## Equipo

- **Lai⚡️** (@warrior-lai) — Fundadora, artista, diseño, producto
- **Ragnar** 🪓 — Desarrollo, estrategia

## Licencia

MIT

---

⚡ Hecho con arte, código y Bitcoin.
