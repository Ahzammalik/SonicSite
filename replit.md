# Overview

CopySonic AI is a professional, GitHub-ready web application for generating AI content in multiple languages (English, Urdu, and Hindi). Built for AdProfitX, this full-stack application helps small business owners and freelancers create website content, blogs, and product pages with AI technology. The project features modern architecture, comprehensive documentation, CI/CD pipelines, and is fully prepared for open-source collaboration and deployment.

## Recent Changes (January 2025)

### GitHub Preparation Completed
- ✅ Fixed all TypeScript import errors and LSP diagnostics
- ✅ Created comprehensive README.md with installation and features
- ✅ Added MIT License for open-source distribution
- ✅ Configured .gitignore for proper version control
- ✅ Created detailed CONTRIBUTING.md for collaboration
- ✅ Added DEPLOYMENT.md with multiple hosting options
- ✅ Set up GitHub Actions CI/CD pipeline
- ✅ Created PROJECT_STRUCTURE.md for codebase navigation
- ✅ Added CHANGELOG.md for version tracking
- ✅ Configured environment variables template (.env.example)
- ✅ Organized component exports for clean imports
- ✅ Fixed CSS import order issues
- ✅ Ready for GitHub upload and collaboration

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
- **Framework**: React 18 with TypeScript for type safety and modern development
- **Routing**: Wouter for lightweight client-side routing
- **Styling**: Tailwind CSS with CSS custom properties for theming and shadcn/ui for component library
- **State Management**: TanStack Query (React Query) for server state management and caching
- **Build Tool**: Vite for fast development and optimized production builds
- **Component Strategy**: Modular component architecture with reusable UI components following shadcn/ui patterns

## Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript for full-stack type safety
- **Development**: ESM modules with tsx for TypeScript execution
- **Storage**: In-memory storage implementation with interface-based design for easy database migration
- **API Design**: RESTful API structure with prefix routing (/api)

## Data Storage Solutions
- **ORM**: Drizzle ORM configured for PostgreSQL with schema-first approach
- **Database**: PostgreSQL (configured via Neon serverless)
- **Schema Management**: Centralized schema definition in shared directory with Zod validation
- **Migrations**: Drizzle Kit for database migrations and schema synchronization

## Authentication and Authorization
- **Session Management**: Connect PG Simple for PostgreSQL-backed sessions
- **User Model**: Basic user schema with username/password authentication
- **Security**: Structured for easy expansion to include JWT or OAuth implementations

## Frontend UI System
- **Design System**: shadcn/ui components with Radix UI primitives
- **Theming**: CSS custom properties for light/dark mode support
- **Typography**: Inter font family for modern, readable design
- **Icons**: Lucide React icons with Font Awesome fallback support
- **Responsive Design**: Mobile-first approach with Tailwind breakpoints

## SEO and Performance
- **Meta Tags**: Comprehensive Open Graph and Twitter Card implementation
- **Image Optimization**: Unsplash integration for professional imagery with proper alt text
- **Font Loading**: Google Fonts with display=swap for performance
- **Build Optimization**: Vite bundling with ESBuild for production builds

## Development Environment
- **Hot Reload**: Vite HMR with Express middleware integration
- **Error Handling**: Runtime error overlay for development
- **TypeScript**: Strict mode enabled with comprehensive path mapping
- **Code Organization**: Monorepo structure with shared types and utilities

# External Dependencies

## Core Framework Dependencies
- **@tanstack/react-query**: Server state management and caching
- **wouter**: Lightweight React routing
- **express**: Node.js web framework
- **drizzle-orm**: TypeScript ORM for database operations

## UI and Styling
- **@radix-ui/***: Accessible component primitives (15+ components)
- **tailwindcss**: Utility-first CSS framework
- **lucide-react**: Modern icon library
- **class-variance-authority**: Component variant management

## Database and Storage
- **@neondatabase/serverless**: PostgreSQL serverless driver
- **connect-pg-simple**: PostgreSQL session store
- **drizzle-kit**: Database migration and introspection tools

## Development Tools
- **vite**: Build tool and development server
- **tsx**: TypeScript execution engine
- **esbuild**: JavaScript bundler for production

## Form and Validation
- **react-hook-form**: Form state management
- **@hookform/resolvers**: Form validation resolvers
- **zod**: Runtime type validation

## Additional Features
- **date-fns**: Date utility library
- **embla-carousel-react**: Carousel component
- **cmdk**: Command palette functionality
- **nanoid**: Unique ID generation

## Replit Integration
- **@replit/vite-plugin-runtime-error-modal**: Development error handling
- **@replit/vite-plugin-cartographer**: Development tooling (conditional)