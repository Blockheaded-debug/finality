# YoYo Final - Crypto Trading Signal Application

**ALWAYS follow these instructions first and fallback to additional search and context gathering ONLY when the information here is incomplete or found to be in error.**

## Application Overview
YoYo Final is a professional cryptocurrency trading signal application with React frontend, Node.js/Express backend, and Python-based technical analysis service. The application provides real-time crypto trading signals using advanced technical indicators (RSI, EMA, Stochastic, MACD, Bollinger Bands).

**Working Directory**: Always work in `/home/runner/work/finality/finality/CHATPGT-GUIDANCE/yoyofinal-1/`

## Build, Test, and Run Commands

### CRITICAL TIMING AND CANCELLATION WARNINGS
- **NEVER CANCEL any build or test commands** - all operations complete quickly in this codebase
- Build times are under 5 seconds - set timeout to 30+ seconds for safety
- TypeScript checking takes ~6 seconds - set timeout to 30+ seconds
- No dedicated test suite exists - validation is done manually

### Essential Commands (Always run these in order)
```bash
cd /home/runner/work/finality/finality/CHATPGT-GUIDANCE/yoyofinal-1

# Install dependencies (takes ~20 seconds - NEVER CANCEL)
npm install

# Install Python dependencies (takes ~60 seconds - NEVER CANCEL) 
pip3 install flask flask-cors numpy pandas prophet requests scikit-learn ta yfinance

# TypeScript type checking (takes ~6 seconds)
npm run check

# Build application (takes ~4 seconds - NEVER CANCEL)
npm run build

# Run development server (runs continuously)
npm run dev
```

### Build Validation Process
1. **ALWAYS** run `npm run check` before making changes to verify TypeScript compilation
2. **ALWAYS** run `npm run build` after code changes to ensure production build works
3. **ALWAYS** test the running application manually after changes
4. Build artifacts are created in `dist/` directory - exclude from commits

## Application Architecture & Key Files

### Frontend (React + TypeScript + Vite)
- **Root**: `client/` directory
- **Main config**: `vite.config.ts` - configured for development proxy
- **Entry point**: `client/src/main.tsx`
- **Components**: `client/src/components/`
- **UI Library**: shadcn/ui components in `client/src/components/ui/`
- **Routing**: Wouter library for client-side routing

### Backend (Node.js + Express)
- **Main file**: `server/index.ts` - serves both API and frontend
- **Port**: Always runs on port 5000 (hardcoded, not configurable)
- **Authentication**: Static credentials in `server/staticAuth.ts`
- **Routes**: Defined in `server/routes.ts`
- **Database**: Configured for PostgreSQL with Drizzle ORM but falls back gracefully

### Python Analysis Service
- **Location**: `python_backend/` directory
- **Main service**: `python_backend/app.py` (Flask server on port 8000)
- **Analysis script**: `python_backend/analyze_pair.py` (standalone CLI tool)
- **Dependencies**: Requires external internet access to CoinGecko API

### Configuration Files
- **Package.json**: Contains all npm scripts and dependencies
- **pyproject.toml**: Python dependencies using modern pyproject format
- **tsconfig.json**: TypeScript configuration
- **tailwind.config.ts**: Tailwind CSS configuration
- **drizzle.config.ts**: Database ORM configuration

## Manual Validation Requirements

### ALWAYS test these scenarios after making changes:
1. **Homepage Loading**: Visit `http://localhost:5000` - should show professional landing page
2. **Login Flow**: Click "Sign In" → Navigate to `/login` → Enter credentials:
   - Username: `nexus_admin`
   - Password: `Crypto$2024#Vault`
3. **API Endpoints**: Test these endpoints work:
   - `GET /api/auth/user` (returns 401 when not logged in)
   - `POST /api/login` with correct credentials (returns success)
4. **Build Process**: Ensure `npm run build` completes without errors
5. **TypeScript**: Ensure `npm run check` passes without errors

### Known Limitations in Sandboxed Environment
- **Python Analysis**: CoinGecko API calls will fail due to network restrictions - this is expected
- **Database**: PostgreSQL connection may fail - application gracefully falls back to in-memory storage
- **External Fonts**: Google Fonts blocked - this is expected and doesn't affect functionality

## Development Workflow

### Making Changes
1. Start development server: `npm run dev`
2. Navigate to http://localhost:5000 to test changes
3. For API changes: Test endpoints with curl or browser developer tools
4. For frontend changes: Verify in browser and check console for errors
5. Always run `npm run check` and `npm run build` before finalizing changes

### Static Credentials for Testing
- **Username**: `nexus_admin`
- **Password**: `Crypto$2024#Vault`
- **Test endpoints**: `/api/login`, `/api/logout`, `/api/auth/user`

### Port Configuration
- **Main Application**: Port 5000 (frontend + API)
- **Python Service**: Port 8000 (separate Flask service)
- **Vite Dev Server**: Port 5173 (proxied through main app)

## Common Issues and Solutions

### "Port already in use" errors
- Stop existing processes with `pkill -f "npm run dev"` or `pkill -f "python3 app.py"`
- Always use port 5000 for main application

### Build failures
- Run `npm install` if missing dependencies
- Check TypeScript errors with `npm run check`
- Verify all imports are correctly typed

### Frontend navigation issues
- Application uses Wouter for routing - check route definitions in components
- 404 errors indicate missing route configuration

### Python service issues
- Install dependencies: `pip3 install flask flask-cors numpy pandas prophet requests scikit-learn ta yfinance`
- Network errors from CoinGecko API are expected in sandboxed environments

## File Structure Reference
```
CHATPGT-GUIDANCE/yoyofinal-1/
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── main.tsx       # App entry point
│   └── index.html         # HTML template
├── server/                # Node.js backend
│   ├── index.ts          # Main server file
│   ├── routes.ts         # API routes
│   └── staticAuth.ts     # Authentication logic
├── python_backend/        # Python analysis service
│   ├── app.py           # Flask server
│   └── analyze_pair.py  # Analysis script
├── shared/               # Shared TypeScript types
├── package.json         # Node.js dependencies
├── pyproject.toml       # Python dependencies
├── vite.config.ts       # Vite configuration
└── tsconfig.json        # TypeScript configuration
```

## CRITICAL: What NOT to do
- **NEVER** cancel build commands - they complete in seconds
- **NEVER** modify port configurations - hardcoded to 5000
- **NEVER** expect Python API calls to work in sandboxed environments
- **NEVER** commit node_modules, dist/, or .local/ directories
- **NEVER** change authentication credentials in staticAuth.ts without testing