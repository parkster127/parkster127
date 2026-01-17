<div align="center">

<!-- Header con imagen de fondo y texto superpuesto -->
<table>
<tr>
<td>
<img src="./assets/banners/Whisk_64d6ecec4d4289db22d456252b7e4300dr.jpeg" alt="Mazatlán Sunset" width="900"/>
</td>
</tr>
</table>

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Inter&weight=700&size=32&duration=3000&pause=1000&color=FFFFFF&center=true&vCenter=true&width=800&lines=MARTIN+PARKS;Full-Stack+Engineer+%7C+System+Architect;Scalable+Solutions+%7C+Best+Practices;From+Mazatl%C3%A1n+to+the+World)](https://git.io/typing-svg)

<br/>

<a href="https://www.linkedin.com/in/parkster127" target="_blank">
  <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
</a>
<a href="mailto:martin_herrera5@hotmail.com">
  <img src="https://img.shields.io/badge/Email-0078D4?style=for-the-badge&logo=microsoft-outlook&logoColor=white" alt="Email"/>
</a>
<a href="https://github.com/parkster127">
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
</a>
<img src="https://komarev.com/ghpvc/?username=parkster127&style=for-the-badge&color=FF6B35" alt="Profile Views"/>

</div>

---

## About Me

**Software Engineer** specializing in **scalable architectures** and **production-grade systems**. I design and build solutions that handle real traffic, real users, and real money.

With experience optimizing fintech backends at **Yopaki** and architecting multi-tenant platforms, I focus on:

- **System Design** — Microservices, event-driven architectures, multi-tenancy
- **Database Engineering** — Schema design, query optimization, data modeling
- **Scalability** — Horizontal scaling, caching strategies, async processing
- **Best Practices** — Clean code, testing, documentation, CI/CD

> _"Code is not about making things work—it's about making them work at scale."_

**Location:** Mazatlán, Sinaloa, México

---

## System Design & Architecture

<table>
<tr>
<td width="50%" valign="top">

### System Architecture

- Microservices decomposition and bounded contexts
- Event-driven architecture with message queues
- RESTful APIs, GraphQL, real-time WebSockets
- Multi-tenant infrastructure design
- Caching strategies (Redis, CDN, application-level)

</td>
<td width="50%" valign="top">

### Database Design

- Normalized and denormalized schema patterns
- Query optimization (indexing, N+1 prevention)
- Relational (PostgreSQL) and Document (MongoDB) modeling
- Zero-downtime migration strategies
- Replication and sharding patterns

</td>
</tr>
<tr>
<td width="50%" valign="top">

### Scalability Patterns

- Load balancing and distribution
- Horizontal scaling with stateless services
- Circuit breakers and fault tolerance
- Rate limiting and API protection
- Background jobs and worker queues

</td>
<td width="50%" valign="top">

### Security & Reliability

- Authentication (JWT, OAuth, sessions)
- Payment security and PCI compliance
- Data integrity (ACID, eventual consistency)
- Observability, monitoring, and alerting
- Disaster recovery and failover

</td>
</tr>
</table>

---

## Tech Stack

<div align="center">

### Languages

[![Languages](https://skillicons.dev/icons?i=ts,js,python,php,bash&theme=dark)](https://skillicons.dev)

### Frontend

[![Frontend](https://skillicons.dev/icons?i=nextjs,react,tailwind,html,css&theme=dark)](https://skillicons.dev)

### Backend

[![Backend](https://skillicons.dev/icons?i=nodejs,express,fastify,rabbitmq&theme=dark)](https://skillicons.dev)

### Databases

[![Databases](https://skillicons.dev/icons?i=mongodb,postgres,mysql,redis,supabase&theme=dark)](https://skillicons.dev)

### DevOps

[![DevOps](https://skillicons.dev/icons?i=docker,vercel,linux,git,github&theme=dark)](https://skillicons.dev)

</div>

<div align="center">

<br/>

![Stripe](https://img.shields.io/badge/Stripe-5469d4?style=flat-square&logo=stripe&logoColor=white)
![Clip](https://img.shields.io/badge/Clip_México-00C853?style=flat-square&logoColor=white)
![Uber](https://img.shields.io/badge/Uber_Eats_API-000000?style=flat-square&logo=uber&logoColor=white)
![Retool](https://img.shields.io/badge/Retool-3D3D3D?style=flat-square&logo=retool&logoColor=white)
![Socket.io](https://img.shields.io/badge/Socket.io-010101?style=flat-square&logo=socket.io&logoColor=white)

</div>

---

## Featured Projects

### HelloSushi — Multi-Tenant Restaurant Platform

Production system handling real orders and payments across multiple branches.

<table>
<tr>
<td width="55%" valign="top">

**Architecture:**

```
PWA (Next.js) → API Gateway (Express) → Services (Workers)
                        │
          ┌─────────────┼─────────────┐
          ▼             ▼             ▼
      MongoDB        Redis        MySQL
      (Orders)      (Cache)      (Legacy)
```

**Features:**

- Multi-tenant architecture for multiple restaurant branches
- Real-time order sync under 200ms with WebSockets
- Payment integrations: Stripe, Clip México
- Legacy PHP to microservices migration
- PWA with offline-first capabilities

</td>
<td width="45%" valign="top">

**Stack:**

- Next.js 14 + TypeScript
- Node.js + Express
- MongoDB + Redis
- Docker + Vercel
- Socket.io

**Results:**

- 99.9% uptime
- Multi-branch support
- Payment gateway failover
- Production traffic handling

</td>
</tr>
</table>

---

### Legacy Modernization Engine

Transforming 10+ year old PHP monoliths into scalable microservices using the Strangler Fig pattern.

```
BEFORE                              AFTER
┌─────────────────────┐            ┌─────────────────────┐
│   PHP Monolith      │     →      │   Order Service     │
│   - Coupled code    │            │   Payment Service   │
│   - Shared DB       │            │   Sync Agent        │
│   - No tests        │            │   Message Queues    │
└─────────────────────┘            └─────────────────────┘
```

**Stack:** Node.js, Fastify, RabbitMQ, Docker, TypeScript

---

### MazTech Web Solutions

Web development agency focusing on Mexican business digitalization.

- Custom e-commerce and automation systems
- Template marketplace (in development)
- SaaS solutions for local businesses

---

## GitHub Stats

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=parkster127&show_icons=true&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=FF6B35&icon_color=FF6B35&text_color=c9d1d9" height="160"/>
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=parkster127&layout=compact&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=FF6B35&text_color=c9d1d9" height="160"/>

<br/>

[![GitHub Streak](https://github-readme-streak-stats.herokuapp.com?user=parkster127&theme=dark&hide_border=true&background=0D1117&stroke=FF6B35&ring=FF6B35&fire=FF6B35&currStreakLabel=FF6B35)](https://git.io/streak-stats)

</div>

---

## Engineering Philosophy

<table>
<tr>
<td width="50%">

**What I Do**

- Ship production-ready code, not prototypes
- Design for scale from day one
- Own mistakes and fix them fast
- Document everything thoroughly
- Test, then deploy with confidence

</td>
<td width="50%">

**What I Avoid**

- "Works on my machine" excuses
- N+1 queries and unoptimized code
- Shortcuts that create technical debt
- Half-finished projects
- Over-engineering simple problems

</td>
</tr>
</table>

---

## Beyond Code

League of Legends competitive player • Minecraft modpack architect • Sushi enthusiast & HelloSushi founder • Suits & HIMYM binge-watcher • Proud Doberman owner

---

## Let's Connect

<div align="center">

**Looking for an engineer who understands system design, ships production code, takes ownership, and writes scalable solutions?**

<br/>

[![Email](https://img.shields.io/badge/Email-martin__herrera5@hotmail.com-0078D4?style=for-the-badge)](mailto:martin_herrera5@hotmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-parkster127-0A66C2?style=for-the-badge)](https://www.linkedin.com/in/parkster127)

<br/>

---

**Built with dedication from Mazatlán, México**

</div>
