# 🛍️ Enflyze

**Enflyze** is a modern multi-tenant e-commerce platform where every user can launch their own online store, manage products, and securely receive payments through **Stripe Connect**.  
Built with **Next.js 15**, **Payload CMS**, **tRPC**, **MongoDB**, and **Stripe**, Enflyze provides a scalable and customizable foundation for marketplaces and SaaS-based commerce systems.

---

## 🚀 Features

### ⚙️ Core
- **Multi-tenant architecture** – each store (tenant) is isolated and secure  
- **Subdomain routing** – `tenant.enflyze.com` URLs for each shop  
- **Stripe Connect integration** – merchants can directly link and verify their Stripe accounts  
- **Payload CMS admin panel** – manage Users, Products, Tenants, Orders, Reviews, and Media  
- **Lexical rich text editor** – advanced editing for product descriptions and content fields  

### 💸 Commerce
- **Product management** – create, update, archive (soft delete), and hide products  
- **Stripe checkout flow** – fully secure payment handling with redirect success flow  
- **Cart system** – global Zustand state management for a seamless user experience  
- **Order tracking** – users can view their purchase history  
- **Review system** – integrated product reviews and ratings from verified buyers  

### 🧩 Multi-Tenant
- **Tenant creation flow** – automatic tenant creation during user registration  
- **Stripe verification** – tenants can verify their accounts directly from the dashboard  
- **Tenant isolation** – each tenant only accesses their own data  
- **Super-admin role** – global access across all tenants for system administrators  

### 🧠 Developer Experience
- **tRPC integration** – end-to-end type-safe API layer  
- **React Query + Infinite Loading** – fast, cached product and tag fetching  
- **NUQS filters** – URL-synced min/max price filters  
- **Next.js Server Components + Suspense** – optimized SSR and streaming rendering  
- **Shadcn/UI components** – clean, accessible design system  
- **TypeScript + Zod validation** – full type safety and runtime schema checks  

---

## 🏗️ Tech Stack

| Layer | Technology |
|--------|-------------|
| **Frontend** | Next.js 15, React 19, TailwindCSS 4, Shadcn/UI |
| **Backend** | Payload CMS 3.57, tRPC, Lexical Editor |
| **Database** | MongoDB (via `@payloadcms/db-mongodb`) |
| **Payments** | Stripe Connect |
| **Auth** | Payload built-in auth system |
| **State Management** | Zustand, React Query |
| **Hosting** | Vercel (Wildcard Subdomain Routing) |
| **Language** | TypeScript (Strict mode) |

---

## 🌐 Domain Structure

| Environment | Domain | Description |
|--------------|---------|-------------|
| **Main App** | `https://enflyze.com` | Landing & marketing site |
| **Tenant Stores** | `https://{tenant}.enflyze.com` | Each tenant’s shop |
| **CMS Admin Panel** | `https://enflyze.com/admin` | Payload admin dashboard |

**DNS Setup Example**

Host: *.enflyze.com
Type: CNAME
Value: your-vercel-domain.vercel.app


---

## ⚡️ Installation

```bash
# Clone the repository
git clone https://github.com/barankilicci/e-nflyze.git
cd e-nflyze

# Install dependencies
bun install

# Create environment file
cp .env.example .env

# 🔑 Environment Variables

NEXT_PUBLIC_APP_URL=http://localhost:3000
NEXT_PUBLIC_ROOT_DOMAIN=enflyze.com
NEXT_PUBLIC_ENABLE_SUBDOMAIN_ROUTING=true

PAYLOAD_SECRET=supersecret
DATABASE_URI=mongodb+srv://...
STRIPE_SECRET_KEY=sk_test_...
STRIPE_WEBHOOK_SECRET=whsec_...

# 🧠 Development

# Generate Payload types
bun run payload:types

# Generate import map for custom admin components
bun run payload:importmap

# Start the development server
bun run dev

🪶 License

MIT © Baran Kılıçcı