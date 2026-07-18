# SuitUp — AI Outfit Recommendations

**SuitUp** is a free mobile shopping app (Android & iOS) that helps people
discover and buy outfits that genuinely suit them. Instead of endless
scrolling, users pick an occasion — casual, formal, a sunny day, an evening
out — and SuitUp assembles complete looks from real retailer products,
ranked by an on-device AI model trained on outfit compatibility.

> This repository hosts the app's **product catalogs**: the curated,
> regularly refreshed lists of retailer products the app recommends from.

---

## What the app does

1. **Shop a Look** — the user picks a style; SuitUp combines retailer
   products into complete outfits (top + bottom + shoes + outerwear),
   filters them through fashion rules (color harmony, category matching),
   and ranks them with AI for that specific user.
2. **My Wardrobe** — users photograph clothes they already own; SuitUp
   builds outfits from them.
3. **Complete the Look** — SuitUp recommends a single new product to buy
   that best completes outfits with what the user already owns — a
   high-intent purchase recommendation.

Every recommended product is shown with its image, brand, and price, and
links **directly to the retailer's product page** to purchase. SuitUp does
not sell anything itself, holds no inventory, and processes no payments —
it sends ready-to-buy shoppers to retailers.

## Why retailers partner with us

- **High purchase intent** — products are recommended as part of a complete
  outfit the user already likes, not as random banner impressions.
- **Fair, brand-safe presentation** — products appear with accurate names,
  images, and prices from official product feeds; deep links go straight to
  the retailer's own product page.
- **Complete-the-Look conversions** — recommending the one item a shopper is
  missing is among the strongest purchase triggers in fashion e-commerce.
- **Privacy-first** — all AI runs on the user's device. No user photos or
  personal data are collected or shared; retailers receive clean referral
  traffic.

## How this repository is used

The app downloads its region catalog from this repository at launch:

| Region | File | Currency |
|---|---|---|
| United States | [`catalog_us.json`](catalog_us.json) | USD |
| Europe | [`catalog_europe.json`](catalog_europe.json) | EUR |
| Israel | [`catalog_israel.json`](catalog_israel.json) | ILS |

Catalogs are rebuilt and validated **weekly** by an automated pipeline that
ingests official affiliate product feeds (AWIN, Rakuten Advertising) and
hand-curated selections. Each item carries its brand, category, color,
price, product image, and the retailer's product URL:

```json
{
  "id": "brand-12345",
  "brand": "Example Brand",
  "name": "Linen shirt",
  "category": "shirt",
  "color": "beige",
  "gender": "men",
  "imageUrl": "https://cdn.example.com/12345.jpg",
  "productUrl": "https://www.example.com/products/12345",
  "price": 49.90,
  "currency": "USD"
}
```

Dead links and unavailable products are pruned automatically on every
refresh, so the app never shows a product that can't be bought.

## For affiliate networks & brand managers

We feature retailer products via **official product feeds** with tracked
deep links. If you'd like your brand featured in SuitUp's outfit
recommendations — or have questions about how your products are presented —
please open an issue on this repository or contact the publisher account
that linked you here.

---

*SuitUp — outfits that suit you.*
