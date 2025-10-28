# SmartCart

## Overview

SmartCart is an AI-powered e-commerce platform designed to offer personalized shopping experiences. It leverages Google's Gemini AI for intelligent product recommendations based on user behavior and browsing patterns. Key features include product browsing, wishlist management, automated price tracking with notifications, real-time price comparison, comprehensive shopping list and budget planning tools, **advanced product comparison**, **similar products discovery**, **AI-powered natural language search**, and enhanced search filters with brand filtering. The platform aims to enhance the online shopping experience by providing smart insights and saving users time and money.

## Recent Changes (October 22, 2025)

### New Features Implemented

1. **Enhanced Search Filters (Task 1)**
   - Brand extraction from product sources with chip-based UI
   - Improved filter sidebar with "Clear All" functionality
   - Fixed critical state management bug where price slider dropped brand selections
   - All filter callbacks now preserve the brands array

2. **Similar Products Feature (Task 2)**
   - Database queries filter by same category and similar price range (±20%)
   - Carousel UI on product detail pages showing 6-8 similar items
   - Excludes current product from results
   - Seamless navigation between related products

3. **Product Comparison System (Task 3)**
   - Centralized state management via React Context (ComparisonProvider)
   - Compare up to 4 products side-by-side
   - Comparison table shows: prices, savings, ratings, reviews
   - Visual indicators for best values (lowest price, highest rating)
   - Shareable URLs via clipboard
   - LocalStorage persistence across sessions
   - Floating "Compare" button on Home page when products selected
   - Individual and bulk removal options

4. **AI Natural Language Search (Task 4)**
   - Gemini AI parses natural language queries into structured filters
   - Examples: "best budget laptop under $500" → auto-applies category, price, sort
   - "gaming headphones with good reviews" → extracts keywords, min rating
   - Smart fallback when Gemini unavailable (preserves all search terms)
   - Preserves existing user filters when AI can't enhance
   - Toast notifications indicate AI status and filter preservation
   - Sparkles icon button triggers smart search

### Technical Improvements

- **State Management**: Migrated comparison from independent useState hooks to shared Context provider for cross-component reactivity
- **Error Handling**: Graceful degradation when Gemini API unavailable
- **Filter Preservation**: Smart search preserves user filters when AI doesn't provide enhancements
- **UX Enhancements**: Clear visual feedback via toast notifications for all AI operations

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

The frontend is built with **React 18** and **TypeScript**, using **Vite** for fast development and optimized builds. **Wouter** handles client-side routing. The UI is constructed using **Radix UI** primitives and styled with **Tailwind CSS**, following a **shadcn/ui** "new-york" style component architecture. **TanStack Query** manages server state, caching, and data fetching, while an **AuthProvider** handles authentication state. The design system supports light/dark themes, uses Inter and Manrope fonts, and follows a mobile-first responsive approach.

### Backend Architecture

The backend utilizes **Express.js** for API routing and HTTP server operations. **Passport.js** provides email/password authentication with session management via `express-session`. **PostgreSQL**, accessed through **Drizzle ORM** (and Neon serverless driver), serves as the primary database, storing users, products, wishlists, notifications, price history, shopping lists, and budgets. **Node-cron** schedules automated price tracking, and **Nodemailer** sends email notifications. The API is RESTful, with **Zod** for validation and consistent JSON error handling.

### AI Integration

**Google Gemini AI** (specifically Gemini 2.5 Flash) is integrated for generating personalized product recommendations. It analyzes user interests from wishlists and browsing history, providing structured JSON outputs with reasons and search keywords.

### System Design Choices

- **Data Persistence**: Full migration to PostgreSQL ensures all user and product data persists across sessions and server restarts.
- **Security**: Implemented secure password hashing (bcrypt), protected routes via authentication middleware, `sanitizeUser()` for password stripping, and Zod validation for input integrity.
- **Real-Time Data**: Integration with SerpAPI provides real product data, prices, and images from Google Shopping.
- **Notifications**: Automated email notifications for price drops and budget alerts enhance user engagement.
- **Search & Filtering**: Advanced search with URL parameter support, category filtering, price range, and rating filters, along with sorting options.
- **Responsive Design**: All components, including navigation, footer, and product displays, are designed to be responsive across devices.

## External Dependencies

### Third-Party APIs

-   **SerpAPI**: Fetches real-time product data from Google Shopping.
-   **Google Gemini API**: Provides AI-powered product recommendations.
-   **Neon Database**: Serverless PostgreSQL database solution.

### UI Component Libraries

-   **Radix UI**: Provides accessible, unstyled UI primitives.
-   **shadcn/ui**: Offers pre-built, customizable React components.
-   **Recharts**: Used for data visualization, specifically for price history graphs.

### Development Tools

-   **TypeScript**: For type-safe development.
-   **Vite**: Frontend build tool.
-   **Drizzle ORM**: Type-safe ORM for PostgreSQL.
-   **Drizzle Kit**: Database migration and schema management.
-   **node-cron**: For scheduling tasks.
-   **Nodemailer**: For sending emails.

### Font Delivery

-   **Google Fonts**: Inter and Manrope font families.