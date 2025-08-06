# Project Structure

This document outlines the complete file structure and organization of the CopySonic AI project.

## 📁 Root Directory

```
copysonic-ai/
├── 📄 README.md                    # Main project documentation
├── 📄 LICENSE                      # MIT License
├── 📄 CHANGELOG.md                 # Version history and changes
├── 📄 CONTRIBUTING.md              # Contribution guidelines
├── 📄 DEPLOYMENT.md                # Deployment instructions
├── 📄 PROJECT_STRUCTURE.md         # This file
├── 📄 package-scripts.md           # Documentation for npm scripts
├── 📄 .gitignore                   # Git ignore rules
├── 📄 .env.example                 # Environment variables template
├── 📄 package.json                 # Dependencies and scripts
├── 📄 package-lock.json            # Locked dependency versions
├── 📄 tsconfig.json                # TypeScript configuration
├── 📄 tailwind.config.ts           # Tailwind CSS configuration
├── 📄 postcss.config.js            # PostCSS configuration
├── 📄 vite.config.ts               # Vite build configuration
├── 📄 components.json              # shadcn/ui component configuration
├── 📄 drizzle.config.ts            # Database ORM configuration
├── 📄 replit.md                    # Project preferences and architecture
├── 📁 .github/                     # GitHub configuration
├── 📁 attached_assets/             # User-provided assets
├── 📁 client/                      # Frontend application
├── 📁 server/                      # Backend application
└── 📁 shared/                      # Shared types and schemas
```

## 🔧 GitHub Configuration (`.github/`)

```
.github/
├── 📁 workflows/
│   └── 📄 ci.yml                   # CI/CD pipeline configuration
├── 📁 ISSUE_TEMPLATE/
│   ├── 📄 bug_report.md            # Bug report template
│   ├── 📄 feature_request.md       # Feature request template
│   └── 📄 custom.md                # Custom issue template
└── 📁 PULL_REQUEST_TEMPLATE/
    └── 📄 pull_request_template.md # PR template
```

## 🎨 Frontend Structure (`client/`)

```
client/
├── 📄 index.html                   # Entry HTML file
└── 📁 src/
    ├── 📄 main.tsx                 # React application entry point
    ├── 📄 App.tsx                  # Main App component with routing
    ├── 📄 index.css                # Global styles and Tailwind imports
    ├── 📁 components/              # React components
    │   ├── 📄 index.ts             # Component exports
    │   ├── 📄 Header.tsx           # Navigation header
    │   ├── 📄 Hero.tsx             # Hero section
    │   ├── 📄 Features.tsx         # Features showcase
    │   ├── 📄 Demo.tsx             # Interactive demo
    │   ├── 📄 Reviews.tsx          # Customer testimonials
    │   ├── 📄 Pricing.tsx          # Pricing plans
    │   ├── 📄 Languages.tsx        # Language switcher
    │   ├── 📄 Contact.tsx          # Contact form and footer
    │   ├── 📄 AdBanner.tsx         # Advertisement placeholders
    │   ├── 📄 ScrollToTop.tsx      # Scroll to top button
    │   └── 📁 ui/                  # shadcn/ui components
    │       ├── 📄 button.tsx       # Button component
    │       ├── 📄 input.tsx        # Input component
    │       ├── 📄 textarea.tsx     # Textarea component
    │       ├── 📄 label.tsx        # Label component
    │       ├── 📄 toast.tsx        # Toast notification
    │       ├── 📄 toaster.tsx      # Toast container
    │       ├── 📄 tooltip.tsx      # Tooltip component
    │       └── 📄 ...              # Other UI components
    ├── 📁 hooks/                   # Custom React hooks
    │   ├── 📄 use-mobile.tsx       # Mobile detection hook
    │   └── 📄 use-toast.ts         # Toast notification hook
    ├── 📁 lib/                     # Utility libraries
    │   ├── 📄 utils.ts             # General utility functions
    │   └── 📄 queryClient.ts       # TanStack Query client setup
    └── 📁 pages/                   # Page components
        ├── 📄 home.tsx             # Main landing page
        └── 📄 not-found.tsx        # 404 error page
```

## ⚙️ Backend Structure (`server/`)

```
server/
├── 📄 index.ts                     # Express server setup and main entry
├── 📄 routes.ts                    # API route definitions
├── 📄 storage.ts                   # Database storage interface
└── 📄 vite.ts                      # Vite integration middleware
```

## 🔗 Shared Code (`shared/`)

```
shared/
└── 📄 schema.ts                    # Shared database schemas and types
```

## 📦 Asset Management (`attached_assets/`)

```
attached_assets/
└── 📄 *.txt                       # User-provided assets and requirements
```

## 🔧 Configuration Files

### `package.json`
- **Dependencies**: React, TypeScript, Express, Drizzle ORM
- **Dev Dependencies**: Vite, ESLint, Prettier, Tailwind CSS
- **Scripts**: Development, build, test, and deployment commands

### `tsconfig.json`
- **Strict TypeScript**: Enabled for type safety
- **Path Mapping**: `@/*` for client sources, `@shared/*` for shared code
- **Module Resolution**: ESNext with bundler resolution
- **Include Paths**: Client, server, and shared directories

### `tailwind.config.ts`
- **Content Paths**: All TypeScript/JavaScript files in client
- **Theme Extension**: Custom colors and design tokens
- **Plugins**: shadcn/ui animations and utilities

