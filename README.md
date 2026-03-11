# Kannada Fake News Detector

A full-stack AI-powered web application for detecting fake news in Kannada language using advanced natural language processing and machine learning techniques.

## 🎯 Overview

The Kannada Fake News Detector is a research-focused application designed to help identify misinformation and fake news content in Kannada, one of India's major languages. It leverages OpenAI's language models combined with custom analysis tools to provide comprehensive verification of news content.

## ✨ Key Features

- **Kannada Text Analysis**: Specialized processing for Kannada language content
- **AI-Powered Verification**: Uses OpenAI GPT models for intelligent analysis
- **Multi-Factor Analysis**:
  - Language pattern detection
  - Factual consistency checking
  - Source credibility assessment
  - Confidence scoring
- **User Authentication**: Secure OAuth-based login system
- **Real-time Streaming**: Live feedback during analysis
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Type-Safe**: Built with TypeScript for reliability

## 🛠️ Technology Stack

### Frontend
- React 19.2.1
- TypeScript 5.9.3
- Vite 7.1.7
- TailwindCSS 4.1.14
- React Hook Form
- Zod (validation)
- Recharts (visualization)

### Backend
- Node.js 22.13.0
- Express 4.21.2
- tRPC 11.6.0
- Drizzle ORM 0.44.5
- MySQL 8.0+

### AI/ML
- OpenAI API (@ai-sdk/openai)
- AI SDK (streaming & tool calling)
- Custom NLP tools

## 📋 Project Structure

```
kannada-detector/
├── client/                    # React frontend
│   ├── src/
│   │   ├── pages/            # Page components
│   │   ├── components/       # Reusable UI components
│   │   ├── _core/            # Core hooks and utilities
│   │   └── contexts/         # React contexts
│   └── public/               # Static assets
├── server/                    # Express backend
│   ├── _core/                # Core server logic
│   │   ├── index.ts          # Server entry point
│   │   ├── chat.ts           # AI chat endpoint
│   │   ├── oauth.ts          # Authentication
│   │   └── ...               # Other utilities
│   ├── routers/              # tRPC routers
│   └── db.ts                 # Database functions
├── drizzle/                   # Database schema
│   └── schema.ts             # Table definitions
├── shared/                    # Shared types
└── package.json              # Dependencies
```

## 🚀 Getting Started

### Prerequisites
- Node.js 22.13.0+
- pnpm 10.4.1+
- MySQL 8.0+
- OpenAI API key

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/kannada-detector.git
cd kannada-detector
```

2. **Install dependencies**
```bash
pnpm install
```

3. **Set up environment variables**
Create a `.env` file in the root directory:
```env
DATABASE_URL=mysql://user:password@localhost:3306/kannada_detector
OPENAI_API_KEY=sk-your-api-key
OPENAI_API_BASE_URL=https://api.openai.com/v1
JWT_SECRET=your-secret-key-here
OAUTH_SERVER_URL=https://oauth.example.com
VITE_OAUTH_PORTAL_URL=https://portal.example.com
```

4. **Set up the database**
```bash
pnpm run db:push
```

5. **Start development server**
```bash
pnpm run dev
```

The application will be available at `http://localhost:3000`

## 📚 API Documentation

### Chat Endpoint
**POST /api/chat**

Stream AI responses with tool calling support.

**Request:**
```json
{
  "messages": [
    {
      "role": "user",
      "content": "ಇದು ನಿಜವಾದ ಸುದ್ದಿಯೇ? (Is this real news?)"
    }
  ]
}
```

**Response:** Server-sent events with streaming text and tool calls

### OAuth Callback
**GET /api/oauth/callback**

Handles OAuth authentication callback.

### tRPC API
**POST /api/trpc**

Type-safe RPC calls for data operations.

## 🔐 Security Features

- JWT-based authentication
- Secure cookie handling
- CORS protection
- Input validation with Zod
- SQL injection prevention via ORM
- Environment variable protection
- Secure OAuth flow

## 📊 Database Schema

### Users Table
```sql
CREATE TABLE users (
  id INT AUTO_INCREMENT PRIMARY KEY,
  openId VARCHAR(64) UNIQUE NOT NULL,
  name TEXT,
  email VARCHAR(320),
  loginMethod VARCHAR(64),
  role ENUM('user', 'admin') DEFAULT 'user',
  createdAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updatedAt TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
  lastSignedIn TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## 🧪 Testing

Run tests with:
```bash
pnpm run test
```

## 📝 Code Quality

Format code:
```bash
pnpm run format
```

Type check:
```bash
pnpm run check
```

## 🏗️ Build & Deployment

### Development Build
```bash
pnpm run dev
```

### Production Build
```bash
pnpm run build
```

### Start Production Server
```bash
pnpm run start
```

## 📈 Performance Optimizations

- Vite for fast builds and HMR
- React Query for efficient data fetching
- Streaming responses for real-time feedback
- TailwindCSS for optimized styling
- Code splitting and lazy loading
- Efficient database queries with Drizzle ORM

## 🔄 Authentication Flow

1. User clicks "Sign In"
2. Redirected to OAuth provider
3. OAuth callback to `/api/oauth/callback`
4. User data stored in database
5. JWT token issued
6. User authenticated for API calls

## 📊 Analysis Pipeline

```
User Input (Kannada Text)
        ↓
Text Preprocessing
        ↓
Language Pattern Analysis
        ↓
AI Model Processing (OpenAI)
        ↓
Factual Consistency Check
        ↓
Source Credibility Assessment
        ↓
Confidence Scoring
        ↓
Results & Visualization
```

## 🎓 Research Applications

This project can be used for:
- Misinformation detection research
- Kannada NLP studies
- Fact-checking system development
- Bias detection in news
- Language model evaluation
- Information verification workflows

## 📄 License

MIT License - See LICENSE file for details

## 👥 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📧 Contact

For research inquiries and collaborations, please contact the development team.

## 🙏 Acknowledgments

- OpenAI for GPT models
- Drizzle ORM for database management
- React and TypeScript communities
- Manus platform for hosting and infrastructure

## 📚 References

- [OpenAI API Documentation](https://platform.openai.com/docs)
- [Drizzle ORM](https://orm.drizzle.team/)
- [tRPC Documentation](https://trpc.io/)
- [React Documentation](https://react.dev/)
- [Express.js Guide](https://expressjs.com/)

---

**Last Updated**: March 11, 2026
**Version**: 1.0.0
**Status**: Active Development
# kannada-detector
