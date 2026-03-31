<p align="center">
  <h1 align="center">💊 MediKiosk × Marien-Apotheke</h1>
  <p align="center">
    <strong>Headless E-Commerce Prototype for the Pharmacy Sector</strong>
    <br />
    A DSGVO-compliant, containerized commerce platform connecting a Next.js storefront to a Shopware 6 backend via headless API architecture.
  </p>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Next.js-16-000000?style=for-the-badge&logo=next.js&logoColor=white" alt="Next.js" />
  <img src="https://img.shields.io/badge/Shopware_6-6.5-189EFF?style=for-the-badge&logo=shopware&logoColor=white" alt="Shopware 6" />
  <img src="https://img.shields.io/badge/PHP-8.2-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP" />
  <img src="https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Docker-Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black" alt="React" />
  <img src="https://img.shields.io/badge/DSGVO-Compliant-34A853?style=for-the-badge&logo=shieldsdotio&logoColor=white" alt="DSGVO" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/license-Private-red?style=flat-square" alt="License" />
  <img src="https://img.shields.io/badge/status-Prototype-orange?style=flat-square" alt="Status" />
  <img src="https://img.shields.io/badge/MySQL-8.0-4479A1?style=flat-square&logo=mysql&logoColor=white" alt="MySQL" />
  <img src="https://img.shields.io/badge/Redis-7-DC382D?style=flat-square&logo=redis&logoColor=white" alt="Redis" />
  <img src="https://img.shields.io/badge/RabbitMQ-3-FF6600?style=flat-square&logo=rabbitmq&logoColor=white" alt="RabbitMQ" />
  <img src="https://img.shields.io/badge/OpenSearch-2-005EB8?style=flat-square&logo=opensearch&logoColor=white" alt="OpenSearch" />
</p>

---

## 📖 About The Project

The German pharmacy market is undergoing a digital transformation, yet most pharmacies still rely on legacy systems that fail to meet modern customer expectations for online ordering, real-time product availability, and data-privacy compliance.

**MediKiosk × Marien-Apotheke** is a headless e-commerce prototype developed as part of a real-world evaluation for the **Marien-Apotheke Köln**. It explores the viability of a decoupled, enterprise-grade commerce architecture purpose-built for the pharmacy sector — where **DSGVO (GDPR) compliance is non-negotiable** and operational reliability is critical.

### The Problem

- Traditional pharmacy software is monolithic, inflexible, and not designed for omnichannel retail.
- Pharmacies face strict German and EU data-privacy regulations (DSGVO / GDPR) that make off-the-shelf SaaS solutions risky.
- There is no established reference architecture for headless commerce in the regulated healthcare space.

### The Solution

This prototype decouples the **presentation layer** (Next.js) from the **commerce engine** (Shopware 6) via the Shopware Store API, enabling:

- Full control over the customer-facing UI/UX
- Backend independence — swap, scale, or extend without frontend disruption
- Regulatory-compliant data handling by design

---

## ✨ Key Features

| Feature                         | Description                                                                                              |
| ------------------------------- | -------------------------------------------------------------------------------------------------------- |
| 🏗️ **Headless Architecture**    | Complete separation of frontend (Next.js) and backend (Shopware 6) via REST / Store API                  |
| 🛡️ **DSGVO / GDPR Compliance**  | Privacy-by-design: cookie consent, data minimization, secure API communication                           |
| 🐳 **Fully Containerized**      | One-command Docker environment with all services (Shopware, MySQL, Redis, RabbitMQ, OpenSearch, Mailhog) |
| ⚡ **Server-Side Rendering**    | Next.js SSR for fast page loads, SEO optimization, and improved Core Web Vitals                          |
| 🔍 **Full-Text Search**         | OpenSearch integration for product discovery                                                             |
| 📨 **Async Processing**         | RabbitMQ message queue for background tasks (order processing, email notifications)                      |
| 🗄️ **High-Performance Caching** | Redis for session management and data caching                                                            |
| 🧪 **Testing Infrastructure**   | Jest + React Testing Library for frontend unit and integration tests                                     |

---

## 🛠️ Built With

### Frontend

