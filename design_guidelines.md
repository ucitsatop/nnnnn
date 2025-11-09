# Design Guidelines: Agricultural Farm Management Platform

## Design Approach

**System Selected**: Material Design with Agricultural Theme Customization
**Rationale**: This platform is utility-focused with complex data visualization, monitoring dashboards, and information-dense interfaces. Material Design provides robust patterns for data-heavy applications while allowing thematic customization for agricultural context.

**Visual Identity**: Modern agricultural aesthetic combining technology and nature - clean interfaces with organic accents, data visualization with natural textures, professional yet approachable.

---

## Typography System

**Font Families** (via Google Fonts):
- **Primary**: Inter (400, 500, 600, 700) - UI elements, data, forms
- **Display**: Poppins (600, 700) - Headers, hero sections

**Type Scale**:
- Hero/Display: text-4xl to text-6xl (Poppins)
- Page Headers: text-3xl (Poppins)
- Section Headers: text-2xl (Inter Semi-bold)
- Card Titles: text-xl (Inter Medium)
- Body Text: text-base (Inter Regular)
- Captions/Labels: text-sm (Inter Regular)
- Metadata: text-xs (Inter Regular)

---

## Layout System

**Spacing Primitives**: Use Tailwind units of 2, 4, 6, 8, 12, 16 for consistent rhythm
- Tight spacing: p-2, gap-2 (form elements, chips)
- Standard spacing: p-4, gap-4 (cards, list items)
- Comfortable spacing: p-6, gap-6 (sections within cards)
- Section padding: py-12 to py-16 (page sections)
- Large gaps: gap-8, gap-12 (between major sections)

**Grid System**:
- Dashboard: 12-column responsive grid
- Desktop: grid-cols-1 lg:grid-cols-3 xl:grid-cols-4 for stat cards
- Maps/Monitoring: Full-width with sidebar (2/3 main + 1/3 sidebar)
- Forms: max-w-2xl centered containers

**Container Widths**:
- Dashboard content: max-w-7xl
- Forms/Settings: max-w-4xl
- Narrow content: max-w-2xl

---

## Component Library

### Navigation Architecture

**Burger Menu System**:
- Fixed header with burger icon (left side)
- On activation: Dual sliding panels (left: primary nav, right: quick actions/notifications)
- Left panel width: 320px with smooth slide animation
- Right panel width: 280px
- Semi-transparent overlay when panels open

**Header Bar**:
- Height: h-16
- Contains: Logo, Burger menu, Language switcher (RU/KZ/EN flags), Profile avatar
- Sticky positioning with subtle shadow on scroll

### Main Dashboard Layout

**Hero Section** (Main Dashboard Landing):
- Height: 60vh minimum
- Contains: Welcome message, AI Chatbot interface (center-aligned), Quick stats grid below
- Background: Subtle agricultural imagery (fields, crops) with overlay for readability

**AI Chatbot Component**:
- Prominent placement on dashboard
- Floating card design (max-w-3xl, centered)
- Voice input button (large, circular, microphone icon)
- Voice output indicator (waveform animation during speech)
- Suggested questions as chips below input (2-3 visible, scrollable)
- Chat history scrollable area above input (max-h-96)
- Message bubbles: user (right-aligned), bot (left-aligned)

### Farm Map Interface

**Interactive Map Component**:
- Full-width map container (min-h-screen)
- Left sidebar (w-80): Field list, filters, current selection details
- Map controls: Zoom, layer toggle, measurement tools (top-right overlay)
- Field polygons: Clickable with hover states
- Selected field: Highlighted with details panel overlay (bottom-right)
- Weather widget overlay (top-left): Current conditions, 5-day forecast

### Monitoring Dashboards

**Plant/Animal Health Cards**:
- Grid layout: grid-cols-1 md:grid-cols-2 xl:grid-cols-3
- Each card: Image/icon, Name, Status indicator (chip), Key metrics, "View Details" action
- Status indicators: Chips with icons (healthy, attention needed, critical)
- Filter bar above grid: Search, category filters, sort options

**Health Detail View**:
- Two-column layout: Image gallery (left), Data panel (right)
- Chip/Tag display: ID number, registration date
- Timeline of health records (vertical, chronological)
- Employee data entries: Name, date, notes, attached images
- Action buttons: Add Entry, Schedule Check, Generate Report

### Statistics & Analytics

**Yield Statistics Pages**:
- Tab navigation: By Crop Type / By Animal Type
- Summary cards row: Total yield, Average per unit, Trend indicator
- Main chart area: Line/bar charts (full-width, min-h-96)
- Chart controls: Date range selector, export data button
- Comparison table below charts: Sortable columns, expandable rows

### Soil Suitability Module

**Assessment Interface**:
- Split view: Map (left 2/3) + Results panel (right 1/3)
- Map: Clickable regions with soil type overlays
- Results panel: Suitability scores (0-100), Crop recommendations list, Improvement suggestions
- Color-coded suitability: Visual scale representation

### Weather System

**Country/Region Selection**:
- Dropdown with search functionality
- Saved locations as quick-access chips
- Weather cards: grid-cols-1 md:grid-cols-2 lg:grid-cols-3
- Each card: Location name, Current conditions (large icon + temp), Hourly forecast (horizontal scroll), 7-day forecast

### Profile Management

**Profile Page Layout**:
- Header section: Large avatar (center), Name, Role
- Avatar selection: Grid of preset options (grid-cols-4 md:grid-cols-6), Radio button selection pattern
- Edit form: Two-column on desktop, stacked on mobile
- Fields: Name, Email, Phone, Role, Farm location, Language preference
- Save/Cancel buttons: Sticky bottom bar on mobile

### Reviews Section

**Reviews Page**:
- Review submission card (top): Star rating selector, Text area (min 3 rows), Name (optional), Submit button
- Reviews list: Card-based layout, infinite scroll
- Each review card: Star rating, Date, Author name (or "Anonymous"), Review text, Helpful counter

### Resource Management

**Resource Dashboard**:
- Category tabs: Equipment, Water, Fertilizers, Feed
- Inventory cards with progress bars (current/total capacity)
- Action buttons: Add Resource, Allocate, View History
- Allocation interface: Drag-and-drop or form-based field assignment

---

## Images

**Hero Image**: Agricultural landscape - aerial view of organized crop fields with irrigation systems, modern farming equipment visible. Conveys scale and technology integration. Use as background with subtle overlay (opacity-60 to opacity-70) for text readability.

**Dashboard Accent Images**: 
- Field monitoring cards: Close-up crop imagery
- Animal health cards: High-quality animal photography
- Weather widgets: Atmospheric sky imagery matching conditions

**Profile Avatars**: Collection of 12-15 agricultural-themed avatar options (illustrated or photographic style) - farmers, agronomists, various demographics.

---

## Interaction Patterns

**Voice Interface Indicators**:
- Recording: Pulsing red circle around mic button
- Processing: Spinner with "Listening..." text
- Speaking: Waveform animation with "AI is speaking..."

**Loading States**:
- Skeleton screens for data-heavy components
- Shimmer effect during load
- Progress indicators for multi-step operations

**Empty States**:
- Illustrative icons with helpful messages
- Primary action button to add first item
- Educational text about feature benefits

---

## Responsive Behavior

**Mobile Adaptations**:
- Burger menu: Single panel (full-width overlay)
- Stat grids: Stack to single column
- Map interface: Tabs for Map/List view toggle
- Charts: Horizontal scroll for wide data
- Voice interface: Bottom sheet modal on mobile

**Touch Targets**: Minimum 44px height for all interactive elements