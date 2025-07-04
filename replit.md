# Replit.md

## Overview

This is a full-stack web application built with React and Express.js, featuring a modern UI component library and PostgreSQL database integration. The application appears to be a personal portfolio/resume website showcasing professional experience, projects, achievements, and skills in AI/ML engineering.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **UI Framework**: Tailwind CSS for styling with shadcn/ui component library
- **State Management**: TanStack Query (React Query) for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Animation**: Framer Motion for smooth animations and transitions

### Backend Architecture
- **Runtime**: Node.js with Express.js server
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (@neondatabase/serverless)
- **Session Management**: PostgreSQL session store (connect-pg-simple)

### Development Setup
- **Hot Module Replacement**: Vite development server with middleware integration
- **Path Aliases**: Configured for clean imports (@, @shared, @assets)
- **Code Quality**: TypeScript strict mode enabled
- **Replit Integration**: Development banner and runtime error overlay

## Key Components

### Database Layer
- **ORM**: Drizzle ORM with PostgreSQL dialect
- **Schema Location**: `shared/schema.ts` for shared types between client/server
- **Migrations**: Automated via `drizzle-kit` with migrations stored in `./migrations`
- **User Model**: Basic user schema with id, username, and password fields

### Frontend Components
- **UI Components**: Comprehensive shadcn/ui component library including:
  - Form components (buttons, inputs, selects, checkboxes, etc.)
  - Layout components (cards, sheets, dialogs, navigation)
  - Data display (tables, charts, progress indicators)
  - Feedback components (toasts, alerts, tooltips)
- **Portfolio Sections**: Modular components for different resume sections:
  - Hero section with professional photo
  - Experience timeline
  - Projects showcase
  - Skills categorization
  - Achievements and leadership activities
  - Contact information

### Backend Services
- **Storage Interface**: Abstract storage layer with in-memory implementation
- **Route Registration**: Centralized route handling in `server/routes.ts`
- **Middleware**: Request logging, JSON parsing, and error handling
- **Static File Serving**: Vite integration for development, static serving for production

## Data Flow

1. **Client Requests**: React components make API calls via TanStack Query
2. **Server Processing**: Express.js handles API routes with middleware chain
3. **Database Operations**: Drizzle ORM manages PostgreSQL interactions
4. **Response Handling**: Structured JSON responses with error handling
5. **State Management**: TanStack Query caches and manages server state
6. **UI Updates**: React components re-render based on state changes

## External Dependencies

### Core Dependencies
- **React Ecosystem**: React 18, React DOM, React Query
- **Database**: PostgreSQL via Neon Database, Drizzle ORM
- **UI Libraries**: Radix UI primitives, Tailwind CSS, shadcn/ui
- **Development Tools**: Vite, TypeScript, PostCSS
- **Form Handling**: React Hook Form with Zod validation
- **Icons**: Lucide React icons, React Icons

### Production Dependencies
- **Server**: Express.js with TypeScript support
- **Database Connection**: Neon serverless PostgreSQL driver
- **Session Management**: PostgreSQL session store
- **Build Tools**: ESBuild for server bundling, Vite for client bundling

## Deployment Strategy

### Development
- **Local Development**: Vite dev server with Express.js middleware
- **Hot Reload**: Both client and server code with automatic restart
- **Environment**: NODE_ENV=development with development-specific features

### Production Build
- **Client Build**: Vite builds optimized React bundle to `dist/public`
- **Server Build**: ESBuild bundles server code to `dist/index.js`
- **Static Assets**: Served from `dist/public` directory
- **Database**: Requires DATABASE_URL environment variable

### Build Commands
- `npm run dev`: Development server with hot reload
- `npm run build`: Production build for both client and server
- `npm run start`: Production server startup
- `npm run db:push`: Database schema deployment

## User Preferences

Preferred communication style: Simple, everyday language.

## Changelog

Changelog:
- July 04, 2025. Initial setup