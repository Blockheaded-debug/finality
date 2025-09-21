# YoYo Final - Crypto Trading Signal Application

## Overview
This is a comprehensive crypto trading signal application with React frontend, Node.js/Express backend, and Python-based technical analysis service. The application provides real-time crypto trading signals using advanced technical indicators.

## Project Architecture
- **Frontend**: React + TypeScript + Vite (client/)
- **Backend**: Node.js + Express + Drizzle ORM (server/)  
- **Analysis Service**: Python + Flask + Technical Analysis (python_backend/)
- **Database**: PostgreSQL (optional, falls back gracefully)

## Recent Changes (September 20, 2025)
- Imported from GitHub and configured for Replit environment
- Fixed Vite configuration to allow all hosts for proxy support
- Installed Node.js 20 and Python 3.11 with all dependencies
- Configured multi-service architecture with proper port separation
- Set up main workflow for frontend serving on port 5000
- Backend services: Node.js (port 5000), Python analysis (port 5001)

## User Preferences
- Uses modern React with TypeScript and shadcn/ui components
- Prefers technical analysis for crypto trading signals
- Uses Drizzle ORM for database operations
- Follows monorepo structure with shared schema

## Key Features
- Real-time crypto price analysis
- Technical indicators: RSI, EMA, Stochastic, MACD, Bollinger Bands
- User authentication with Replit Auth
- Trading dashboard with interactive charts
- Signal confidence scoring system

## Development Setup
- Main workflow runs on port 5000 (combines frontend and API)
- Python analysis service on port 5001 (localhost)
- Database optional with graceful fallback for development
- Vite dev server proxies API calls to Express backend