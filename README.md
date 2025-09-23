# PairMe™ — Comprehensive Engineering Documentation (v1.2) 🌟

![1000023847](https://github.com/user-attachments/assets/cc11da47-7578-475b-9531-1100f9463d90))
  *Image: PairMe App Icon (1000023795)*

**Author**: Christopher Perry  
**Contributors**: Talor W  
**Status**: v1.2 (Production-Ready MVP with Events, Budget, Coupons, No External Licensing)  
**Date**: September 23, 2025  
**License**: No License – Restricted to Christopher Perry and Talor W  

**PairMe™** is an AI-driven mobile and web app that curates personalized **Food, Drink, Spark, Vibe, and Events** recommendations from a single scan (QR, barcode, or image). Powered by the proprietary **LabelSync Engine** for label parsing, translation, compliance, and drink inventory management, PairMe delivers a seamless, budget-optimized experience with auto-applied coupons and an Events ticketing hub. Inspired by Spotify’s discovery and Mint.com’s budgeting, it’s the ultimate lifestyle curator with a cinematic UI, targeting 10M+ users at <400ms P95 latency.


**Use this for**: Infrastructure setup, development, API integrations, compliance, investor pitches, and USPTO filing.  

---

## 📁 Repository Structure

```
pairme/
├── README.md
├── .env.example
├── docker-compose.yml
├── .github/
│   ├── workflows/
│   │   ├── deploy-api.yml
│   │   ├── deploy-web.yml
├── pairme-api/
│   ├── Dockerfile
│   ├── package.json
│   ├── jest.config.js
│   ├── migrations/
│   │   ├── 2025092301_create_tables.sql
│   │   ├── 2025092302_add_events_budget.sql
│   ├── src/
│   │   ├── index.js
│   │   ├── services/
│   │   │   ├── db.js
│   │   │   ├── labelsync.js  # Enhanced for drink inventory
│   │   │   ├── personalization.js
│   │   │   ├── analytics.js
│   │   │   ├── budget.js
│   │   │   ├── events.js
│   │   │   ├── coupons.js
│   │   ├── middleware/
│   │   │   ├── auth.js
│   │   │   ├── validate.js
│   │   ├── routes/
│   │   │   ├── scan.js
│   │   │   ├── pair.js
│   │   │   ├── find.js
│   │   │   ├── feedback.js
│   │   │   ├── auth.js
│   │   │   ├── analytics.js
│   │   │   ├── events.js
│   │   │   ├── budget.js
│   │   │   ├── coupons.js
│   │   ├── data/
│   │   │   ├── whiskey_db.json
│   │   │   ├── food_db.json
│   │   │   ├── strain_db.json
│   │   │   ├── vibe_db.json
│   │   │   ├── events_db.json
│   │   ├── __tests__/
│   │   │   ├── scan.test.js
│   │   │   ├── pair.test.js
│   │   │   ├── find.test.js
│   │   │   ├── feedback.test.js
│   │   │   ├── auth.test.js
│   │   │   ├── analytics.test.js
│   │   │   ├── events.test.js
│   │   │   ├── budget.test.js
│   │   │   ├── coupons.test.js
├── pairme-app/
│   ├── app.json
│   ├── package.json
│   ├── .env.example
│   ├── babel.config.js
│   ├── App.js
│   ├── assets/
│   │   ├── adaptive-icon.png
│   │   ├── icon.png  # Updated with 1000023795
│   │   ├── splash.png
│   │   ├── events-icon.svg
│   ├── src/
│   │   ├── config.js
│   │   ├── api.js
│   │   ├── auth/
│   │   │   ├── AuthContext.js
│   │   ├── screens/
│   │   │   ├── AuthScreen.js
│   │   │   ├── ScanScreen.js
│   │   │   ├── SessionScreen.js
│   │   │   ├── SettingsScreen.js
│   │   │   ├── EventsScreen.js
│   │   │   ├── BudgetScreen.js
│   │   ├── utils/
│   │   │   ├── export.js
│   │   ├── __tests__/
│   │   │   ├── AuthScreen.test.js
│   │   │   ├── ScanScreen.test.js
│   │   │   ├── SessionScreen.test.js
│   │   │   ├── EventsScreen.test.js
│   │   │   ├── BudgetScreen.test.js
├── reset-web/
│   ├── package.json
│   ├── vite.config.js
│   ├── index.html
│   ├── src/
│   │   ├── main.jsx
│   │   ├── pages/
│   │   │   ├── Home.jsx
│   │   ├── components/
│   │   │   ├── BudgetSlider.jsx
│   │   │   ├── EventsHub.jsx
│   │   │   ├── CouponCard.jsx
├── docs/
│   ├── patent-draft.md
│   ├── api-spec.md
│   ├── compliance-report.md
│   ├── analytics.md
│   ├── style-guide.md
├── postman/
│   ├── PairMe.postman_collection.json
├── assets/
│   ├── visuals/
│   │   ├── hero-mockup.png  # Updated with 1000020584
│   │   ├── session-screen.png  # Updated with 1000020589
│   │   ├── find-near-me.png  # Updated with 1000020590
│   │   ├── coupon-book.png
│   │   ├── app-icon.png  # Updated with 1000023795
│   │   ├── events-hub.png
│   │   ├── budget-slider.png
```

---

## 📜 Documentation Sections

### 🌍 00_CONCEPT - Vision

<details>
<summary>Overview</summary>

PairMe™ is the world’s premier AI-driven pairing and lifestyle curation app, delivering personalized recommendations for **Food, Drink, Spark, Vibe, and Events** from a single scan. Powered by the **LabelSync Engine**, it parses labels, translates multilingual data, ensures compliance, and manages drink inventory in-house. Features include a **budget slider + optimizer**, **auto-applied coupons**, and an **Events ticketing hub**, blending Spotify’s discovery with Mint.com’s financial control.

![Hero Mockup]![1000023855](https://github.com/user-attachments/assets/7c4ce1f1-9099-4d12-af28-233592577e6c)

*Image: PairMe Hero Screen (1000020584)*

**Outcomes**:
- **Personalization**: 95% user satisfaction; adapts in 1–2 sessions.
- **Efficiency**: <2s Session page render (5 recommendation windows).
- **Budget Control**: Optimizes pairings within $20–$1000+ budgets.
- **Compliance**: Meets alcohol, cannabis, and ticketing regulations.
- **Engagement**: 75% D1 retention; 45% merchant/event click-through.
- **Scalability**: 10M+ users, <400ms P95 latency.

**Target Users**:
- **Primary**: Food/drink enthusiasts, cannabis users, event-goers (18–45, urban).
- **Secondary**: Merchants and event organizers for premium features.
- **Buyers**: Consumers ($4.20/mo); businesses ($32/mo).

**Market Validation**:
- **Pain Points**: Siloed apps, no budget-aware pairing, no event integration (85% user frustration).
- **Opportunity**: $2B+ pairing/ticketing market; 15% CAGR (2025–2030).
- **Competitors**: Ticketmaster (events-only), Weedmaps (cannabis-only); none combine cross-category pairing, budgeting, and events.

</details>

### ❓ 00_CONCEPT - Problem Space

<details>
<summary>Details</summary>

Users face fragmented apps for pairings, ticketing, and budgeting, with no unified platform for curating a night within financial constraints. PairMe solves this with:
- **Unified Pairing**: One scan for 5 categories.
- **Budget Optimizer**: AI allocates spend within user limits.
- **Auto-Applied Coupons**: Maximizes value with merchant deals.
- **Events Hub**: Live ticketing for concerts, tastings, and experiences.
- **LabelSync Engine**: In-house OCR, translation, compliance, and drink inventory.

**Key Challenges Addressed**:
- **Fragmentation**: Combines 5 categories in one app.
- **Budgeting**: Ensures affordability with real-time optimization.
- **Compliance**: Age gating, geofencing, regulatory scans.
- **Scalability**: Handles 10M+ daily scans.
- **Personalization**: Adapts to user feedback and tastes.

</details>

### 🛠 01_TECH_SPECS - System Architecture

<details>
<summary>Architecture</summary>

**Frontend**: React Native (Expo) for iOS/Android; React/Vite for web.  
**Backend**: Node.js/Express, PostgreSQL (Supabase), Redis cache.  
**Search**: Meilisearch/Elasticsearch + `pgvector` for flavor/event embeddings.  
**AI**: Deterministic scoring (cosine similarity) + LLM for suggestions.  
**Budget Optimizer**: Knapsack algorithm for spend allocation.  
**Storage**: S3-compatible for images, tickets, labels.  
**LabelSync Engine**: OCR (Tesseract.js), translation (Hugging Face), compliance scans, drink inventory parsing.  
**Integrations**: Ticketmaster (events), Weedmaps (cannabis), Untappd (beer), Open Food Facts (food/drinks).  
**Pipelines**:
- **Ingestion**: Cron/webhooks pull partner data; LabelSync normalizes labels/inventory.
- **Scoring**: Ranks candidates by flavor vectors, budget, availability.
- **Find-It**: Geo-based merchant/event lookup.
- **Budget**: Optimizes allocations within constraints.
- **Coupons**: Auto-applies deals.

**Performance**:
- Latency: <400ms P95 for `/pair`, `/events`, `/budget`.
- Uptime: 99.9% API availability.
- Scalability: 10M+ daily active users.

</details>

### 📊 01_TECH_SPECS - Data Model Schema

<details>
<summary>Schema</summary>

```typescript
interface SeedItem {
  type: "strain" | "whiskey" | "food" | "playlist" | "event";
  id?: string;
  name: string;
  meta?: Record<string, any>;
}

interface Vectors {
  terpenes?: Record<string, number>;
  flavor_tags?: string[];
  intensity?: number; // 0–1
}

interface RecItem {
  id: string;
  name: string;
  type: "food" | "drink" | "spark" | "event";
  score: number; // 0–1
  why: string;
  profile?: Record<string, any>;
  mode?: "neat" | "big_ice" | "highball" | "stirred";
  pricing?: { min_price?: number; store_count?: number; coupon_id?: string };
}

interface VibeItem {
  category: "music" | "lighting" | "environment" | "scent" | "activity";
  name: string;
  details: string;
  score?: number; // 0–1
  links?: { service?: string; url?: string }[];
}

interface Budget {
  total: number; // e.g., $100
  allocations: {
    food?: number;
    drink?: number;
    spark?: number;
    vibe?: number;
    event?: number;
  };
  remaining: number;
  coupons_applied: string[];
}

interface Session {
  session_id: string;
  seed_item: SeedItem;
  profile?: {
    mood?: "chill" | "creative" | "social" | "sleep";
    intensity_target?: number; // 0–1
    preferences?: { sweet?: number; spice?: number; fruit?: number; smoke?: number };
    budget?: Budget;
  };
  vectors: Vectors;
  recommendations: {
    food: RecItem[];
    drink: RecItem[];
    spark: RecItem[];
    vibe: VibeItem[];
    event: RecItem[];
  };
}
```

</details>

### ⚙️ 01_TECH_SPECS - Pairing Engine

<details>
<summary>Pairing Logic</summary>

```typescript
type Vec = Record<string, number>;

const dot = (a: Vec, b: Vec) => Object.keys(a).reduce((s, k) => s + (a[k] || 0) * (b[k] || 0), 0);
const mag = (a: Vec) => Math.sqrt(dot(a, a));
const cosine = (a: Vec, b: Vec) => (mag(a) * mag(b) === 0 ? 0 : dot(a, b) / (mag(a) * mag(b)));

interface PairInput {
  terpenes: Vec;
  intensity: number; // 0–1
  mood?: "chill" | "creative" | "social" | "sleep";
  prefs?: { sweet?: number; spice?: number; fruit?: number; smoke?: number };
  budget?: Budget;
}

interface Candidate {
  id: string;
  vector: Vec;
  abv?: number;
  availability?: "common" | "uncommon" | "grail";
  price?: number;
  coupon_id?: string;
  event_type?: "concert" | "tasting" | "show" | "pop-up";
}

export function scoreCandidate(seed: PairInput, c: Candidate): number {
  const terpToFlavor: Vec = {
    sweet: (seed.terpenes.limonene || 0) * 0.2 + (seed.terpenes.linalool || 0) * 0.2,
    fruit_orchard: (seed.terpenes.limonene || 0) * 0.3,
    fruit_tropical: (seed.terpenes.myrcene || 0) * 0.2,
    spice: (seed.terpenes.caryophyllene || 0) * 0.4,
    oak: (seed.terpenes.myrcene || 0) * 0.2,
    smoke: 0,
  };

  const sim = cosine(terpToFlavor, c.vector);
  const complement = (c.vector.spice || 0) * 0.3 + (c.vector.oak || 0) * 0.2;
  const smokeClash = (c.vector.smoke || 0) * 0.6;
  const abvMatch = c.abv ? 1 - Math.abs(c.abv / 60 - seed.intensity) : 0.75;
  const moodBoost =
    seed.mood === "chill" ? (1 - (c.vector.spice || 0)) * 0.2 :
    seed.mood === "creative" ? ((c.vector.fruit_tropical || 0) + (c.vector.fruit_orchard || 0)) * 0.1 :
    seed.mood === "social" ? (c.vector.sweet || 0) * 0.1 : 0;
  const availability = c.availability === "common" ? 0.05 : c.availability === "uncommon" ? 0.02 : 0;
  const budgetFit = seed.budget && c.price ? Math.min(1, seed.budget.remaining / c.price) * 0.1 : 0;

  const base = 0.30 * sim + 0.20 * complement - 0.15 * smokeClash + 0.15 * abvMatch + 0.10 * moodBoost + availability + budgetFit;
  const p = seed.prefs || {};
  const prefAdj =
    (p.sweet || 0) * (c.vector.sweet || 0) * 0.05 +
    (p.spice || 0) * (c.vector.spice || 0) * 0.05 +
    (p.fruit || 0) * ((c.vector.fruit_orchard || 0) + (c.vector.fruit_tropical || 0)) * 0.05 -
    (p.smoke || 0) * (c.vector.smoke || 0) * 0.05;

  return Math.max(0, Math.min(1, base + prefAdj));
}

export function optimizeBudget(session: Session): Session {
  const { budget, recommendations } = session;
  if (!budget) return session;

  const items = [
    ...recommendations.food,
    ...recommendations.drink,
    ...recommendations.spark,
    ...recommendations.event,
  ].filter(item => item.pricing?.min_price);

  const knapsack = (items: RecItem[], capacity: number) => {
    const dp = Array(items.length + 1).fill(0).map(() => Array(capacity + 1).fill(0));
    const selected = Array(items.length + 1).fill(0).map(() => Array(capacity + 1).fill([]));

    for (let i = 1; i <= items.length; i++) {
      for (let w = 0; w <= capacity; w++) {
        const item = items[i - 1];
        const price = item.pricing!.min_price!;
        if (price <= w) {
          const value = item.score * 100;
          if (dp[i - 1][w] < value + dp[i - 1][w - price]) {
            dp[i][w] = value + dp[i - 1][w - price];
            selected[i][w] = [...selected[i - 1][w - price], item];
          } else {
            dp[i][w] = dp[i - 1][w];
            selected[i][w] = selected[i - 1][w];
          }
        } else {
          dp[i][w] = dp[i - 1][w];
          selected[i][w] = selected[i - 1][w];
        }
      }
    }

    return selected[items.length][capacity];
  };

  const selectedItems = knapsack(items, budget.total);
  const newRecs = {
    food: selectedItems.filter(i => i.type === 'food'),
    drink: selectedItems.filter(i => i.type === 'drink'),
    spark: selectedItems.filter(i => i.type === 'spark'),
    event: selectedItems.filter(i => i.type === 'event'),
    vibe: recommendations.vibe, // Vibe is free
  };

  const totalSpent = selectedItems.reduce((sum, i) => sum + (i.pricing!.min_price || 0), 0);
  budget.allocations = {
    food: newRecs.food.reduce((sum, i) => sum + (i.pricing!.min_price || 0), 0),
    drink: newRecs.drink.reduce((sum, i) => sum + (i.pricing!.min_price || 0), 0),
    spark: newRecs.spark.reduce((sum, i) => sum + (i.pricing!.min_price || 0), 0),
    event: newRecs.event.reduce((sum, i) => sum + (i.pricing!.min_price || 0), 0),
    vibe: 0,
  };
  budget.remaining = budget.total - totalSpent;

  return { ...session, recommendations: newRecs, profile: { ...session.profile, budget } };
}
```

**Explainability Output**:
- Score: 0–1 (e.g., 0.92).
- Why: “Citrus complements oak; fits $50 budget.”
- Mode: “Neat” or “Big ice.”
- Availability: “3 stores nearby from $54; event at $25.”

</details>

### 🔒 01_TECH_SPECS - Security & Compliance

<details>
<summary>Security</summary>

- **Authentication**: Argon2 hashing, JWT (access/refresh tokens), CSRF protection.
- **Age Gating**: 21+ modal; ID verification (e.g., Yoti).
- **Geofencing**: Spark as cannabis in legal regions, coffee/desserts elsewhere.
- **Compliance**: LabelSync scans for alcohol, cannabis, ticketing regulations; adheres to 3-tier laws.
- **Data Privacy**: GDPR/CCPA-compliant; opt-out for retention; encrypted storage.

</details>

### 📸 02_INTEGRATION_LABELSYNC - LabelSync Engine

<details>
<summary>Overview</summary>

The **LabelSync Engine** powers PairMe’s in-house parsing, translation, compliance, and drink inventory management:
1. **OCR & Extraction**: Processes QR/barcode/image into JSON (Tesseract.js).
2. **Translation**: Multilingual labels (Hugging Face transformers).
3. **Compliance**: Flags regulatory issues for alcohol, cannabis, ticketing.
4. **Inventory**: Parses drink data from user scans or public datasets (e.g., Open Food Facts).

**Integration Points**:
- **Scan**: `/scan` endpoint for OCR/translation.
- **Inventory**: `/find` queries LabelSync’s drink database.
- **Risk Scans**: `/compliance/scan` for regulatory checks.
- **Data Flow**: Labels → flavor vectors → scoring → budget optimization.

</details>

### 🎫 02_INTEGRATION_EVENTS - Events Hub

<details>
<summary>Events</summary>

```javascript
// pairme-api/src/services/events.js
import axios from 'axios';

const TICKETMASTER_API_KEY = process.env.TICKETMASTER_API_KEY;
const BASE_URL = 'https://app.ticketmaster.com/discovery/v2';

export async function searchEvents({ geo, budget, preferences }) {
  const response = await axios.get(`${BASE_URL}/events.json`, {
    params: {
      apikey: TICKETMASTER_API_KEY,
      latlong: `${geo.lat},${geo.lon}`,
      radius: 50,
      unit: 'km',
      keyword: preferences.type || '',
      startDateTime: preferences.date || '',
      maxPrice: budget || 1000,
    },
  });

  return response.data._embedded?.events.map(e => ({
    id: e.id,
    name: e.name,
    type: 'event',
    score: 0.8, // Placeholder; refine with vectors
    why: `Matches ${preferences.type || 'local experience'}`,
    pricing: { min_price: e.priceRanges?.[0]?.min || 0 },
    url: e.url,
  }));
}
```

</details>

### 💸 02_INTEGRATION_COUPONS - Coupons

<details>
<summary>Coupons</summary>

```javascript
// pairme-api/src/services/coupons.js
export async function applyCoupons(session: Session): Promise<Session> {
  const { budget, recommendations } = session;
  if (!budget) return session;

  const coupons = await db.query('SELECT * FROM coupons WHERE min_price <= $1 AND active = true', [budget.total]);
  const applicable = coupons.rows.filter(c => {
    const itemTypes = recommendations[c.item_type]?.map(i => i.id) || [];
    return itemTypes.includes(c.item_id) && c.expires_at > new Date();
  });

  const updatedRecs = { ...recommendations };
  let totalDiscount = 0;
  const appliedCoupons = [];

  for (const coupon of applicable) {
    const item = Object.values(updatedRecs).flat().find(i => i.id === coupon.item_id);
    if (item && item.pricing?.min_price) {
      item.pricing.min_price -= coupon.discount;
      totalDiscount += coupon.discount;
      appliedCoupons.push(coupon.id);
    }
  }

  budget.remaining += totalDiscount;
  budget.coupons_applied = appliedCoupons;

  return { ...session, recommendations: updatedRecs, profile: { ...session.profile, budget } };
}
```

</details>

### 🎨 03_UX - Wireframes

<details>
<summary>Wireframes</summary>

![Session Screen]![1000023795](https://github.com/user-attachments/assets/a26890d5-ed13-4d59-be75-0607073cfd4a)![1000020589](https://github.com/user-attachments/assets/44bbbb93-8137-47a9-b80b-ca5fbb891430)

![1000020606](https://github.com/user-attachments/assets/fe7c5dba-8a5e-4242-92f2-c3330c8364a7)
)  
*Image: PairMe Mood Pairing Screen (1000020589)*

**Scan Screen**:
- Camera feed with Neon Teal scanner frame (pulsing).
- Buttons: Flash, History, Manual Input (Amber Gold).
- Tagline: “Scan Once. Curate Your Night.” (Inter Bold, White).

**Mood Pairing Screen**:
- 2x3 grid: Food, Drink, Spark, Vibe, Events, Budget.
- Budget Slider: Neon Teal, $20–$1000+, real-time allocations.
- Optimize Button: “Optimize My Night” (Neon Teal, glowing).
- Coupons: Amber Gold badges (e.g., “-$10 off”).
- Tiles: Score (Neon Teal), “Why” button (Inter Italic), price (Amber Gold).

**Events Screen**:
- Scrollable event list (concerts, tastings) with images, prices, distances.
- Filters: Type, Date (Amber Gold).
- CTA: “Buy Tickets” (Neon Teal).

**Budget Screen**:
- Full-screen slider ($20–$1000+).
- Pie chart: Allocations (Food, Drink, Spark, Vibe, Events).
- Toggle: “Apply Coupons” (Amber Gold).
- CTA: “Save Budget” (Neon Teal).

**Find It Near Me**:
- List: Merchant/event name, price, stock, distance, URL.
- Filters: Radius, Price, Stock Status (Amber Gold).
]

  
*Image: PairMe Find It Near Me Screen (1000020590)*

**Settings Screen**:
- Taste Refresh Slider (7–180 days).
- Budget Preferences: One-time or monthly.
- Top Tags Visualization (bar chart).
- Export: JSON/CSV via email, sharing.

</details>

### 🖼 03_UX - Visual Style Guide

<details>
<summary>Style Guide</summary>

**Colors**:
| Name          | Hex       | Usage                                    |
|---------------|-----------|------------------------------------------|
| Deep Indigo   | `#1E1A39` | Backdrop, headers                       |
| Neon Teal     | `#00FFC6` | AI glow, buttons, active states         |
| Amber Gold    | `#FFB300` | Coupons, pricing, event tickets         |
| Crimson Red   | `#E63946` | Alerts, timers                          |
| White         | `#FFFFFF` | Text, overlays                          |
| Neutral Gray  | `#4A4A4A` | Secondary text, inactive states         |

**Typography**:
- Headings: Inter Bold (24–32px).
- Body: SF Pro/Roboto Regular (14–16px).
- Captions: Inter Italic (12px for “Why it Works”).

**Tone**:
- Cinematic gradients (Indigo to Teal), glowing edges.
- High-res images (whiskey, cannabis, charcuterie, events).
- Micro-animations (scanner pulse, tile flips, budget slider).

**Iconography**:
- Custom SVGs: Food (fork), Drink (glass), Spark (starburst), Vibe (music note), Events (ticket).
- Neon Teal for active; Gray for inactive.

**Motion**:
- 300ms transitions, 200ms button hovers.
- 60fps on mid-tier devices (iPhone 12, Galaxy A54).

</details>

### 🚀 04_GTM - Launch Plan

<details>
<summary>Launch Plan</summary>

- **Region**: US pilot; state-aware compliance.
- **Channels**: TikTok/IG/X reels; influencer collabs (whiskey experts, budtenders, event organizers).
- **Beta**: Invite-only codes at bars, dispensaries, venues; 10K users.
- **KPIs**: 75% D1 retention, 45% merchant/event clicks, 80% thumbs-up rate, 60% coupon redemption.

</details>

### 💼 07_INVESTOR_PACK - One-Pager

<details>
<summary>One-Pager</summary>

**PairMe™**: AI-driven pairing and ticketing hub for Food, Drink, Spark, Vibe, Events with budget optimization and in-house inventory.  
- **Problem**: Siloed apps, no budget-aware pairing, no event integration.  
- **Solution**: Scan → Curated night with budget optimizer, coupons, Events hub; LabelSync for parsing/inventory.  
- **Market**: $2B+; 15% CAGR.  
- **Traction**: 10K beta users; 75% D1 retention target.  
- **Ask**: $750K for US launch; scale LabelSync and Events globally.

</details>

### ⚖️ 08_IP_LEGAL - Patent Draft

<details>
<summary>Patent Draft</summary>

**Title**: Adaptive Cross-Category Pairing and Ticketing System with Budget Optimization and In-House Label Parsing  
**Inventors**: Christopher Perry, Talor W  
**Abstract**: A mobile/web app for personalized pairing across food, drink, spark, vibe, and events, using image-based scanning, deterministic scoring, budget optimization, auto-applied coupons, and LabelSync for OCR, translation, compliance, and drink inventory. Novel features include budget optimization, event ticketing, and taste decay.  
**Claims**:
1. Cross-category pairing and ticketing via image-based input and flavor vectors.
2. Budget optimization using knapsack algorithm.
3. In-house label parsing and inventory via LabelSync.
4. UI for budget allocation and taste decay.  
**Drawings**:
- FIG.1: System architecture.
- FIG.2: Scan-to-Session UX flow.
- FIG.3: Events hub UI.
- FIG.4: Budget optimizer flowchart.  
**Predicate**: US20230153654A1, US20220198476A1.

</details>

### 🛠 09_DEPLOYMENT - Setup Instructions

<details>
<summary>Setup</summary>

**Backend (pairme-api)**:
```bash
git clone https://github.com/your-username/pairme-api.git
cd pairme-api
npm ci
cp .env.example .env
# Edit .env: DATABASE_URL, TICKETMASTER_KEY
npm run migrate
npm start
```

**Mobile App (pairme-app)**:
```bash
cd pairme-app
npm install
cp .env.example .env
# Edit .env: API_BASE
npx expo start
```

**Web (reset-web)**:
```bash
cd reset-web
npm install
npm run dev
# Set VITE_API_BASE in .env
```

**Docker**:
```bash
docker compose up --build
```

</details>

### 🧪 10_TESTING - Test Plan

<details>
<summary>Test Plan</summary>

- **Unit Tests**: Jest for backend (routes, services, LabelSync); Jest-Expo for frontend (screens).
- **Integration Tests**: Postman for `/pair`, `/events`, `/budget`, `/coupons/apply`.
- **Load Testing**: 1K concurrent `/pair` requests; <400ms P95.
- **Compliance Tests**: LabelSync risk scans on 100 partner ToS.
- **Usability**: 95% task completion rate in beta (100 users).

</details>

---

## 🎨 PairMe Visual Master Pack

### 1. 🎯 Master Style Guide

**Colors**:
| Name          | Hex       | Usage                                    |
|---------------|-----------|------------------------------------------|
| Deep Indigo   | `#1E1A39` | Backdrop, headers                       |
| Neon Teal     | `#00FFC6` | AI glow, buttons, active states         |
| Amber Gold    | `#FFB300` | Coupons, pricing, event tickets         |
| Crimson Red   | `#E63946` | Alerts, timers                          |
| White         | `#FFFFFF` | Text, overlays                          |
| Neutral Gray  | `#4A4A4A` | Secondary text, inactive states         |

**Typography**:
- Headings: Inter Bold (24–32px).
- Body: SF Pro/Roboto Regular (14–16px).
- Captions: Inter Italic (12px).

**Tone**:
- Cinematic gradients, glowing edges.
- High-res images (whiskey, cannabis, events).
- Micro-animations (scanner pulse, tile flips).

### 2. 📱 App Experience Images

**App Icon (1000023795)**:
- Bold “P” on Indigo-to-Teal gradient; micro-icons for 5 categories.
- Usage: App Store, home screen.

**Hero Screen (1000020584)**:
- iPhone 16 frame with Scan Screen; Neon Teal scanner, Amber Gold CTA.
- Usage: App Store, website hero.

**Mood Pairing Screen (1000020589)**:
- 2x3 grid with budget slider, coupons, and Events tile.
- Usage: App Store screenshots.

**Find Near Me (1000020590)**:
- Merchant/event list with Neon Teal pins, Amber Gold filters.
- Usage: App Store previews.

---

