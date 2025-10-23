# 🍽️ Raha MVP - Restaurant Delivery Platform

## 📂 Project Structure

```
raha/
├── apps/
│   ├── dashboard/                 # Restaurant management dashboard
│   │   ├── src/
│   │   │   ├── components/       # Reusable UI components
│   │   │   ├── pages/           # Dashboard pages
│   │   │   ├── hooks/           # Custom React hooks
│   │   │   ├── services/        # API services
│   │   │   ├── store/           # State management (Zustand)
│   │   │   └── utils/           # Helper functions
│   │   ├── public/
│   │   └── package.json
│   │
│   ├── widget/                   # Embeddable ordering widget
│   │   ├── src/
│   │   │   ├── components/       # Widget components
│   │   │   ├── hooks/           # Widget-specific hooks
│   │   │   ├── services/        # Widget API calls
│   │   │   └── utils/           # Widget utilities
│   │   ├── dist/                # Built widget files
│   │   └── package.json
│   │
│   └── public-site/             # Generated restaurant mini-sites
│       ├── src/
│       │   ├── components/      # Public site components
│       │   ├── pages/          # Dynamic pages
│       │   └── utils/          # Site generation utils
│       └── package.json
│
├── functions/                    # Serverless backend functions
│   ├── src/
│   │   ├── orders/             # Order management
│   │   ├── restaurants/        # Restaurant CRUD
│   │   ├── menus/              # Menu management
│   │   ├── payments/           # Stripe integration
│   │   ├── webhooks/           # Webhook handlers
│   │   └── utils/              # Shared utilities
│   └── package.json
│
├── shared/                      # Shared types and utilities
│   ├── types/                  # TypeScript definitions
│   ├── utils/                  # Shared utilities
│   └── constants/              # App constants
│
├── supabase/                    # Database migrations and config
│   ├── migrations/
│   ├── seed.sql
│   └── config.toml
│
├── docs/                       # Documentation
├── .env.example
├── package.json                # Root package.json
└── README.md
```

---

## ✅ Phase 1 — Setup & Architecture

### 📋 Repository & Environment Setup
- [ ] Initialize monorepo with pnpm workspaces
- [ ] Setup Vite + React + TypeScript for dashboard app
- [ ] Setup Vite + React + TypeScript for widget app
- [ ] Setup Vite + React + TypeScript for public-site app
- [ ] Configure TailwindCSS for all apps
- [ ] Setup ESLint + Prettier configuration
- [ ] Create .env.example with all required environment variables
- [ ] Setup Git hooks with Husky for code quality

### 🗄️ Database Schema Design
- [ ] Design restaurants table (id, name, slug, logo_url, theme_config, contact_info, settings)
- [ ] Design menu_categories table (id, restaurant_id, name, sort_order, is_active)
- [ ] Design menu_items table (id, category_id, name, description, price, image_url, is_available, sort_order)
- [ ] Design orders table (id, restaurant_id, customer_info, items, total, status, payment_intent_id)
- [ ] Design users table (id, email, role, restaurant_id, profile_data)
- [ ] Design themes table (id, name, config, is_default)
- [ ] Design payment_accounts table (id, restaurant_id, stripe_account_id, is_verified)
- [ ] Create database migrations in Supabase
- [ ] Setup Row Level Security (RLS) policies
- [ ] Create seed data for development

### 🔐 Authentication & Roles
- [ ] Setup Supabase Auth with email/password
- [ ] Configure user roles (admin, restaurant_owner, customer)
- [ ] Create auth middleware for protected routes
- [ ] Setup JWT token handling
- [ ] Create user registration flow with role selection
- [ ] Implement password reset functionality

### ⚙️ Environment & Configuration
- [ ] Setup Supabase project and get API keys
- [ ] Configure Stripe Connect for marketplace payments
- [ ] Setup Resend for email notifications
- [ ] Configure OpenStreetMap/Mapbox for distance calculations
- [ ] Setup Vercel deployment configuration
- [ ] Setup Cloudflare Workers for backend functions
- [ ] Create environment variable validation

---

## ✅ Phase 2 — Restaurant Dashboard