### `vite.config.ts`
- **React Plugin**: JSX transformation and HMR
- **Path Aliases**: Matches TypeScript path mapping
- **Build Options**: Production optimizations
- **Dev Server**: Proxy configuration for API routes

### `drizzle.config.ts`
- **Database Connection**: PostgreSQL via Neon serverless
- **Migration Output**: SQL files for version control
- **Schema**: Located in shared directory

## 📱 Component Architecture

### Layout Components
- **Header**: Navigation, logo, mobile menu
- **Hero**: Main banner with CTA buttons
- **Features**: Service highlights with icons
- **Footer**: Contact info, social links, copyright

### Interactive Components
- **Demo**: Live content generator with form
- **Contact**: Contact form with validation
- **Languages**: Language switcher with samples
- **ScrollToTop**: Smooth scroll utility

### UI Components (shadcn/ui)
- **Form Elements**: Button, Input, Textarea, Label
- **Feedback**: Toast notifications, Tooltips
- **Layout**: Cards, Separators, Containers
- **Navigation**: Menus, Breadcrumbs, Pagination

## 🎨 Styling System

### CSS Architecture
```
index.css
├── 🎨 Google Fonts import
├── 🎨 Tailwind base, components, utilities
├── 🎨 CSS custom properties (:root, .dark)
├── 🎨 Component classes (.gradient-bg, .hover-lift)
└── 🎨 Animation classes (.fade-in, .mobile-menu)
```

### Color System
- **Primary**: Blue (#3b82f6) - Main brand color
- **Secondary**: Purple (#8b5cf6) - Accent color
- **Accent**: Cyan (#06b6d4) - Highlight color
- **Background**: Light gray (#f8fafc) - Page background
- **Text**: Slate variants for hierarchy

### Typography
- **Font**: Inter (Google Fonts)
- **Weights**: 300-800 range
- **Sizes**: Responsive scale using Tailwind classes
- **Line Heights**: Optimized for readability

## 🗃️ Data Flow

### State Management
```
TanStack Query
├── 🔄 Server State: API data caching
├── 🔄 Mutations: Form submissions
├── 🔄 Background Updates: Auto-refresh
└── 🔄 Optimistic Updates: Instant feedback
```

### Local State
```
React useState/useEffect
├── 📱 UI State: Modal visibility, form data
├── 📱 User Preferences: Language selection
├── 📱 Component State: Loading, errors
└── 📱 Navigation State: Mobile menu, scroll position
```

### Persistent Storage
```
localStorage
├── 💾 Language Preference: User's selected language
├── 💾 Theme Preference: Light/dark mode
└── 💾 User Settings: Display preferences
```

## 🔐 Security Architecture

### Frontend Security
- **Input Validation**: Form data sanitization
- **XSS Protection**: React's built-in escaping
- **CSRF Protection**: SameSite cookies
- **Content Security Policy**: Restricted resource loading

### Backend Security
- **Environment Variables**: Sensitive data isolation
- **Session Management**: Secure session handling
- **Rate Limiting**: API abuse prevention
- **CORS Configuration**: Cross-origin request control

## 📊 Performance Strategy

### Build Optimization
- **Code Splitting**: Route-based lazy loading
- **Asset Optimization**: Image compression, font loading
- **Bundle Analysis**: Webpack bundle analyzer
- **Tree Shaking**: Unused code elimination

### Runtime Performance
- **React Optimization**: Memo, useMemo, useCallback
- **Image Optimization**: Lazy loading, responsive images
- **Caching Strategy**: Browser and CDN caching
- **Database Optimization**: Query optimization, indexing

## 🔍 SEO Implementation

### Meta Tags
```html
<head>
  <title>CopySonic AI - Smart Content in Any Language</title>
  <meta name="description" content="AI-powered content generator..." />
  <meta property="og:title" content="..." />
  <meta property="og:description" content="..." />
  <meta property="og:image" content="..." />
  <meta name="twitter:card" content="summary_large_image" />
</head>
```

### Structured Data
- **Organization Schema**: Company information
- **WebSite Schema**: Site navigation
- **Product Schema**: Service offerings
- **Review Schema**: Customer testimonials

### Performance Metrics
- **Core Web Vitals**: LCP, FID, CLS optimization
- **Lighthouse Score**: Target 90+ across all metrics
- **Mobile-First**: Responsive design priority
- **Page Speed**: Sub-3 second load times

## 🚀 Deployment Architecture

### Development Environment
```
Local Development
├── 🔧 Vite Dev Server: Hot reload, source maps
├── 🔧 Express Server: API development
├── 🔧 PostgreSQL: Local database
└── 🔧 Environment Variables: Development configuration
```

### Production Environment
```
Production Deployment
├── 🚀 Static Assets: CDN distribution
├── 🚀 API Server: Containerized Express app
├── 🚀 Database: Managed PostgreSQL
├── 🚀 SSL/TLS: Automatic certificate management
└── 🚀 Monitoring: Application performance monitoring
```

## 📋 Development Workflow

### Code Organization
1. **Feature Development**: Component-based architecture
2. **Type Safety**: Strict TypeScript throughout
3. **Code Quality**: ESLint + Prettier automation
4. **Testing**: Unit and integration tests
5. **Documentation**: Inline comments and README updates

### Git Workflow
1. **Branching**: Feature branches from main
2. **Commits**: Conventional commit format
3. **Pull Requests**: Code review process
4. **CI/CD**: Automated testing and deployment
5. **Releases**: Semantic versioning

This structure ensures maintainability, scalability, and ease of contribution for the CopySonic AI project.