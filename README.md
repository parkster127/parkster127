<div align="center">

# Martin

**Full-Stack Engineer | System Architect**

<img src="https://readme-typing-svg.herokuapp.com?font=Poppins&weight=400&size=14&duration=4000&pause=2000&color=888888&center=true&vCenter=true&width=700&lines=%22Programming+is+like+sex%3A+One+mistake+and+you+have+to+support+it+for+the+rest+of+your+life.%22" alt="Quote"/>

</div>

---

## **About Me**

**Software Engineer** specializing in **scalable architectures** and **production-grade systems**. I design and build solutions that handle real traffic, real users, and real money.

With experience architecting multi-tenant restaurant platforms with live POS sync, payment gateway integrations, and real-time order management, I focus on building systems that **don't break at 3am**.

### **Where was I born?**

In the beautiful **Mazatlan** city — _Donde se rompen las olas_ 🌊

---

## **What I Do Best**

<table>
<tr>
<td width="25%" align="center">

**System Architecture**

- Multi-tenant SaaS
- Event-driven systems
- Real-time WebSocket
- Legacy system bridging

</td>
<td width="25%" align="center">

**Backend Engineering**

- Express + MongoDB
- Zod contract validation
- RabbitMQ workers
- Circuit breakers

</td>
<td width="25%" align="center">

**Payment & Integration**

- Stripe, Clip (MX)
- Uber Eats API
- POS MySQL sync
- Webhook signatures

</td>
<td width="25%" align="center">

**Security & Reliability**

- RBAC permissions
- Fraud detection
- Rate limiting (Redis)
- Correlation tracing

</td>
</tr>
</table>

---

## **Tech Stack**

<div align="center">

**Languages**