### 🎨 UI Foundation
- [ ] Create responsive layout with sidebar navigation
- [ ] Setup component library (Button, Input, Modal, Card, etc.)
- [ ] Implement dark/light theme toggle
- [ ] Create loading states and error boundaries
- [ ] Setup form validation with react-hook-form + zod
- [ ] Create toast notification system

### 🔑 Authentication UI
- [ ] Design login/signup pages
- [ ] Create restaurant onboarding flow
- [ ] Build profile setup wizard
- [ ] Implement password reset UI
- [ ] Create role-based navigation

### 🍽️ Menu Builder
- [ ] Create menu categories management (CRUD)
- [ ] Build menu items editor with image upload
- [ ] Implement drag-and-drop reordering (react-beautiful-dnd)
- [ ] Add bulk actions (enable/disable, delete multiple)
- [ ] Create menu preview component
- [ ] Add menu item variants (sizes, add-ons)
- [ ] Implement image optimization and resizing

### 🎨 Site Customizer
- [ ] Create theme picker with color customization (react-color)
- [ ] Build logo upload with preview
- [ ] Design hero section editor
- [ ] Create about section editor
- [ ] Add contact information management
- [ ] Implement live preview of customizations
- [ ] Create theme templates selection

### 📦 Orders Management
- [ ] Build orders list with real-time updates
- [ ] Create order details modal
- [ ] Implement order status management (pending, confirmed, preparing, ready, completed)
- [ ] Add order filtering and search
- [ ] Create order analytics dashboard
- [ ] Implement order notifications

### ⚙️ Settings & Integration
- [ ] Create Stripe Connect onboarding flow
- [ ] Build delivery settings (zones, fees, minimum order)
- [ ] Add restaurant profile management
- [ ] Create notification preferences
- [ ] Implement data export functionality

---

## ✅ Phase 3 — Customer Widget (Embeddable Ordering)

### 📦 Widget Core
- [ ] Create lightweight widget loader script
- [ ] Build iframe-based widget container
- [ ] Implement responsive design (mobile-first)
- [ ] Add widget configuration options
- [ ] Create widget initialization API
- [ ] Setup cross-origin communication

### 🍽️ Menu Display
- [ ] Fetch and display restaurant menu
- [ ] Create category navigation
- [ ] Build menu item cards with images
- [ ] Implement search and filtering
- [ ] Add item availability indicators
- [ ] Create loading and error states

### 🛒 Cart & Checkout
- [ ] Build shopping cart with add/remove items
- [ ] Create cart summary with totals
- [ ] Implement customer information form
- [ ] Add delivery address collection
- [ ] Create order review page
- [ ] Build checkout flow with Stripe

### 💳 Payment Integration
- [ ] Integrate Stripe Elements for card input
- [ ] Handle payment processing
- [ ] Create payment success/failure handling
- [ ] Implement order confirmation
- [ ] Add payment method validation

### 📱 Mobile Optimization
- [ ] Ensure touch-friendly interactions
- [ ] Optimize for small screens
- [ ] Implement swipe gestures
- [ ] Add mobile-specific UI patterns
- [ ] Test on various devices

---

## ✅ Phase 4 — Backend APIs & Logic (Serverless)

### 🍽️ Restaurant Management APIs
- [ ] Create restaurant CRUD endpoints
- [ ] Build menu management APIs
- [ ] Implement theme customization APIs
- [ ] Create restaurant settings endpoints
- [ ] Add restaurant search and discovery

### 📦 Order Management APIs
- [ ] Create order placement endpoint
- [ ] Build order status update APIs
- [ ] Implement order history retrieval
- [ ] Create order cancellation logic
- [ ] Add order validation and business rules

### 💳 Payment Integration
- [ ] Setup Stripe Connect for marketplace
- [ ] Create payment intent generation
- [ ] Implement payment confirmation
- [ ] Build refund processing
- [ ] Add payment dispute handling

### 🔔 Webhooks & Notifications
- [ ] Setup Stripe webhook handlers
- [ ] Create order notification system
- [ ] Implement email notifications (Resend)
- [ ] Add SMS notifications (optional)
- [ ] Build real-time updates (Supabase Realtime)

### 📊 Analytics & Reporting
- [ ] Track order metrics
- [ ] Create sales analytics
- [ ] Implement customer insights
- [ ] Build performance monitoring
- [ ] Add error tracking and logging

---

## ✅ Phase 5 — Site Builder Output

