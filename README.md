# Hash21 Shop ⚡

Tienda de objetos de diseño inspirados en Bitcoin creados por artistas latinoamericanos y con pagos nativos Lightning Network.

## ¿Qué es?

Hash21 Shop es la tienda de objetos de diseño de la Galeria de arte inspirado en Bitcoin Hash 21. Cada objeto es único y diseñado por artistas y se paga directamente con Lightning Network — sin intermediarios, sin KYC, sin procesadores de pago tradicionales.

**Live:** [hash21.studio/shop](https://hash21.studio/shop)

## ¿Cómo funciona?

1. El usuario elige un objeto.
2. Click en "Comprar con Lightning ⚡"
3. Se genera un invoice via LNURL (Lightning Address)
4. El usuario escanea el QR con su wallet Lightning
5. Pago confirmado → coordina envío

### Flow técnico

```
Usuario → Elige producto → Click comprar
  → Fetch LNURL metadata desde Lightning Address
  → Request invoice (amount en msats + comment)
  → Muestra QR code (bolt11)
  → Poll payment verification
  → Confirmación
```

## Stack

- **Frontend:** HTML/CSS/JS puro (zero frameworks, zero build tools)
- **Pagos:** LNURL-pay via Lightning Address
- **QR:** Generación client-side
- **Hosting:** GitHub Pages
- **Wallet:** Wallet of Satoshi (Lightning Address)

## Características

- ⚡ Pagos Lightning nativos (LNURL-pay)
- 🎨 Diseño premium, responsive, mobile-first
- 🖼️ Galería de productos con hover effects
- 💬 Comentario del comprador incluido en el invoice
- 📱 QR code para escanear desde cualquier wallet
- 🔒 Sin backend, sin base de datos, sin servidor
- 🌐 Bilingüe (ES/EN ready)
- 0️⃣ Zero dependencias externas

## Correr localmente

```bash
git clone https://github.com/warrior-lai/hash21-shop.git
cd hash21-shop
python3 -m http.server 8000
# o
npx serve .
```

Abrir http://localhost:8000

## Configuración

Para usar tu propia Lightning Address, editá la variable en `index.html`:

```javascript
const LIGHTNING_ADDRESS = "tu@walletofsatoshi.com";
```

## Productos

| Pieza | Material | Sats |
|---|---|---|
| Stay Humble and Stack Sats | Plata 925 | 278,000 |
| Fix the Money, Fix the World | Plata 925 | 278,000 |
| Proof of Work, Proof of Soul | Plata 925 | 278,000 |
| Bloque 21 | Plata 925 | 359,000 |
| Dije Rayo ⚡ | Plata 925 | 157,000 |

## Por qué Lightning

- **Sin intermediarios:** El pago va directo del comprador al vendedor
- **Sin fees absurdos:** Fracciones de centavo vs 3-5% de procesadores tradicionales
- **Sin KYC:** No necesitás cuenta, email, ni datos personales
- **Instantáneo:** Confirmación en segundos, no días
- **Global:** Cualquier persona del mundo puede comprar

## Sobre Hash21

[Hash21](https://hash21.studio) es una galería de arte curada en Bitcoin. Exhibición, certificación y ahora comercio — todo nativo en Lightning Network.

## Hackathon

Proyecto presentado en **Lightning Hackathons 2026 — FOUNDATIONS** de [La Crypta](https://lacrypta.ar).

## Equipo

- **Abstract Lai** (@warrior-lai) — Diseño, producto, arte
- **Ragnar** 🪓 — AI assistant, desarrollo, estrategia

## Licencia

MIT

---

⚡ Hecho con plata, código y Bitcoin.
