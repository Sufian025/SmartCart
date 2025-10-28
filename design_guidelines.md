# SmartCart - Design Guidelines

## Design Approach

**Reference-Based Approach** drawing from modern e-commerce leaders:
- **Primary Inspiration**: Shopify's clean, product-focused interface
- **Secondary Influence**: Amazon's efficient product browsing patterns
- **AI Touch**: Modern AI assistant aesthetics (clean, conversational)

**Key Principles**: 
- Product-first visual hierarchy
- Trust-building through clarity and consistency
- Seamless AI integration without overwhelming users
- Action-oriented design for quick shopping decisions

## Core Design Elements

### A. Color Palette

**Light Mode:**
- Primary: 220 70% 50% (Trustworthy blue for CTAs and interactive elements)
- Surface: 0 0% 100% (Pure white for product cards and main background)
- Background: 220 15% 97% (Subtle warm gray for page background)
- Text Primary: 220 20% 15% (Deep charcoal for readability)
- Text Secondary: 220 15% 45% (Medium gray for supporting text)
- Success: 140 60% 45% (Price drop notifications)
- Border: 220 15% 88% (Soft dividers)

**Dark Mode:**
- Primary: 220 80% 60% (Brighter blue for dark backgrounds)
- Surface: 220 20% 12% (Elevated card surface)
- Background: 220 25% 8% (Deep background)
- Text Primary: 220 15% 95% (Soft white)
- Text Secondary: 220 10% 65% (Muted gray)
- Success: 140 55% 55% (Accessible green)
- Border: 220 20% 20% (Subtle separation)

### B. Typography

**Font Families:**
- Primary: Inter (Google Fonts) - Clean, modern sans-serif for UI and body text
- Display: Manrope (Google Fonts) - Bold, confident for product titles and headings

**Scale:**
- Headings: font-bold, text-2xl to text-5xl (product names, section headers)
- Body: font-normal, text-base to text-lg (descriptions, details)
- Captions: font-medium, text-sm to text-xs (prices, metadata, labels)
- AI Assistant: font-medium with slightly increased letter-spacing for conversational feel

### C. Layout System

**Spacing Primitives**: Consistent use of Tailwind units: 2, 4, 6, 8, 12, 16, 20, 24
- Component padding: p-4 to p-6 (cards, buttons)
- Section spacing: py-12 to py-20 (between major sections)
- Grid gaps: gap-4 to gap-6 (product grids, card layouts)
- Container max-width: max-w-7xl (main content area)

**Grid System:**
- Product Grid: grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4
- Wishlist View: grid-cols-1 md:grid-cols-2 lg:grid-cols-3
- Mobile-first responsive with breakpoint consistency

### D. Component Library

**Navigation:**
- Sticky top header with search bar prominence
- Quick access to: Home, Wishlist, Notifications, Profile
- Search bar with AI suggestion preview on focus
- Shopping cart icon with badge counter

**Product Cards:**
- Product image with 4:3 aspect ratio, subtle hover lift effect
- Product title (2 lines max with ellipsis)
- Price display (current + original if discounted)
- Rating stars with review count
- Quick "Add to Wishlist" heart icon (outline/filled states)
- "View Details" CTA button on hover

**AI Recommendation Panel:**
- Conversational card design with subtle gradient background
- "Why we recommend this" explanation text
- Horizontal scrolling product suggestions
- Dismissible recommendations with thumbs up/down feedback

**Wishlist Interface:**
- Grid view with larger product cards
- Price history mini-chart (sparkline) for each item
- "Price dropped" badge with percentage saved
- Bulk action toolbar (remove multiple, share list)

**Notification Center:**
- Slide-out panel from top-right
- Notification cards with icons (price drop, new recommendation)
- Read/unread states with subtle background differentiation
- "Mark all as read" quick action

**Price Drop Alerts:**
- Toast notifications in bottom-right corner
- Email template with product image and price comparison
- Notification badge on bell icon in header

**Filters & Search:**
- Left sidebar filters (category, price range, ratings) on desktop
- Bottom sheet filters on mobile
- Active filter chips with clear-all option
- Sort dropdown (relevance, price, rating)

**Forms & Inputs:**
- Rounded input fields with focus ring states
- Floating labels for text inputs
- Toggle switches for notification preferences
- Multi-select dropdowns for categories

### E. Visual Enhancements

**Micro-interactions:**
- Wishlist heart animation (subtle bounce on add)
- Loading skeleton screens for product grids
- Smooth transitions between filter states (300ms ease)
- Price drop celebration animation (confetti or sparkle effect)

**Imagery Strategy:**
- Hero Section: Feature lifestyle image showing happy shopping experience or AI assistant visualization (1200x600px minimum)
- Product Images: High-quality, consistent white backgrounds
- Empty States: Friendly illustrations for empty wishlist, no search results
- AI Avatar: Modern gradient icon or abstract geometric representation

**Trust Elements:**
- Verified seller badges on product cards
- Secure checkout indicators
- "Price match guarantee" messaging where relevant
- Customer review highlights with verified purchase tags

## Images

**Hero Image**: Large, aspirational lifestyle shot showing someone using the shopping assistant on multiple devices (desktop + mobile), warm and inviting environment. Alternative: Abstract visualization of AI connecting shoppers to perfect products (interconnected nodes, product icons flowing to happy customer).

**Product Placeholders**: Use high-quality stock product photography with consistent white or subtle gradient backgrounds. Categories should include electronics, fashion, home goods, beauty.

**Empty State Illustrations**: Custom illustrations showing friendly character with empty shopping bag for wishlist, magnifying glass with question mark for no results, bell with checkmark for all notifications read.

**AI Assistant Visual**: Gradient orb or geometric shape that pulses subtly, positioned in recommendation cards and onboarding screens.