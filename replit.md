# Overview

This is a lead generation and management application built for recruitment agencies and staffing companies in the Philippines. The application allows users to browse, filter, search, and export company data with detailed filtering capabilities and lead scoring functionality. It provides a comprehensive interface for managing potential business leads with features like advanced filtering, bulk selection, and data export in multiple formats.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture

The frontend is built with React 18 using TypeScript and follows a modern component-based architecture:

- **UI Framework**: React with TypeScript for type safety and better development experience
- **Styling**: Tailwind CSS with shadcn/ui component library for consistent, accessible UI components
- **State Management**: TanStack Query (React Query) for server state management and caching
- **Routing**: Wouter for lightweight client-side routing
- **Form Handling**: React Hook Form with Zod validation for type-safe form management
- **Build Tool**: Vite for fast development and optimized production builds

The application uses a component-driven design with reusable UI components from Radix UI primitives wrapped with Tailwind styling. The architecture separates concerns between presentation components, business logic, and data fetching.

## Backend Architecture

The backend follows a RESTful API design built with Express.js:

- **Runtime**: Node.js with TypeScript and ES modules
- **Framework**: Express.js for HTTP server and API routing
- **Data Storage**: Currently uses in-memory storage with a well-defined interface that can be easily swapped for a database implementation
- **API Design**: RESTful endpoints with proper HTTP status codes and JSON responses
- **Error Handling**: Centralized error middleware for consistent error responses

The storage layer uses an interface-based design (`IStorage`) allowing for easy replacement of the current memory-based implementation with a database-backed solution without changing the business logic.

## Data Storage Solutions

Currently implements in-memory storage with sample data for development:

- **Current**: Memory-based storage with mock data for recruitment companies
- **Database Ready**: Drizzle ORM configuration prepared for PostgreSQL with schema definitions
- **Schema**: Well-defined TypeScript types and Zod validation schemas shared between client and server
- **Migration Support**: Drizzle Kit configured for database migrations when transitioning to persistent storage

The schema includes comprehensive company data fields including industry classification, location data, contact information, website status, and lead scoring metrics.

## Authentication and Authorization

Currently, the application does not implement authentication, operating as a single-user system. The architecture is prepared for future authentication implementation with:

- Session handling middleware configured (connect-pg-simple for PostgreSQL sessions)
- Query client configured to handle 401 responses
- Consistent error handling patterns for authorization failures

## External Dependencies

- **Neon Database**: PostgreSQL serverless database service (configured but not yet active)
- **Radix UI**: Comprehensive set of accessible UI primitives
- **Lucide React**: Icon library for consistent iconography
- **TanStack Query**: Advanced data fetching and caching solution
- **Drizzle ORM**: Type-safe database toolkit with PostgreSQL support
- **Tailwind CSS**: Utility-first CSS framework
- **Zod**: TypeScript-first schema validation library
- **React Hook Form**: Performant forms library with built-in validation
- **Vite**: Next-generation frontend build tool
- **Wouter**: Minimalist routing library for React

The application is designed to be easily deployable and scalable, with configuration for both development and production environments including proper error handling, logging, and build optimization.