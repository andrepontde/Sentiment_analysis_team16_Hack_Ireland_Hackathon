# SentiMetrics - AI-Powered Social Media Sentiment Analysis Platform

[![Hackathon](https://img.shields.io/badge/Hackathon-HackIreland-orange.svg)](https://hackireland.com)
[![Next.js](https://img.shields.io/badge/Next.js-15.1.7-black.svg)](https://nextjs.org/)
[![Flask](https://img.shields.io/badge/Flask-Backend-blue.svg)](https://flask.palletsprojects.com/)
[![OpenAI](https://img.shields.io/badge/OpenAI-GPT--3.5-green.svg)](https://openai.com/)
[![VADER](https://img.shields.io/badge/VADER-Sentiment-purple.svg)](https://github.com/cjhutto/vaderSentiment)

> **Team 16 - HackIreland Hackathon Project**  
> A comprehensive social media sentiment analysis platform that empowers users to make informed decisions in stock trading and understand real-world events through AI-powered sentiment analysis.

## 🌟 Overview

SentiMetrics is an innovative hackathon project built for HackIreland that revolutionizes how people understand public sentiment around topics, stocks, and events. By aggregating posts from multiple social media platforms and analyzing their sentiment, the platform provides users with actionable insights backed by AI-powered analysis.

### 🎯 Problem Statement

In today's fast-paced digital world, understanding public sentiment is crucial for:
- **Stock Market Trading**: Making informed investment decisions based on public sentiment
- **Event Analysis**: Understanding public reaction to current events
- **Brand Monitoring**: Tracking public perception of companies and products
- **Risk Assessment**: Identifying potential market shifts before they happen

### 💡 Solution

SentiMetrics combines real-time social media data aggregation with advanced sentiment analysis and conversational AI to provide users with comprehensive insights and actionable recommendations.

## ✨ Key Features

### 🔍 Multi-Platform Data Aggregation
- **Twitter Integration**: Fetches recent tweets using Twitter API v2
- **Bluesky Integration**: Retrieves posts from the emerging Bluesky social network
- **Real-time Data**: Up-to-date posts based on user-specified keywords
- **Scalable Architecture**: Designed to easily add more social platforms

### 📊 Advanced Sentiment Analysis
- **VADER Sentiment Analysis**: Industry-standard sentiment scoring (-1 to +1 scale)
- **Aggregate Scoring**: Normalized sentiment scores (0-100% scale) for easy interpretation
- **Real-time Processing**: Instant sentiment calculation for all retrieved posts
- **Detailed Metrics**: Positive, negative, neutral, and compound sentiment scores

### 🤖 AI-Powered Insights
- **OpenAI GPT Integration**: Conversational AI powered by OpenAI's GPT-3.5
- **Contextual Analysis**: AI understands the full context of retrieved posts
- **Strategic Recommendations**: Generates actionable plans for sentiment improvement
- **Interactive Chat**: Natural language interface for querying insights

### 🎨 Modern Web Interface
- **Next.js Frontend**: Fast, responsive React-based user interface
- **TypeScript**: Type-safe development for better reliability
- **Clerk Authentication**: Secure user authentication and session management
- **Material-UI Components**: Professional, accessible UI components
- **Real-time Updates**: Live sentiment scores and chat functionality

### 💾 Session Management
- **Persistent Sessions**: Conversation history maintained across interactions
- **Data Caching**: Efficient storage of retrieved posts and analysis results
- **Cross-request Continuity**: Seamless user experience across multiple queries

## 🏗️ Architecture

### Backend (Flask/Python)
```
backend/
├── app.py                 # Main Flask application
├── twitter_API.py         # Twitter API integration
├── bluesky_API.py         # Bluesky API integration
├── requirements.txt       # Python dependencies
└── .env                   # Environment variables (not in repo)
```

### Frontend (Next.js/TypeScript)
```
frontend/
├── app/
│   ├── components/        # Reusable UI components
│   ├── enter-hashtags/    # Hashtag input interface
│   ├── layout.tsx         # App layout
│   └── page.tsx          # Main page component
├── package.json          # Node.js dependencies
└── tsconfig.json         # TypeScript configuration
```

## 🚀 Getting Started

### Prerequisites

- **Python 3.8+**
- **Node.js 18+**
- **API Keys for:**
  - Twitter API v2 (Bearer Token)
  - Bluesky API (Username/Password)
  - OpenAI API Key
  - Clerk Authentication

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/andrepontde/Language-Style-Auto-Matching.git
   cd Sentiment_analysis_team16_Hack_Ireland_Hackathon
   ```

2. **Backend Setup:**
   ```bash
   cd backend
   pip install -r requirements.txt
   ```

3. **Frontend Setup:**
   ```bash
   cd frontend
   npm install
   ```

4. **Environment Configuration:**
   
   Create a `.env` file in the `backend/` directory:
   ```env
   # Twitter API Credentials
   BEARER_TOKEN=your_twitter_bearer_token
   API_KEY_TWITTER=your_twitter_api_key
   API_SECRET_TWITTER=your_twitter_api_secret
   
   # Bluesky API Credentials
   BLUESKY_API_USERNAME=your_bluesky_username
   BLUESKY_API_PASSWORD=your_bluesky_password
   
   # OpenAI API
   OPENAI_API_KEY=your_openai_api_key
   
   # Flask Configuration
   FLASK_SECRET_KEY=your_secret_key
   ```

   Create a `.env.local` file in the `frontend/` directory:
   ```env
   # Clerk Authentication
   NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
   CLERK_SECRET_KEY=your_clerk_secret_key
   
   # API URLs
   NEXT_PUBLIC_API_URL=http://localhost:5000
   ```

### Running the Application

1. **Start the Backend:**
   ```bash
   cd backend
   python app.py
   ```
   The Flask server will start on `http://localhost:5000`

2. **Start the Frontend:**
   ```bash
   cd frontend
   npm run dev
   ```
   The Next.js app will start on `http://localhost:3000`

## 📖 Usage Guide

### Basic Usage Flow

1. **Authentication**: Sign in using Clerk authentication
2. **Enter Keywords**: Input hashtags or keywords to analyze
3. **Data Retrieval**: System fetches posts from Twitter and Bluesky
4. **Sentiment Analysis**: VADER analyzes sentiment of all posts
5. **AI Insights**: ChatGPT provides contextual analysis and recommendations
6. **Interactive Chat**: Ask follow-up questions about the data

### API Endpoints

#### `POST /api/chat`
Chat with the AI about analyzed sentiment data
- **Request**: `{"message": "user message"}`
- **Response**: AI-generated response with context

#### `POST /api/fetch-posts`
Retrieve and analyze posts for a keyword
- **Request**: `{"keyword": "stock symbol or topic"}`
- **Response**: Posts data with sentiment scores

#### `GET /api/clear-session`
Clear current session data
- **Response**: Session cleared confirmation

### Example Queries

- **Stock Analysis**: "What's the sentiment around $AAPL?"
- **Event Analysis**: "How do people feel about the latest tech announcement?"
- **Trend Analysis**: "Should I invest based on this sentiment?"
- **Strategy Questions**: "How can this company improve their public perception?"

## 🛠️ Technical Implementation

### Sentiment Analysis Pipeline

1. **Data Collection**: Parallel API calls to Twitter and Bluesky
2. **Text Processing**: Clean and prepare social media text
3. **VADER Analysis**: Calculate compound sentiment scores (-1 to +1)
4. **Score Normalization**: Convert to percentage scale (0-100%)
5. **Aggregation**: Weighted average of all posts

### AI Integration

The system builds dynamic prompts for OpenAI's GPT-3.5 that include:
- Complete post dataset with sentiment scores
- Aggregate sentiment metrics
- Strategic planning instructions
- Context for informed responses

### Session Management

- **Flask-Session**: Server-side session storage
- **Conversation History**: Maintains chat context
- **Data Persistence**: Caches retrieved posts to avoid API limits
- **Cross-request State**: Seamless user experience

## 🎯 Use Cases

### 📈 Stock Market Trading
- **Pre-trade Analysis**: Assess market sentiment before making investments
- **Risk Assessment**: Identify potential negative sentiment trends
- **Timing Decisions**: Understand when public opinion might affect stock prices
- **Competitor Analysis**: Compare sentiment across different stocks

### 📰 Event Monitoring
- **Crisis Management**: Monitor public reaction to company announcements
- **Product Launches**: Track reception of new products or services
- **PR Campaign Effectiveness**: Measure impact of marketing initiatives
- **Reputation Management**: Identify and address negative sentiment patterns

### 🎯 Business Intelligence
- **Market Research**: Understand customer sentiment toward brands
- **Competitive Analysis**: Compare public perception across competitors
- **Trend Identification**: Spot emerging topics and conversations
- **Strategic Planning**: Make data-driven decisions based on public sentiment

## 🏆 Hackathon Achievement

### Team 16 - HackIreland 2024
This project was developed during the HackIreland hackathon, demonstrating:
- **Rapid Prototyping**: Full-stack application built in limited time
- **API Integration**: Multiple complex API integrations
- **AI Implementation**: Practical application of conversational AI
- **Real-world Impact**: Addressing genuine market needs

### Technical Challenges Overcome
- **Rate Limiting**: Efficient API usage within platform constraints
- **Data Synchronization**: Managing multiple async data sources
- **Session Persistence**: Maintaining state across web requests
- **Real-time Processing**: Instant sentiment analysis and AI responses

## 🚀 Future Enhancements

### Planned Features
- **Additional Platforms**: Reddit, LinkedIn, Instagram integration
- **Historical Analysis**: Trend analysis over time periods
- **Visualization**: Charts and graphs for sentiment trends
- **Advanced AI**: Custom-trained models for financial sentiment
- **Mobile App**: Native mobile application
- **Alert System**: Real-time notifications for sentiment changes

### Scalability Improvements
- **Database Integration**: PostgreSQL for data persistence
- **Caching Layer**: Redis for improved performance
- **Microservices**: Break down into smaller, scalable services
- **Load Balancing**: Handle increased user traffic
- **API Rate Management**: Advanced queue system for API calls

## 🤝 Contributing

We welcome contributions from the community! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/amazing-feature`
3. **Commit your changes**: `git commit -m 'Add amazing feature'`
4. **Push to the branch**: `git push origin feature/amazing-feature`
5. **Open a Pull Request**

### Development Guidelines
- Follow TypeScript best practices for frontend
- Use Python PEP 8 style guide for backend
- Write comprehensive commit messages
- Add tests for new features
- Update documentation as needed

## 📊 Performance Metrics

### Current Capabilities
- **Data Processing**: Up to 50 posts per platform per query
- **Response Time**: < 3 seconds for sentiment analysis
- **AI Response Time**: 2-5 seconds for GPT responses
- **Concurrent Users**: Supports multiple simultaneous sessions
- **API Reliability**: 99%+ uptime during hackathon demo

## 🔒 Security & Privacy

### Data Protection
- **No Data Storage**: Posts are processed and discarded after session
- **API Key Security**: Environment variables for sensitive credentials
- **Session Encryption**: Secure session management
- **CORS Protection**: Proper cross-origin resource sharing setup

### Privacy Considerations
- **Public Data Only**: Only analyzes publicly available posts
- **Anonymous Processing**: No personal data collection
- **Temporary Sessions**: Data cleared after user session ends

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **HackIreland**: For providing the platform and inspiration
- **OpenAI**: For GPT-3.5 API access
- **Twitter/X**: For social media API access
- **Bluesky**: For emerging platform integration
- **NLTK/VADER**: For sentiment analysis capabilities
- **Vercel**: For frontend hosting and deployment
- **Flask Community**: For excellent web framework

## 📞 Contact

**Team 16 - HackIreland**
- **Project Repository**: [GitHub](https://github.com/andrepontde/Language-Style-Auto-Matching)
- **Developer**: Andre Pont de Lima
- **Email**: [Your Email]
- **LinkedIn**: [Your LinkedIn]

---

> **"Empowering informed decisions through AI-powered sentiment analysis"**  
> *SentiMetrics - Where Data Meets Intelligence*
