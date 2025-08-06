# CopySonic AI - Professional Content Generator

A modern, SEO-optimized website for CopySonic AI, an advanced multilingual content generation tool by AdProfitX. Generate professional website content, blogs, and product pages in English, Urdu, and Hindi with cutting-edge AI technology.

## 🌟 Features

- **Multilingual AI**: Generate content in English, Urdu, and Hindi
- **SEO Optimized**: Built-in SEO optimization with meta tags and structured data
- **Responsive Design**: Modern, mobile-first design with smooth animations
- **Live Demo**: Interactive content generator with real-time preview
- **Ad Monetization**: Google AdSense integration points throughout the site
- **Professional UI**: Clean, minimal design with blue/purple gradients
- **Fast Performance**: Built with React 18, TypeScript, and Vite

## 🚀 Quick Start

### Prerequisites

- Node.js 18+ 
- npm or yarn

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/copysonic-ai.git
cd copysonic-ai
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Open [http://localhost:5000](http://localhost:5000) in your browser

## 🏗️ Tech Stack

### Frontend
- **React 18** with TypeScript
- **Tailwind CSS** for styling
- **Wouter** for routing
- **TanStack Query** for state management
- **shadcn/ui** component library
- **Lucide React** icons

### Backend
- **Node.js** with Express
- **TypeScript** for type safety
- **Drizzle ORM** for database operations
- **PostgreSQL** (Neon serverless)

### Development Tools
- **Vite** for fast builds
- **ESLint** for code quality
- **Prettier** for code formatting
- **tsx** for TypeScript execution

## 📁 Project Structure

```
copysonic-ai/
├── client/                 # Frontend application
│   ├── src/
│   │   ├── components/     # Reusable UI components
│   │   ├── pages/          # Page components
│   │   ├── hooks/          # Custom React hooks
│   │   ├── lib/            # Utility functions
│   │   └── index.css       # Global styles
│   └── index.html          # Entry HTML file
├── server/                 # Backend application
│   ├── index.ts           # Express server setup
│   ├── routes.ts          # API routes
│   └── storage.ts         # Data storage interface
├── shared/                 # Shared types and schemas
│   └── schema.ts          # Database schemas
└── components.json         # shadcn/ui configuration
```

## 🎨 Design System

### Colors
- **Primary**: Blue (#3b82f6)
- **Secondary**: Purple (#8b5cf6)
- **Accent**: Cyan (#06b6d4)
- **Background**: Light gray (#f8fafc)

### Typography
- **Font Family**: Inter (Google Fonts)
- **Headings**: Bold weights (600-800)
- **Body**: Regular weight (400)

## 📱 Responsive Breakpoints

- **Mobile**: < 768px
- **Tablet**: 768px - 1024px
- **Desktop**: > 1024px

## 🌍 Multilingual Support

The application supports three languages with proper RTL text direction for Urdu:

- **English**: Default language
- **Urdu**: Right-to-left text direction
- **Hindi**: Devanagari script support

## 💰 Monetization

Google AdSense integration points:
- Header banner (728x90)
- Sidebar ad (160x600) - Desktop only
- Inline content ad (300x250)
- Footer ad (320x100)

## 🔧 Configuration

### Environment Variables

Create a `.env` file in the root directory:

```env
# Database
DATABASE_URL=your_postgresql_connection_string

# Session
SESSION_SECRET=your_session_secret

# Development
NODE_ENV=development
```

### Google AdSense Setup

Replace placeholder ad units in `AdBanner.tsx` with your actual AdSense code.

## 🚀 Deployment

### Replit Deployment

1. Import the project to Replit
2. Configure environment variables
3. Run `npm run dev`
4. Use Replit's deployment feature

### Manual Deployment

1. Build the project:
```bash
npm run build
```

2. Deploy the `dist` folder to your hosting provider

## 📋 Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint
- `npm run type-check` - Run TypeScript compiler

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **AdProfitX** - Project owner and design direction
- **shadcn/ui** - Beautiful component library
- **Tailwind CSS** - Utility-first CSS framework
- **Unsplash** - Professional photography

## 📞 Contact

- **Website**: [AdProfitX](https://adprofitx.com)
- **Email**: hello@adprofitx.com
- **Support**: Create an issue in this repository

---

Built with ❤️ by the AdProfitX team