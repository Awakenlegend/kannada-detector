# Kannada Fake News Detector - Project Structure

## Overview
This is a full-stack web application built with React, TypeScript, Express, and MySQL for detecting fake news in Kannada language using AI-powered analysis.

## Technology Stack

### Frontend
- **React 19.2.1** - UI framework
- **TypeScript 5.9.3** - Type safety
- **Vite 7.1.7** - Build tool
- **TailwindCSS 4.1.14** - Styling
- **Wouter 3.7.1** - Routing
- **React Hook Form 7.64.0** - Form management
- **Zod 4.1.12** - Schema validation
- **Lucide React 0.453.0** - Icons
- **Recharts 2.15.2** - Data visualization
- **Framer Motion 12.23.22** - Animations

### Backend
- **Express 4.21.2** - Web framework
- **Node.js 22.13.0** - Runtime
- **tRPC 11.6.0** - Type-safe API
- **Drizzle ORM 0.44.5** - Database ORM
- **MySQL2 3.15.0** - Database driver

### AI/ML Integration
- **@ai-sdk/openai 3.0.12** - OpenAI API integration
- **ai 6.0.38** - AI SDK for streaming and tool calling
- **Streamdown 1.0.1** - Markdown rendering with code highlighting

### Database
- **MySQL** - Primary database
- **Drizzle Kit 0.31.4** - Schema migrations

## Directory Structure

```
kannada-detector/
├── client/                      # Frontend React application
│   ├── src/
│   │   ├── App.tsx             # Main app component
│   │   ├── pages/              # Page components
│   │   │   ├── Home.tsx        # Home page
│   │   │   └── NotFound.tsx    # 404 page
│   │   ├── components/         # Reusable components
│   │   │   ├── ui/             # Shadcn UI components
│   │   │   ├── AIChatBox.tsx   # AI chat interface
│   │   │   ├── DashboardLayout.tsx
│   │   │   └── ErrorBoundary.tsx
│   │   ├── _core/
│   │   │   └── hooks/
│   │   │       └── useAuth.ts  # Authentication hook
│   │   ├── contexts/           # React contexts
│   │   │   └── ThemeContext.ts # Theme management
│   │   └── const.ts            # Constants
│   ├── public/                 # Static assets
│   └── index.html              # Entry HTML
│
├── server/                      # Backend Node.js application
│   ├── _core/
│   │   ├── index.ts            # Server entry point
│   │   ├── chat.ts             # AI chat API endpoint
│   │   ├── oauth.ts            # OAuth authentication
│   │   ├── context.ts          # tRPC context
│   │   ├── trpc.ts             # tRPC setup
│   │   ├── env.ts              # Environment variables
│   │   ├── cookies.ts          # Cookie handling
│   │   ├── vite.ts             # Vite integration
│   │   ├── imageGeneration.ts  # Image generation
│   │   ├── voiceTranscription.ts # Voice to text
│   │   ├── notification.ts     # Notifications
│   │   └── patchedFetch.ts     # Fetch wrapper
│   ├── routers/                # tRPC routers
│   ├── db.ts                   # Database functions
│   └── auth.logout.test.ts     # Tests
│
├── drizzle/                     # Database schema
│   ├── schema.ts               # Table definitions
│   └── migrations/             # Migration files
│
├── shared/                      # Shared types
│   └── types.ts                # Shared TypeScript types
│
├── package.json                # Dependencies
├── tsconfig.json               # TypeScript config
├── vite.config.ts              # Vite configuration
├── vitest.config.ts            # Test configuration
├── drizzle.config.ts           # Drizzle configuration
└── README.md                   # Documentation
```

## Key Features

### 1. Kannada News Verification
- Accept Kannada text input
- AI-powered analysis of news content
- Multi-factor verification including:
  - Language pattern analysis
  - Factual consistency checking
  - Source credibility assessment
  - Confidence scoring

### 2. User Authentication
- OAuth-based authentication
- User roles (admin, user)
- Session management with JWT
- Secure cookie handling

### 3. AI Integration
- OpenAI API integration for text analysis
- Streaming responses for real-time feedback
- Tool calling for structured data extraction
- Custom tools for weather and calculations

### 4. Database
- User management with Drizzle ORM
- MySQL database backend
- Type-safe queries with TypeScript

### 5. Frontend Features
- Responsive design with TailwindCSS
- Dark/light theme support
- Real-time form validation
- Error boundaries for crash prevention
- Markdown rendering with syntax highlighting

## API Endpoints

### Chat API
- **POST /api/chat** - Stream AI responses with tool calling

### OAuth
- **GET /api/oauth/callback** - OAuth callback handler

### tRPC API
- **POST /api/trpc** - Type-safe RPC calls

## Environment Variables

```
DATABASE_URL=mysql://user:password@host/database
OPENAI_API_KEY=sk-...
OPENAI_API_BASE_URL=https://api.openai.com/v1
JWT_SECRET=your-secret-key
OAUTH_SERVER_URL=https://oauth.example.com
VITE_OAUTH_PORTAL_URL=https://portal.example.com
```

## Build & Deployment

### Development
```bash
npm run dev
```

### Production Build
```bash
npm run build
npm run start
```

### Database Migrations
```bash
npm run db:push
```

## Testing
```bash
npm run test
```

## Code Quality
```bash
npm run format
npm run check
```

## Authentication Flow

1. User clicks "Sign In"
2. Redirected to OAuth provider
3. OAuth callback to `/api/oauth/callback`
4. User data stored in database
5. JWT token issued
6. User authenticated for API calls

## Data Flow

1. **Input**: User pastes Kannada news text
2. **Processing**: AI analyzes content using OpenAI API
3. **Analysis**: 
   - Language pattern detection
   - Factual consistency check
   - Source credibility assessment
4. **Output**: Confidence score and detailed breakdown
5. **Storage**: Results can be saved to database

## Security Features

- JWT-based authentication
- Secure cookie handling
- CORS protection
- Input validation with Zod
- SQL injection prevention via ORM
- Environment variable protection

## Performance Optimizations

- Vite for fast builds
- React Query for efficient data fetching
- Streaming responses for real-time feedback
- Tailwind CSS for optimized styling
- Code splitting and lazy loading

## Future Enhancements

- Multi-language support
- Advanced NLP models
- Real-time fact-checking database
- User feedback loop for model improvement
- Analytics dashboard
- API rate limiting
- Caching mechanisms
