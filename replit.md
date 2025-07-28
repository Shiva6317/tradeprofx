# TradePro FX Trading Platform

## Overview
This is a modern full-stack trading platform built with React and Express.js. The application provides real-time trading data, market statistics, and a comprehensive trading interface for forex, indices, commodities, stocks, and cryptocurrency trading.

## User Preferences
Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Styling**: TailwindCSS with shadcn/ui component library
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack Query for server state management
- **Build Tool**: Vite for development and production builds
- **UI Components**: Extensive use of Radix UI primitives through shadcn/ui

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Data Layer**: Drizzle ORM with PostgreSQL
- **Database**: PostgreSQL (configured for Neon Database)
- **Session Management**: PostgreSQL session store with connect-pg-simple
- **Development**: Hot reload with Vite middleware integration

### Database Schema
The application uses three main entities:
- **Users**: Authentication and user management
- **Trading Instruments**: Market data for various trading assets
- **Market Stats**: Key performance metrics and statistics

## Key Components

### Trading Features
- Real-time market data display
- Trading instrument categorization (forex, indices, commodities, stocks, crypto)
- Interactive trading charts powered by TradingView widgets
- Market statistics dashboard
- Cross-rate tables for forex pairs

### User Interface
- Responsive design with mobile-first approach
- Professional trading-focused color scheme
- Navigation with active state management
- Ticker tape for live market updates
- Modal dialogs and sheets for enhanced UX

### API Structure
RESTful API endpoints:
- `/api/trading-instruments` - Get all trading instruments
- `/api/trading-instruments/:category` - Get instruments by category
- `/api/market-stats` - Get market statistics

## Data Flow

### Client-Server Communication
1. React components use TanStack Query for data fetching
2. API requests go through a centralized query client with error handling
3. Server responses are cached and automatically revalidated
4. Real-time updates handled through TradingView widget integrations

### Storage Strategy
- Development: In-memory storage with mock data initialization
- Production: PostgreSQL database with Drizzle ORM
- Session management through PostgreSQL store

## External Dependencies

### Major Libraries
- **UI Framework**: React with TypeScript
- **Database**: Drizzle ORM with @neondatabase/serverless
- **Styling**: TailwindCSS with Radix UI components
- **Charts**: TradingView embedded widgets
- **Form Handling**: React Hook Form with Zod validation
- **Date Handling**: date-fns for date manipulation

### Third-Party Integrations
- **TradingView**: Embedded widgets for charts, ticker tape, and forex cross rates
- **Neon Database**: Serverless PostgreSQL hosting
- **Replit**: Development environment integration

## Deployment Strategy

### Build Process
- Frontend: Vite builds React app to `dist/public`
- Backend: esbuild bundles server code to `dist/index.js`
- Single deployment artifact containing both client and server

### Environment Configuration
- Development: Uses Vite dev server with Express API proxy
- Production: Serves static files through Express with API routes
- Database: PostgreSQL connection via DATABASE_URL environment variable

### Development Workflow
- `npm run dev`: Starts development server with hot reload
- `npm run build`: Creates production build
- `npm run start`: Runs production server
- `npm run db:push`: Syncs database schema with Drizzle

The application follows a modern full-stack architecture with clear separation of concerns, type safety throughout, and a focus on developer experience while maintaining production readiness.