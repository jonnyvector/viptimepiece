# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

**Primary Development Server:**
```bash
npm run dev
```
- Runs `shopify theme dev --store=viptimepiece.myshopify.com --theme=180236386621`
- Connects to the live Shopify store for theme development
- Requires Shopify CLI authentication first

**Authentication:**
- Use `shopify auth` commands to authenticate with Shopify before running dev server
- Theme ID 180236386621 is the staging theme

## Theme Architecture

**Base Theme:** Symmetry v8.0.0 by Clean Canvas
- This is a customized version of the Symmetry theme for VIP Timepiece

**Core Structure:**
- `layout/theme.liquid` - Main theme wrapper with RTL language support and font loading
- `sections/` - Modular sections that can be added to any template
- `templates/*.json` - Template configurations defining section arrangements
- `snippets/` - Reusable code components
- `assets/` - CSS, JavaScript, and media files

**JavaScript Architecture:**
- `assets/main.js` - Core utilities including `initLazyScript` for performance optimization
- Component-based JS modules (30+ individual files) for specific functionality:
  - `variant-picker.js` - Product variant selection
  - `cart-drawer.js` - Slide-out cart functionality
  - `sticky-atc.js` - Sticky add-to-cart functionality
  - `slideshow.js`, `slider.js` - Image carousels and galleries
  - `search-suggestions.js` - Search autocomplete
  - `modal.js`, `side-drawer.js` - UI overlays
- Each component is loaded independently and uses lazy initialization

**Template System:**
- Templates define page layouts using JSON configuration
- Auto-generated template files contain warnings about admin modifications
- Sections can have configurable blocks and settings via schema definitions

**Styling:**
- `assets/main.css` - Primary stylesheet
- Component-specific CSS files for modular styling
- CSS custom properties used extensively for theming
- RTL language support built into core layout

**Configuration:**
- `config/settings_schema.json` - Theme customizer options (layout, colors, typography)
- `config/settings_data.json` - Current theme settings values
- Maximum page width configurable (1100-2200px, default 1480px)

**Key Features:**
- Responsive design with mobile-specific adjustments
- Internationalization support (8+ languages in `locales/`)
- Product variant management with media grouping
- Sticky header and transparent header options
- Full-width layout options for collections
- Performance optimizations with lazy loading