### 🌐 Mini-Site Generation
- [ ] Create dynamic page generation system
- [ ] Build SEO-friendly URL structure
- [ ] Implement meta tags and Open Graph
- [ ] Create sitemap generation
- [ ] Add robots.txt configuration

### 🎨 Theme Rendering
- [ ] Build theme engine for custom sites
- [ ] Create responsive layout templates
- [ ] Implement custom CSS injection
- [ ] Add font and color customization
- [ ] Create mobile-optimized layouts

### 🔍 SEO & Performance
- [ ] Implement structured data (JSON-LD)
- [ ] Add page speed optimization
- [ ] Create image optimization
- [ ] Implement caching strategies
- [ ] Add analytics tracking

### 📱 Public Ordering
- [ ] Integrate widget into public sites
- [ ] Create public menu pages
- [ ] Add restaurant information pages
- [ ] Implement contact forms
- [ ] Create social media integration

---

## 🧩 Recommended Libraries

### Frontend
- **UI Components:** Headless UI, Radix UI, or Chakra UI
- **Forms:** React Hook Form + Zod validation
- **Drag & Drop:** React Beautiful DnD
- **Color Picker:** React Color
- **Icons:** Lucide React or Heroicons
- **State Management:** Zustand or Redux Toolkit
- **HTTP Client:** Axios or Fetch API
- **Date Handling:** Day.js or date-fns

### Backend
- **Serverless:** Cloudflare Workers or Vercel Functions
- **Database:** Supabase (PostgreSQL)
- **Payments:** Stripe Connect
- **Email:** Resend or Postmark
- **Maps:** Mapbox or OpenStreetMap
- **Real-time:** Supabase Realtime or Pusher

### Development
- **Build Tool:** Vite
- **Styling:** TailwindCSS
- **TypeScript:** Full type safety
- **Testing:** Vitest + Testing Library
- **Linting:** ESLint + Prettier
- **Deployment:** Vercel (frontend) + Cloudflare (backend)

---

## 💡 Optional Enhancements

### 🎯 Advanced Features
- [ ] **Coupon System:** Discount codes and promotional offers
- [ ] **Delivery Tracking:** Real-time order tracking with maps
- [ ] **Analytics Dashboard:** Advanced reporting and insights
- [ ] **AI Menu Suggestions:** Smart recommendations for menu items
- [ ] **Multi-language Support:** Internationalization
- [ ] **Loyalty Program:** Customer rewards and points
- [ ] **Inventory Management:** Stock tracking and alerts
- [ ] **Staff Management:** Employee accounts and permissions
- [ ] **Advanced Theming:** Custom CSS and branding
- [ ] **API Documentation:** Public API for integrations

### 🚀 Performance & Scale
- [ ] **CDN Integration:** Global content delivery
- [ ] **Caching Layer:** Redis for improved performance
- [ ] **Database Optimization:** Query optimization and indexing
- [ ] **Image CDN:** Cloudinary or similar for image optimization
- [ ] **Monitoring:** Application performance monitoring
- [ ] **Error Tracking:** Sentry or similar for error monitoring

### 🔒 Security & Compliance
- [ ] **PCI Compliance:** Enhanced payment security
- [ ] **GDPR Compliance:** Data protection and privacy
- [ ] **Rate Limiting:** API protection
- [ ] **Audit Logging:** Security event tracking
- [ ] **Two-Factor Authentication:** Enhanced security
- [ ] **Data Encryption:** End-to-end encryption

---

## 🎯 Development Guidelines

### Code Quality
- Write TypeScript for type safety
- Use ESLint and Prettier for consistent code formatting
- Write unit tests for critical business logic
- Follow React best practices and hooks patterns
- Implement proper error handling and loading states

### UX Principles
- Mobile-first responsive design
- Intuitive navigation and user flows
- Clear visual hierarchy and typography
- Accessible components (WCAG 2.1 AA)
- Fast loading and smooth interactions

### Security
- Validate all user inputs
- Implement proper authentication and authorization
- Use HTTPS for all communications
- Follow OWASP security guidelines
- Regular security audits and updates

This comprehensive plan provides a solid foundation for building your Raha MVP while keeping each task manageable and actionable. Each phase builds upon the previous one, ensuring a logical development progression.