[![Languages](https://skillicons.dev/icons?i=ts,js,python,php,bash&theme=dark)](https://skillicons.dev)

**Frontend**

[![Frontend](https://skillicons.dev/icons?i=nextjs,react,tailwind,html,css&theme=dark)](https://skillicons.dev)

**Backend**

[![Backend](https://skillicons.dev/icons?i=nodejs,express,rabbitmq&theme=dark)](https://skillicons.dev)

**Databases**

[![Databases](https://skillicons.dev/icons?i=mongodb,postgres,mysql,redis,supabase&theme=dark)](https://skillicons.dev)

**DevOps & CI/CD**

[![DevOps](https://skillicons.dev/icons?i=docker,vercel,linux,git,github,githubactions&theme=dark)](https://skillicons.dev)

<br/>

![Stripe](https://img.shields.io/badge/Stripe-5469d4?style=for-the-badge&logo=stripe&logoColor=white)
![Clip](https://img.shields.io/badge/Clip_Mexico-00C853?style=for-the-badge&logoColor=white)
![Uber](https://img.shields.io/badge/Uber_Eats_API-000000?style=for-the-badge&logo=uber&logoColor=white)

</div>

---

## **Success Stories**

Real problems solved for real clients.

### **HelloSushi -- Multi-Branch Restaurant Platform**

**Challenge:** A restaurant chain running a 10+ year old Windows POS system with MySQL. No online ordering, no multi-branch support, no payment gateway. Orders were phone-only and manually entered into the legacy system.

**Solution:** Built a complete three-tier platform from scratch:

- **Express API** (`hello-api`) -- 30+ route modules, MongoDB with Mongoose, RabbitMQ worker for async order processing, WebSocket real-time updates, Redis for rate limiting and pub/sub
- **React PWA** (`hello-app`) -- Mobile-first ordering app with Vite, service worker, cart validation, Clip payment SDK integration, address autocomplete with fuzzy matching
- **Next.js CMS** (`saas-monorepo/apps/cms`) -- Admin panel with App Router, TanStack Query for data fetching, Zustand for state, shadcn/ui components, granular RBAC
- **Legacy Sync Agent** (`legacy-sync-agent`) -- Bridges MongoDB orders to the old MySQL POS in real-time, mapping modern product structures to legacy schema

**Architecture:**

```
PWA Customer --> Express API --> MongoDB
                   |    ^          |
                   v    |          v
              RabbitMQ   |    Legacy Sync Agent --> MySQL POS
                   |     |          |
                   v     |          v
             Order Worker   |    Kitchen Display
                   |        |
                   v        v
              WebSocket (Socket.IO + Redis Pub/Sub)
                   |
                   v
              CMS Admin Panel
```

**Results:**
- Multi-branch restaurant chain support (branch-scoped orders, delivery zones, operating hours)
- Real-time POS sync -- orders appear in the legacy kitchen display within seconds
- Payment processing via Clip (transparent checkout, 3DS, webhook verification)
- Uber Eats integration -- incoming orders from the marketplace are normalized and synced to the same POS
- Fraud detection system with Redis-backed velocity checks, IP fanout tracking, and Telegram alerts
- Server-side pricing engine -- all prices and promotions calculated server-side, client never controls totals

**Stack:** Node.js TypeScript Express MongoDB RabbitMQ Redis Socket.IO Next.js React Vite Cloudinary Twilio

---

## **Engineering Highlights**

Patterns and implementations from production systems.

### **Contract-First Validation with Zod**

Every API route validates input through Zod schemas via a `validateRequest()` middleware. The schema both validates and strips unknown fields -- preventing silent data loss when new model fields are added without updating the route schema. Validation errors return structured field-level feedback.

```
Route -> validateRequest(ZodSchema) -> handler receives typed, sanitized body
```

### **Accent-Insensitive Search for Spanish Text**

Custom `buildAccentInsensitiveRegex()` utility that maps accented characters (a, e, i, o, u, n) to character classes (`[aáàäâã]`) for MongoDB queries. Searches for "atun" correctly match "Atun", "camaron" matches "Camaron", and "nino" matches "Nino". Required for a Mexican restaurant with Spanish-language product names.

### **Dual PUT/PATCH Route Registration**

A recurring production bug: the CMS sends `PUT` for updates, but Express routes only registered `PATCH`. Result: silent 404s. The fix is a deliberate pattern where every update route registers both methods pointing to the same handler and middleware chain. Documented as a project rule after causing 4+ production incidents.

```typescript
router.patch('/:id', authenticate, requirePermission('module.update'), validateRequest(Schema), handler);
router.put('/:id', authenticate, requirePermission('module.update'), validateRequest(Schema), handler);
```

### **Multi-Tenant Branch Isolation**

Each branch has its own operating hours, delivery zones, payment credentials, and Uber Eats store mapping. Orders are branch-scoped -- the API enforces that users can only access orders for their assigned branches unless they have global access. Delivery zones use fuzzy Levenshtein matching for colony names with source priority tracking (CMS > legacy > historical import).

### **POS Legacy Sync Architecture**

The `legacy-sync-agent` is a standalone TypeScript service that:
1. Consumes RabbitMQ messages when a new order is created or updated in MongoDB
2. Maps modern order items (variants, option groups, extras) to legacy MySQL product IDs using a configurable mapping table
3. Inserts into the old Windows POS MySQL database so the kitchen display works without changes
4. Handles recipe removals (e.g., "no onion") as separate POS line items
5. Includes a claim-based lease system for multi-instance coordination
6. Sends Telegram notifications on sync failures

### **PWA with Offline-First Capabilities**

The customer-facing app is a React PWA built with Vite and `vite-plugin-pwa`. Features service worker registration with update prompts, mobile-first atomic design (atoms/molecules/organisms/components), 26 custom hooks for cart validation, delivery zone detection, Clip SDK integration, FCM push notifications, haptic feedback, and address autocomplete.

### **RBAC with Granular Permissions**

6 roles (developer, admin, manager, cashier, call_center, viewer) mapped to 30+ granular permissions. The `authenticate` middleware verifies JWTs, resolves role permissions, and attaches them to the request. The `requirePermission()` factory middleware checks access on every route. The CMS mirrors this with client-side `access-control.ts` that determines navigation visibility and route protection.

### **Fraud Detection Pipeline**

Orders pass through a Redis-backed fraud detection middleware before creation:
- **R1:** Customer velocity -- max orders per customer in a rolling window
- **R2:** IP fanout -- max different customers from the same IP
- **R3:** High-value orders from unverified phones
- **R4:** Previously blocked customers

Configurable modes (mark, block, both). All events logged to MongoDB for audit. Telegram alerts sent in real-time. Gracefully degrades when Redis is unavailable (never blocks legitimate orders due to infrastructure failure).

### **Circuit Breaker for External Services**

Custom `CircuitBreaker` class with CLOSED/OPEN/HALF_OPEN state machine. Pre-configured instances for Clip payments (strict: 3 failures threshold) and Uber Eats (5 failures, 30s timeout). Prevents cascading failures when payment gateways or delivery platforms are down.

### **Real-Time Order Updates via WebSocket + Redis Pub/Sub**

Socket.IO with Redis adapter for multi-instance scaling. An EventBus (Observer pattern) decouples order lifecycle events from WebSocket broadcasting. The CMS receives live order status updates without polling. Branch-scoped rooms ensure each branch only sees its own orders.

### **Server-Side Pricing Engine**

All prices calculated server-side to prevent client-side manipulation. The pricing engine handles:
- Base prices with variant support (protein-based pricing)
- Promo $99 ceiling at item level
- Cart-level NxM promotions (3x2, 4x3) with best-deal selection
- Delivery channel pricing (dine_in vs to_go vs delivery)
- Price history snapshots for audit

The client sends product selections; the server returns the final price. Promotions are never accepted from client input.

### **Correlation IDs for Distributed Tracing**

Every request gets a unique correlation ID (timestamp-UUID format). Propagated through middleware, services, logs, and error responses. Enables end-to-end tracing across the API, worker, and legacy sync agent.

---

## **Activity**

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/parkster127/parkster127/snake/github-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/parkster127/parkster127/snake/github-snake.svg" />
  <img alt="github-snake" src="https://raw.githubusercontent.com/parkster127/parkster127/snake/github-snake-dark.svg" />
</picture>

</div>
