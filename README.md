
<div align="center">

# 💊 MediKiosk × Marien-Apotheke
### Headless E-Commerce Prototype for the Pharmaceutical Sector

DSGVO-compliant, containerized commerce platform integrating a Next.js storefront with a Shopware 6 backend via a headless API architecture.

<br />

[![Next.js](https://img.shields.io/badge/Next.js-16-000000?style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org/)
[![Shopware 6](https://img.shields.io/badge/Shopware_6-6.5-189EFF?style=for-the-badge&logo=shopware&logoColor=white)](https://www.shopware.com/)
[![PHP](https://img.shields.io/badge/PHP-8.2-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://www.php.net/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
![DSGVO](https://img.shields.io/badge/DSGVO-Compliant-34A853?style=for-the-badge&logo=shieldsdotio&logoColor=white)

![License](https://img.shields.io/badge/License-Private-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Prototype-orange?style=for-the-badge)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-7-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-3-FF6600?style=for-the-badge&logo=rabbitmq&logoColor=white)
![OpenSearch](https://img.shields.io/badge/OpenSearch-2-005EB8?style=for-the-badge&logo=opensearch&logoColor=white)

</div>

---

## 📖 About The Project

The German pharmaceutical retail sector is undergoing a rapid digital transformation, while many pharmacies still rely on legacy systems that fail to meet modern expectations for online ordering, real-time availability, and strict data protection requirements.

**MediKiosk × Marien-Apotheke** is a headless e-commerce prototype developed as part of a real-world evaluation for **Marien-Apotheke Köln**. It explores a decoupled, enterprise-grade architecture designed specifically for regulated healthcare environments, where **DSGVO (GDPR) compliance and operational reliability are critical requirements**.

### The Problem

- Traditional pharmacy systems are monolithic and not suited for modern omnichannel commerce.
- Strict German and EU data protection regulations (DSGVO / GDPR) limit the use of many standard SaaS solutions.
- There is no widely adopted reference architecture for headless commerce in regulated pharmaceutical environments.

### The Solution

This prototype separates the **presentation layer (Next.js)** from the **commerce backend (Shopware 6)** via the Shopware Store API, enabling:

- Full flexibility in UI/UX development
- Independent scaling of frontend and backend systems
- Privacy-by-design compliance with regulatory requirements

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 🏗️ **Headless Architecture** | Complete separation between frontend (Next.js) and backend (Shopware 6) via REST Store API |
| 🛡️ **DSGVO / GDPR Compliance** | Privacy-by-design implementation including consent management and data minimization |
| 🐳 **Fully Containerized** | One-command Docker environment including Shopware, MySQL, Redis, RabbitMQ, OpenSearch, and Mailhog |
| ⚡ **Server-Side Rendering** | Next.js SSR for performance, SEO optimization, and improved Core Web Vitals |
| 🔍 **Full-Text Search** | OpenSearch integration for fast and scalable product discovery |
| 📨 **Async Processing** | RabbitMQ-based message queue for background tasks such as order processing and notifications |
| 🗄️ **High-Performance Caching** | Redis-based caching for sessions and frequently accessed data |
| 🧪 **Testing Infrastructure** | Jest and React Testing Library for unit and integration testing |

---

## 🛠️ Built With

### Frontend

| Technology | Version | Purpose |
|------------|---------|---------|
| Next.js | 16.x | React framework with SSR and App Router |
| React | 19.x | UI component library |
| TypeScript | 5.x | Type-safe development |
| Jest | 30.x | Testing framework |

### Backend

| Technology | Version | Purpose |
|------------|---------|---------|
| Shopware 6 | 6.5+ | Headless commerce engine and admin system |
| PHP | 8.2 | Server-side runtime |
| MySQL / MariaDB | 8.0 / 11.8 | Relational database system |

### Infrastructure

| Technology | Version | Purpose |
|------------|---------|---------|
| Docker | Compose v2 | Container orchestration |
| Redis | 7 (Alpine) | Caching and session storage |
| RabbitMQ | 3 (Alpine) | Message queue system |
| OpenSearch | 2.x | Full-text search engine |
| Mailhog | latest | SMTP testing environment |

---

## 🏛️ Architecture Overview

```text
Next.js Frontend  ────────► Shopware 6 API
│                           │
│                           ▼
│                 Commerce Core (Products, Orders)
│                           │
▼                           ▼
SSR Rendering             MySQL / MariaDB
│                           │
├──── Redis Cache ─────────┤
├──── RabbitMQ Queue ──────┤
└──── OpenSearch Index ────┘

```

**Flow Summary:**

* Frontend requests data via Store API only
* Shopware processes all commerce logic
* Redis accelerates repeated requests
* RabbitMQ handles async workflows
* OpenSearch powers product discovery
* Docker orchestrates the full environment

---

## 🚀 Getting Started

### Requirements

* Docker Desktop
* Node.js LTS (18+)
* Git

### Setup

```bash
git clone [https://github.com/aseel7marwan/marien-apotheke.git](https://github.com/aseel7marwan/marien-apotheke.git)
cd marien-apotheke

```

### Start Backend

```bash
cd backend
docker compose up -d

```

Services:

* Shopware Admin: [http://localhost:8000/admin](https://www.google.com/search?q=http://localhost:8000/admin)
* RabbitMQ: [http://localhost:15672](https://www.google.com/search?q=http://localhost:15672)
* Mailhog: [http://localhost:8025](https://www.google.com/search?q=http://localhost:8025)

### Initialize Shopware Headless Mode

```bash
docker exec -it medikiosk_shopware bash /var/www/html/init_marien.sh

```

### Frontend Setup

```bash
cd ../frontend
cp .env.local.example .env.local
npm install
npm run dev

```

Frontend:

* [http://localhost:3000](https://www.google.com/search?q=http://localhost:3000)

---

## 🔒 Security & Compliance

This project was developed with **DSGVO (GDPR) compliance as a core architectural principle**, not as an add-on.

### Data Privacy (DSGVO / GDPR)

| Principle | Implementation |
| --- | --- |
| Data Minimization | Only essential operational data is collected and processed |
| Purpose Limitation | Data is used exclusively for order processing and legally required communication |
| Storage Limitation | Automated retention policies are enforced via Shopware |
| Right to Erasure | GDPR-compliant deletion workflows are supported |
| Cookie Consent | Consent banner ensures compliant tracking behavior |

### Technical Security Measures

* **🔐 HTTPS Enforcement** — Encrypted communication via TLS
* **🔑 API Authentication** — Scoped Shopware Store API access keys
* **🐳 Network Isolation** — Docker network segmentation
* **📧 Email Sandbox** — Mailhog prevents real email transmission in development
* **🚫 Debug Hardening** — Debugging tools disabled in production
* **🔒 Secure ORM Layer** — Parameterized queries via Shopware DAL

---

## 📁 Project Structure

```text
frontend/        Next.js storefront (UI layer)
backend/         Shopware 6 commerce system
docs/            Architecture + governance documentation
docker-compose   Full infrastructure orchestration
init_marien.sh   Headless API initialization script

```

---

## ⚖️ License

> **Showcase / Private Prototype** > This project is part of a technical portfolio and evaluation system.
> Reuse, redistribution, or commercial usage is not permitted without explicit approval.

---

## 👤 Author & Contact

**Aseel Marwan Kheder** IT-Support & Junior Full-Stack Developer

Based in Cologne, Germany

- 🌐 Portfolio: www.aseelmarwan.de  
- 💼 GitHub: https://github.com/aseel7marwan  
- 💼 LinkedIn: https://www.linkedin.com/in/aseel7marwan/  
- 📧 Email: kontakt@aseelmarwan.de  