| Technology                                    | Version | Purpose                               |
| --------------------------------------------- | ------- | ------------------------------------- |
| [Next.js](https://nextjs.org/)                | 16.x    | React framework with SSR & App Router |
| [React](https://react.dev/)                   | 19.x    | UI component library                  |
| [TypeScript](https://www.typescriptlang.org/) | 5.x     | Type-safe development                 |
| [Jest](https://jestjs.io/)                    | 30.x    | Testing framework                     |

### Backend

| Technology                                | Version    | Purpose                          |
| ----------------------------------------- | ---------- | -------------------------------- |
| [Shopware 6](https://www.shopware.com/)   | 6.5+       | Headless commerce engine & Admin |
| [PHP](https://www.php.net/)               | 8.2        | Server-side runtime              |
| [MySQL](https://www.mysql.com/) / MariaDB | 8.0 / 11.8 | Relational database              |

### Infrastructure

| Technology                                    | Version    | Purpose                    |
| --------------------------------------------- | ---------- | -------------------------- |
| [Docker](https://www.docker.com/)             | Compose v2 | Container orchestration    |
| [Redis](https://redis.io/)                    | 7 (Alpine) | Caching & session store    |
| [RabbitMQ](https://www.rabbitmq.com/)         | 3 (Alpine) | Message queue              |
| [OpenSearch](https://opensearch.org/)         | 2.x        | Full-text search engine    |
| [Mailhog](https://github.com/mailhog/MailHog) | latest     | Local email testing (SMTP) |

---

## 🏛️ Architecture Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                        DOCKER ENVIRONMENT                       │
│                                                                 │
│  ┌──────────────────┐          ┌──────────────────────────────┐ │
│  │                  │  REST /  │                              │ │
│  │   Next.js 16     │  Store   │     Shopware 6 (PHP 8.2)    │ │
│  │   Frontend       │◄────────►│     Commerce Engine          │ │
│  │                  │  API     │                              │ │
│  │  • SSR / SSG     │          │  • Product Catalog           │ │
│  │  • TypeScript    │          │  • Order Management          │ │
│  │  • React 19      │          │  • Customer Management       │ │
│  │  • Jest Tests    │          │  • Admin Panel               │ │
│  │                  │          │                              │ │
│  │  :3000           │          │  :8000 (HTTP) / :8443 (SSL)  │ │
│  └──────────────────┘          └──────────┬───────────────────┘ │
│                                           │                     │
│           ┌───────────────────────────────┼──────────────┐      │
│           │                               │              │      │
│    ┌──────▼──────┐  ┌────────────┐  ┌─────▼──────┐ ┌────▼───┐  │
│    │   MySQL /   │  │  RabbitMQ  │  │   Redis    │ │OpenSrch│  │
│    │   MariaDB   │  │  (Queue)   │  │  (Cache)   │ │(Search)│  │
│    │   :3306     │  │  :5672     │  │  :6379     │ │        │  │
│    └─────────────┘  └────────────┘  └────────────┘ └────────┘  │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

**Data Flow:**

1. The **Next.js frontend** renders pages server-side and communicates with Shopware 6 exclusively through the **Store API** (RESTful JSON endpoints).
2. **Shopware 6** handles all commerce logic — products, customers, orders, payments — and exposes data via its headless API.
3. **Redis** provides high-speed caching for sessions and frequently accessed data.
4. **RabbitMQ** handles asynchronous message processing (e.g., order confirmations, inventory updates).
5. **OpenSearch** powers the product search and filtering experience.
6. All services are orchestrated via **Docker Compose** on a shared bridge network (`medikiosk_network`).

---

## 🚀 Getting Started

Follow these steps to set up the project on your local development machine.

### Prerequisites

Ensure the following are installed on your system:

- **[Docker Desktop](https://www.docker.com/products/docker-desktop/)** (v4.0+ with Compose V2)
- **[Node.js](https://nodejs.org/)** (v18+ LTS recommended)
- **[Git](https://git-scm.com/)**

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/marien-apotheke.git
cd marien-apotheke
```

### 2. Start the Backend (Shopware 6 + Services)

```bash
cd backend
docker compose up -d
```

This will spin up the following containers:

| Container            | Service                  | Port                                      |
| -------------------- | ------------------------ | ----------------------------------------- |
| `medikiosk_shopware` | Shopware 6 Admin & API   | [localhost:8000](http://localhost:8000)   |
| `medikiosk_redis`    | Redis Cache              | `6379`                                    |
| `medikiosk_rabbitmq` | RabbitMQ + Management UI | [localhost:15672](http://localhost:15672) |
| `medikiosk_mailhog`  | Email Testing UI         | [localhost:8025](http://localhost:8025)   |
| `database`           | MariaDB 11.8             | `3306`                                    |
| `opensearch`         | OpenSearch 2.x           | `9200`                                    |

> **Default Shopware Admin Credentials:**
>
> - URL: `http://localhost:8000/admin`
> - Username: `admin`
> - Password: `shopware`

### 3. Initialize the Headless Sales Channel

Once Shopware is running, execute the initialization script to create the headless sales channel and configure API domains:

```bash
docker exec -it medikiosk_shopware bash /var/www/html/init_marien.sh
```

> ⚡ **Save the `SW-ACCESS-KEY`** printed at the end — you'll need it for the frontend configuration.

### 4. Configure & Start the Frontend

```bash
cd ../frontend
cp .env.local.example .env.local
```

Edit `.env.local` and add your Shopware access key:

```env
NEXT_PUBLIC_SHOPWARE_ACCESS_KEY=<YOUR_SW_ACCESS_KEY>
NEXT_PUBLIC_SHOPWARE_API_URL=http://localhost:8000
```

Install dependencies and start the development server:

```bash
npm install
npm run dev
```

The storefront will be available at **[http://localhost:3000](http://localhost:3000)**.

### 5. Verify the Setup

| Check                 | URL                                                        |
| --------------------- | ---------------------------------------------------------- |
| ✅ Frontend           | [http://localhost:3000](http://localhost:3000)             |
| ✅ Shopware Admin     | [http://localhost:8000/admin](http://localhost:8000/admin) |
| ✅ RabbitMQ Dashboard | [http://localhost:15672](http://localhost:15672)           |
| ✅ Mailhog            | [http://localhost:8025](http://localhost:8025)             |

---

## 🔒 Security & Compliance

This project was developed with **DSGVO (GDPR)** compliance as a foundational requirement, not an afterthought.

### Data Privacy (DSGVO / GDPR)

| Principle              | Implementation                                                                 |
| ---------------------- | ------------------------------------------------------------------------------ |
| **Data Minimization**  | Only essential customer data is collected and processed                        |
| **Purpose Limitation** | Data is used strictly for order fulfillment and legally required communication |
| **Storage Limitation** | Automated data retention policies are configured within Shopware               |
| **Right to Erasure**   | Shopware's built-in GDPR module supports customer data deletion requests       |
| **Cookie Consent**     | Frontend implements a DSGVO-compliant consent banner before any tracking       |

### Technical Security Measures

- **🔐 HTTPS Enforcement** — SSL/TLS transport encryption for all API communication
- **🔑 API Authentication** — Shopware Store API access keys with scoped permissions
- **🐳 Network Isolation** — Docker bridge network isolates services from the host
- **📧 Email Sandboxing** — Mailhog captures all outgoing emails in development (no real emails sent)
- **🚫 XDebug Disabled** — Debugging tools are disabled by default to prevent information leakage
- **🔒 Database Security** — MariaDB runs in strict mode with parameterized queries enforced by the Shopware ORM (DAL)

### Compliance Architecture

```
┌──────────────────────────────────────────────┐
│              COMPLIANCE LAYER                │
│                                              │
│  ┌────────────────┐  ┌────────────────────┐  │
│  │  Cookie Consent │  │  Data Encryption  │  │
│  │  (Frontend)     │  │  (TLS / at-rest)  │  │
│  └────────────────┘  └────────────────────┘  │
│                                              │
│  ┌────────────────┐  ┌────────────────────┐  │
│  │  GDPR Module   │  │  Audit Logging     │  │
│  │  (Shopware)    │  │  (Backend)         │  │
│  └────────────────┘  └────────────────────┘  │
│                                              │
│  ┌────────────────┐  ┌────────────────────┐  │
│  │  Network       │  │  Email Sandbox     │  │
│  │  Isolation     │  │  (Mailhog)         │  │
│  └────────────────┘  └────────────────────┘  │
└──────────────────────────────────────────────┘
```

---

## 📁 Project Structure

```
marien-apotheke/
├── frontend/                  # Next.js 16 storefront (TypeScript)
│   ├── src/                   # Application source code
│   ├── public/                # Static assets
│   ├── jest.config.ts         # Test configuration
│   └── package.json           # Dependencies & scripts
│
├── backend/                   # Shopware 6 commerce engine
│   ├── custom/plugins/        # Custom Shopware plugins
│   ├── config/                # Shopware configuration
│   ├── docker-compose.yml     # Backend service orchestration
│   └── composer.json          # PHP dependencies
│
├── docs/                      # Project documentation
│   ├── 00_governance/         # Build Playbook (SSoT)
│   ├── 01_requirements/       # Sprint task breakdowns
│   └── 07_wireframes/         # UI/UX wireframes
│
├── .github/workflows/         # CI/CD pipeline
├── docker-compose.yml         # Root-level compose (alternative)
├── init_marien.sh             # Headless channel initialization script
└── README.md
```

---

## 📜 Available Scripts

### Frontend

```bash
npm run dev          # Start Next.js development server
npm run build        # Create production build
npm run start        # Serve production build
npm run lint         # Run ESLint checks
npm run lint:fix     # Auto-fix linting issues
npm run format       # Format code with Prettier
npm run test         # Run Jest test suite
npm run type-check   # TypeScript type validation
```

### Backend (Docker)

```bash
docker compose up -d       # Start all backend services
docker compose down        # Stop all services
docker compose logs -f     # Stream container logs
docker compose ps          # View running containers
```

---

## 📄 Documentation

| Document                    | Path                                              |
| --------------------------- | ------------------------------------------------- |
| **Build Playbook (SSoT)**   | `docs/00_governance/Build_Playbook.md`            |
| **Sprint 1 Task Breakdown** | `docs/01_requirements/Sprint_1_Task_Breakdown.md` |
| **UI/UX Wireframes**        | `docs/07_wireframes/`                             |

---

## 👤 Author & Contact

**Aseel Marwan Kheder**
IT-Support Specialist & Web Developer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/aseel-marwan-kheder-36b17033b/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/aseel7marwan)

📧 **Email:** [kontakt@aseelmarwan.de](mailto:kontakt@aseelmarwan.de)

<p align="center">
  <sub>Built with ❤️ using Next.js, Shopware 6, and Docker</sub>
</p>
