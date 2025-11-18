# SahaayAI - AI-Powered Assistant for Underserved Communities

[![Python 3.13](https://img.shields.io/badge/python-3.13-blue.svg)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115.0-green.svg)](https://fastapi.tiangolo.com/)
[![Gemini 2.0](https://img.shields.io/badge/Gemini-2.0%20Flash-orange.svg)](https://ai.google.dev/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## 🌟 Overview

SahaayAI is an AI-powered multilingual assistant designed to deliver simplified, actionable guidance to underserved communities across India. The platform supports multiple communication channels including SMS, WhatsApp, Voice (IVR), and Web, making essential services accessible to everyone regardless of literacy level or connectivity.

### 🎯 The Problem

Millions in underserved communities face barriers accessing essential services:
- 🌍 **Language barriers** - 650+ languages in India with limited digital content
- 📱 **Low digital literacy** - Complex government portals are difficult to navigate  
- 📡 **Poor connectivity** - Limited internet access in rural areas
- ❌ **Lack of actionable guidance** - Information exists but isn't accessible or understandable

### ✨ The Solution

SahaayAI bridges this gap by:
- 🤖 Converting complex information into **easy-to-understand action plans**
- 🌍 Supporting **12 Indian languages** with automatic translation
- 📱 Working via **SMS, WhatsApp, Voice, and Web** channels
- 📖 Adapting content to user's **literacy level** and **location**
- 🎯 Providing **step-by-step guidance** with document checklists

---

## ✨ Key Features

### 🌍 Multilingual Support
- **12 Indian Languages**: English, Hindi, Bengali, Tamil, Telugu, Marathi, Gujarati, Kannada, Malayalam, Punjabi, Odia, Assamese
- **Automatic Language Detection**: Identifies language from user input
- **Real-time Translation**: Translates AI responses to preferred language
- **Dialect Support**: Handles regional variations

### 📱 Multi-Channel Communication
- ✅ **SMS** - Works on basic phones, automatic message chunking for long text
- ✅ **WhatsApp** - Rich formatting with emojis, bold text, and media support
- ✅ **Voice/IVR** - Interactive voice response with text-to-speech in multiple languages
- ✅ **Web Interface** - Responsive chat UI with voice input/output
- 📥 **Webhooks** - Real-time message processing from Twilio

### 🤖 AI-Powered Intelligence
- **Google Gemini 2.0 Flash** - State-of-the-art LLM for understanding and generation
- **Intent Recognition** - Automatically classifies queries into domains (health, agriculture, finance, etc.)
- **Context-Aware** - Uses location, literacy level, conversation history
- **Multi-turn Conversations** - Maintains context across messages
- **Confidence Scoring** - Measures certainty of responses

### 📋 Smart Action Plans
- **Step-by-Step Guidance** - Breaks complex tasks into actionable steps
- **Document Checklists** - Lists required documents for schemes/services
- **Eligibility Checking** - Verifies user eligibility criteria
- **Resource Directory** - Helpline numbers and contact information
- **Risk Alerts** - Time-sensitive warnings and important notices
- **Progress Tracking** - Monitors completion of action steps

### 📖 Accessibility Features
- **Literacy-Level Adaptation** - Simplifies language (low/medium/high literacy)
- **Text-to-Speech** - Audio output for all responses in user's language
- **Visual Guides** - Icon-based instructions for low-literacy users
- **SMS-Optimized** - Works on basic phones without internet
- **Offline-First Design** - Handles intermittent connectivity

### 🔒 Security & Privacy
- **AES-256 Encryption** - All PII encrypted at rest
- **JWT Authentication** - Secure API access with token expiration
- **Rate Limiting** - 60 requests/minute, 1000 requests/hour per user
- **Minimal Data Collection** - Only essential information stored
- **GDPR Compliant** - Right to deletion, data portability
- **Audit Logging** - Comprehensive activity tracking

### 🚀 Production-Ready Architecture
- **FastAPI** - High-performance async REST API framework
- **Docker Support** - Containerized deployment with docker-compose
- **Redis Caching** - Sub-millisecond lookups for user data
- **Horizontal Scaling** - Stateless design supports multiple instances
- **Health Monitoring** - Prometheus metrics and structured logging
- **Database Flexibility** - SQLite for dev, PostgreSQL for production

---

## 🎯 Use Cases

| Domain | Example Query | AI Response |
|--------|---------------|-------------|
| **Healthcare** | "मुझे बुखार और खांसी है" (I have fever and cough) | Symptom triage, nearby PHC locations, medication guidance, when to visit doctor |
| **Agriculture** | "ಬರಗಾಲದಿಂದ ಬೆಳೆ ಹಾನಿಯಾಗಿದೆ" (Crop damaged by drought) | Compensation schemes, eligibility criteria, required documents, application steps |
| **Finance** | "আমি কিভাবে ব্যাংক অ্যাকাউন্ট খুলব?" (How to open bank account?) | Required documents, nearest branch, KYC process, fraud prevention tips |
| **Gov. Schemes** | "Am I eligible for PM-KISAN?" | Eligibility check based on location, application process, document list, helpline |
| **Education** | "மகளுக்கு கல்வி உதவித்தொகை" (Education scholarship for daughter) | Relevant schemes, eligibility, deadlines, application process, required documents |

---

## 🚀 Quick Start

### Prerequisites
- **Python 3.9+** (Python 3.13 recommended)
- **Google Gemini API key** - [Get free API key](https://makersuite.google.com/app/apikey)
- **(Optional) Twilio Account** - For SMS/WhatsApp ([Sign up](https://www.twilio.com))

### Installation

#### Option 1: Automated Installation (Recommended)
```bash
# Clone repository
git clone <repository-url>
cd SahaayAI

# Run automated installer
./install.sh
```

The installer will:
- ✅ Create Python virtual environment
- ✅ Install all dependencies from requirements.txt
- ✅ Create .env file from template
- ✅ Initialize SQLite database
- ✅ Create storage directories

#### Option 2: Manual Installation
```bash
# Clone repository
git clone <repository-url>
cd SahaayAI

# Create virtual environment
python3 -m venv sahaayAI

# Activate virtual environment
source sahaayAI/bin/activate  # On macOS/Linux
# OR
sahaayAI\Scripts\activate     # On Windows

# Install dependencies
pip install -r requirements.txt

# Create .env file
cp .env.example .env
nano .env  # Edit with your API keys
```

### Configuration

Edit `.env` file with your credentials:

#### Required Configuration
```bash
# Gemini API (Required)
GEMINI_API_KEY=your_gemini_api_key_here

# Security Keys (Required - generate random strings)
SECRET_KEY=your_secret_key_here
ENCRYPTION_KEY=your_encryption_key_here
```

#### Optional Configuration (for SMS/WhatsApp)
```bash
# Twilio Credentials (Optional)
TWILIO_ACCOUNT_SID=your_account_sid
TWILIO_AUTH_TOKEN=your_auth_token
TWILIO_PHONE_NUMBER=+1234567890
```

### Start the Server

```bash
# Activate virtual environment
source sahaayAI/bin/activate

# Start FastAPI server
uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload
```

Server starts at: **http://localhost:8000**

### Access the Application

| Interface | URL | Description |
|-----------|-----|-------------|
| 🌐 **Web UI** | http://localhost:8000/ | Interactive chat interface |
| 📚 **API Docs** | http://localhost:8000/docs | Swagger UI with all endpoints |
| 📖 **ReDoc** | http://localhost:8000/redoc | Alternative API documentation |
| ❤️ **Health Check** | http://localhost:8000/health | Service status and diagnostics |
| 🔌 **Webhook Status** | http://localhost:8000/webhooks/health | SMS/WhatsApp webhook health |

---

## 📝 API Examples

### 1. Send Web Message
```bash
curl -X POST http://localhost:8000/api/v1/message/web \
  -H "Content-Type: application/json" \
  -d '{
    "phone_number": "+919876543210",
    "message": "How do I apply for PM-KISAN scheme?",
    "language": "en",
    "literacy_level": "medium"
  }'
```

**Response:**
```json
{
  "success": true,
  "response": "To apply for PM-KISAN scheme:\n\n1. Check eligibility...",
  "language": "en",
  "conversation_id": "conv_123",
  "action_plan": {
    "steps": [...],
    "documents": ["Aadhaar", "Bank Account", "Land Records"]
  }
}
```

### 2. Send SMS (Requires Twilio)
```bash
curl -X POST http://localhost:8000/api/v1/send/sms \
  -H "Content-Type: application/json" \
  -d '{
    "phone_number": "+919876543210",
    "message": "Hello from SahaayAI! Reply with your question."
  }'
```

### 3. Send WhatsApp (Requires Twilio)
```bash
curl -X POST http://localhost:8000/api/v1/send/whatsapp \
  -H "Content-Type: application/json" \
  -d '{
    "phone_number": "+919876543210",
    "message": "*Welcome to SahaayAI!* 🎉\n\nAsk me anything about government schemes."
  }'
```

### 4. Generate Audio Response
```bash
curl -X POST http://localhost:8000/api/v1/voice/tts \
  -H "Content-Type: application/json" \
  -d '{
    "text": "नमस्ते, मैं सहाय एआई हूं",
    "language": "hi"
  }'
```

### 5. Check Message Status
```bash
curl http://localhost:8000/api/v1/send/status/SM1234567890
```

---

## 📚 API Endpoints

### Messaging Endpoints
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/v1/message/web` | Send message via web interface |
| POST | `/api/v1/message/sms` | Process SMS message (internal) |
| POST | `/api/v1/message/whatsapp` | Process WhatsApp message (internal) |

### Send Endpoints (Twilio Integration)
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/v1/send/sms` | Send SMS to phone number |
| POST | `/api/v1/send/whatsapp` | Send WhatsApp message |
| GET | `/api/v1/send/status/{sid}` | Get message delivery status |
| POST | `/api/v1/send/validate-phone` | Validate phone number |

### Webhook Endpoints (Twilio Callbacks)
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/webhooks/sms/incoming` | Receive incoming SMS from Twilio |
| POST | `/webhooks/whatsapp/incoming` | Receive incoming WhatsApp messages |
| POST | `/webhooks/sms/status` | SMS delivery status callback |
| POST | `/webhooks/whatsapp/status` | WhatsApp delivery status callback |
| GET | `/webhooks/health` | Webhook system health check |

### Voice Endpoints
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/v1/voice/incoming` | Handle incoming voice calls |
| POST | `/api/v1/voice/tts` | Text-to-speech generation |
| POST | `/api/v1/voice/gather` | Process voice input |

### Health & Monitoring
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/health` | API health check and status |
| GET | `/metrics` | Prometheus metrics |
| GET | `/` | Redirect to web interface |

---

## 🧪 Testing

### Run Integration Tests
```bash
# Activate virtual environment
source sahaayAI/bin/activate

# Run all unit tests
pytest tests/ -v

# Run with coverage report
pytest tests/ --cov=app --cov-report=html

# View coverage report
open htmlcov/index.html
```

### Manual Testing

#### Test Web Interface
1. Open http://localhost:8000/
2. Type a question in any supported language
3. View AI response with action plan

#### Test SMS/WhatsApp (Requires Twilio Setup)
1. Configure Twilio credentials in `.env`
2. Use ngrok to expose local server: `ngrok http 8000`
3. Configure webhook URLs in Twilio Console:
   - SMS: `https://your-ngrok-url/webhooks/sms/incoming`
   - WhatsApp: `https://your-ngrok-url/webhooks/whatsapp/incoming`
4. Send SMS or WhatsApp message to your Twilio number
5. Check logs for processing: `tail -f logs/sahaayai.log`
6. Test via API documentation at http://localhost:8000/docs

---

## 🛠️ Technology Stack

### Backend Framework
- **Python 3.13** - Core programming language
- **FastAPI 0.115.0** - High-performance async web framework
- **Uvicorn** - ASGI server with WebSocket support
- **Pydantic** - Data validation and settings management

### Database & Caching
- **SQLAlchemy 2.0.36** - ORM for database operations
- **SQLite** - Lightweight database for development/POC
- **Redis 5.2.0** - In-memory cache for user sessions and preferences
- **Alembic** - Database migration tool

### AI & Machine Learning
- **Google Gemini 2.0 Flash** - Primary LLM via google-generativeai SDK
- **langdetect** - Language identification
- **googletrans** - Translation service (fallback)

### Communication Services
- **Twilio 9.3.7** - SMS, WhatsApp, and Voice integration (configured via webhooks)
- **WebSocket** - Real-time web communication

### Audio & Media Processing
- **gTTS** - Google Text-to-Speech for audio generation
- **PyDub** - Audio file manipulation
- **Pillow** - Image processing for visual guides

### Security & Authentication
- **python-jose** - JWT token generation and validation
- **passlib[bcrypt]** - Password hashing
- **cryptography 44.0.0** - AES-256 encryption for PII
- **python-dotenv** - Environment variable management

### Monitoring & Observability
- **prometheus-client** - Metrics collection
- **structlog** - Structured logging
- **psutil** - System resource monitoring

### Development Tools
- **pytest** - Unit and integration testing
- **black** - Code formatting
- **flake8** - Code linting
- **mypy** - Static type checking

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                    Communication Channels                    │
│         SMS  │  WhatsApp  │  Voice/IVR  │  Web UI          │
└────────────────────┬────────────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────────────┐
│                  API Gateway (FastAPI)                      │
│    Rate Limiting  │  Authentication  │  Request Routing    │
└────────────────────┬────────────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────────────┐
│                    Service Layer                            │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │  Twilio      │  │  Translation │  │  Multimodal  │     │
│  │  Service     │  │  Service     │  │  Service     │     │
│  └──────────────┘  └──────────────┘  └──────────────┘     │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │  AI Service  │  │  Action      │  │  Context     │     │
│  │  (Gemini)    │  │  Planner     │  │  Manager     │     │
│  └──────────────┘  └──────────────┘  └──────────────┘     │
└────────────────────┬────────────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────────────┐
│              AI Processing (Gemini API)                     │
│  - Intent Extraction  - Response Generation                │
│  - Prompt Engineering - Multi-turn Context                 │
└────────────────────┬────────────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────────────┐
│                Knowledge Base & Data Layer                  │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │  Government  │  │  Healthcare  │  │  Agriculture │     │
│  │  Schemes     │  │  Guidelines  │  │  Advisory    │     │
│  └──────────────┘  └──────────────┘  └──────────────┘     │
└────────────────────┬────────────────────────────────────────┘
                     │
┌────────────────────▼────────────────────────────────────────┐
│                    Storage Layer                            │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐     │
│  │   SQLite     │  │     Redis    │  │  File Store  │     │
│  │   Database   │  │     Cache    │  │  (Audio/Img) │     │
│  └──────────────┘  └──────────────┘  └──────────────┘     │
└─────────────────────────────────────────────────────────────┘
```

---

## 📊 Data Models

### User
```python
- id: Primary Key
- phone_number: Encrypted, unique identifier
- preferred_language: ISO language code
- literacy_level: Enum(low, medium, high)
- location_district: String
- location_state: String
- created_at: Timestamp
- last_active: Timestamp
```

### Conversation
```python
- id: Primary Key
- user_id: Foreign Key -> User
- channel: Enum(SMS, WhatsApp, Voice, Web)
- domain: Enum(health, agriculture, finance, etc.)
- started_at: Timestamp
- ended_at: Timestamp (nullable)
- status: Enum(active, completed, abandoned)
```

### Message
```python
- id: Primary Key
- conversation_id: Foreign Key -> Conversation
- role: Enum(user, assistant)
- content: Text (encrypted)
- language: ISO language code
- audio_file_path: String (nullable)
- timestamp: Timestamp
```

### ActionPlan
```python
- id: Primary Key
- conversation_id: Foreign Key -> Conversation
- domain: String
- summary: Text
- steps: JSON array of steps
- documents_required: JSON array
- estimated_time: String
- risk_alerts: JSON array
- resources: JSON array
- created_at: Timestamp
```

---

## 📁 Project Structure

```
SahaayAI/
├── app/
│   ├── main.py                      # FastAPI application entry
│   ├── config.py                    # Configuration settings
│   ├── database.py                  # Database models and connection
│   │
│   ├── api/
│   │   ├── middleware/
│   │   │   ├── auth.py              # JWT authentication
│   │   │   └── rate_limit.py        # Rate limiting middleware
│   │   └── routes/
│   │       ├── health.py            # Health check endpoints
│   │       ├── messaging.py         # Message processing endpoints
│   │       ├── send.py              # SMS/WhatsApp sending endpoints
│   │       ├── voice.py             # IVR and TTS endpoints
│   │       └── webhooks.py          # Twilio webhook handlers
│   │
│   ├── services/
│   │   ├── ai_service.py            # Gemini API integration
│   │   ├── action_planner.py        # Action plan generation
│   │   ├── translation_service.py   # Multi-language translation
│   │   ├── multimodal_service.py    # Audio/image processing
│   │   └── twilio_service.py        # Twilio SMS/WhatsApp integration
│   │
│   ├── models/                      # SQLAlchemy models (in database.py)
│   │
│   └── utils/
│       ├── encryption.py            # AES-256 encryption utilities
│       ├── logger.py                # Structured logging setup
│       └── validation.py            # Input validation and sanitization
│
├── data/
│   ├── knowledge_base/
│   │   └── schemes.json             # Government schemes database
│   └── prompts/
│       └── system_prompts.json      # AI prompt templates
│
├── frontend/
│   ├── index.html                   # Web chat interface
│   ├── app.js                       # Frontend JavaScript
│   ├── styles.css                   # Styling
│   └── README.md                    # Frontend documentation
│
├── tests/
│   ├── test_api.py                  # API endpoint tests
│   ├── test_services.py             # Service layer tests
│   └── __init__.py
│
├── logs/                            # Application logs
├── storage/
│   └── audio/                       # Generated audio files
│
├── docker-compose.yml               # Docker orchestration
├── Dockerfile                       # Container definition
├── requirements.txt                 # Python dependencies
├── .env.example                     # Environment template
├── install.sh                       # Automated setup script
├── start.sh                         # Application startup script
├── technical_overview.tex           # LaTeX technical document
├── TECHNICAL_ARCHITECTURE.pdf       # PDF architecture documentation
└── README.md                        # This file
```

---

## 🔐 Security Features

### Data Protection
- **AES-256 Encryption**: All PII (phone numbers, location) encrypted at rest
- **TLS/HTTPS**: All API communication encrypted in transit
- **Password Security**: Bcrypt hashing for any stored credentials

### Authentication & Authorization
- **JWT Tokens**: HS256 algorithm with 30-minute expiration
- **API Key Management**: Secure storage of external API keys
- **Rate Limiting**: 60 requests/minute, 1000 requests/hour per user

### Privacy-First Design
- **Minimal Data Collection**: Only essential information stored
- **Data Retention**: 90-day automatic deletion policy
- **Consent Management**: Explicit user consent required
- **Anonymized Logging**: No PII in application logs
- **Right to Deletion**: Users can request immediate data removal

### Compliance
- **GDPR Ready**: Data portability and deletion support
- **Audit Trail**: Comprehensive logging for security review
- **Secure Configuration**: Environment variables for secrets

---

## 🚀 Deployment

### Docker Deployment (Recommended)

```bash
# Build and start all services
docker-compose up -d

# View logs
docker-compose logs -f

# Stop services
docker-compose down
```

### Manual Production Deployment

```bash
# Install dependencies
pip install -r requirements.txt

# Set production environment
export DEBUG=False
export DATABASE_URL=postgresql://user:pass@host/db

# Run with Gunicorn
gunicorn app.main:app -w 4 -k uvicorn.workers.UvicornWorker \
  --bind 0.0.0.0:8000
```

### Environment Variables for Production

```bash
# Required
GEMINI_API_KEY=your_key
SECRET_KEY=strong_random_key
ENCRYPTION_KEY=strong_random_key

# Database (Production)
DATABASE_URL=postgresql://user:password@host:5432/sahaayai

# Redis
REDIS_HOST=redis-server
REDIS_PORT=6379
REDIS_PASSWORD=your_password

# Twilio
TWILIO_ACCOUNT_SID=your_sid
TWILIO_AUTH_TOKEN=your_token
TWILIO_PHONE_NUMBER=+1234567890

# Production Settings
DEBUG=False
LOG_LEVEL=INFO
DATA_RETENTION_DAYS=90
```

---

## 📈 Monitoring & Observability

### Health Checks
```bash
# API health
curl http://localhost:8000/health

# Webhook health
curl http://localhost:8000/webhooks/health
```

### Prometheus Metrics
Available at `/metrics` endpoint:
- Request count by endpoint
- Response time histograms
- Error rates
- Active connections

### Logging
Structured JSON logs in `logs/sahaayai.log`:
```json
{
  "timestamp": "2025-11-18T12:00:00Z",
  "level": "INFO",
  "message": "Message processed",
  "user_id": "user_123",
  "conversation_id": "conv_456",
  "language": "hi",
  "domain": "health"
}
```

---

## 🤝 Contributing

We welcome contributions! Please follow these guidelines:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes
4. Run tests: `pytest tests/`
5. Run linting: `black . && flake8`
6. Commit changes: `git commit -m 'Add amazing feature'`
7. Push to branch: `git push origin feature/amazing-feature`
8. Open a Pull Request

---

## 🎓 Use Case Examples

### Example 1: Healthcare Query
**User:** "मुझे बुखार है और सिर दर्द है" (I have fever and headache)

**AI Response:**
```
लक्षण: बुखार और सिर दर्द

तत्काल कदम:
1. बुखार की जांच करें
2. पर्याप्त पानी पिएं
3. आराम करें

अगर 2 दिन में ठीक न हों, तो नजदीकी PHC जाएं:
📍 राजकीय स्वास्थ्य केंद्र, आपके जिले में
📞 हेल्पलाइन: 104

चेतावनी: अगर बुखार 102°F से ज्यादा हो, तुरंत डॉक्टर से मिलें।
```

### Example 2: Government Scheme
**User:** "How to apply for PM-KISAN scheme?"

**AI Response:**
```
PM-KISAN Scheme Application

Eligibility:
✓ Small/marginal farmer
✓ Landholding up to 2 hectares
✓ Indian citizen

Required Documents:
• Aadhaar Card
• Bank Account (linked to Aadhaar)
• Land ownership documents

Steps:
1. Visit PM-KISAN portal or nearest CSC
2. Fill application form
3. Upload documents
4. Submit and get acknowledgment

Processing Time: 15-30 days
Helpline: 155261 / 011-24300606
```

---

## 📊 Performance Metrics

### Current Capabilities
- **Response Time**: < 2 seconds for most queries
- **Supported Languages**: 12 Indian languages
- **Concurrent Users**: 10,000+ with horizontal scaling
- **Message Throughput**: 60 messages/min per user
- **Uptime**: 99.9% with health monitoring

### Scalability
- **Horizontal Scaling**: Add more FastAPI instances
- **Database**: Easily switch to PostgreSQL for production
- **Caching**: Redis reduces load on database and AI API
- **Load Balancing**: Ready for nginx/HAProxy

---

## 🗺️ Roadmap

### Phase 1: Core Features (✅ Completed)
- ✅ Multi-language support (12 languages)
- ✅ SMS/WhatsApp integration
- ✅ Voice/IVR support
- ✅ Web interface
- ✅ Action plan generation
- ✅ Knowledge base for government schemes

### Phase 2: Enhanced Features (🚧 In Progress)
- 🚧 Offline mobile app with sync
- 🚧 Voice biometric authentication
- 🚧 Advanced dialect recognition
- 🚧 Computer vision for document scanning

### Phase 3: Scale & Integration (📋 Planned)
- 📋 Integration with government APIs
- 📋 Predictive assistance
- 📋 Multi-region deployment
- 📋 Advanced analytics dashboard

---

## 🐛 Troubleshooting

### Common Issues

#### 1. Server won't start
```bash
# Check if port 8000 is in use
lsof -i :8000

# Use different port
uvicorn app.main:app --port 8001
```

#### 2. Gemini API errors
```bash
# Verify API key
echo $GEMINI_API_KEY

# Check API key in .env file
cat .env | grep GEMINI_API_KEY
```

#### 3. Twilio not working
```bash
# Check credentials
python -c "from app.services.twilio_service import twilio_service; print(twilio_service.enabled)"

# Test via API
curl -X POST http://localhost:8000/api/v1/send/sms \
  -H "Content-Type: application/json" \
  -d '{"phone_number": "+1234567890", "message": "test"}'
```

#### 4. Database errors
```bash
# Reset database
rm sahaayai.db
python -c "from app.database import init_db; init_db()"
```

---

## 📞 Support

For questions or issues:
- 📧 Email: support@sahaayai.org (if applicable)
- 🐛 Issues: [GitHub Issues](repository-url/issues)
- 📖 Documentation: [Wiki](repository-url/wiki)

---

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 🙏 Acknowledgments

- **Google Gemini** - Advanced AI capabilities
- **Twilio** - SMS and WhatsApp integration
- **FastAPI** - Excellent web framework
- **Open Source Community** - All the amazing libraries

---

## 📊 Project Status

**Current Version:** 1.0.0-POC  
**Status:** ✅ Production-Ready POC  
**Last Updated:** November 18, 2025

### Implementation Status

| Feature | Status | Notes |
|---------|--------|-------|
| Web Interface | ✅ Complete | Responsive chat UI |
| SMS Integration | ✅ Complete | Twilio webhooks configured |
| WhatsApp Integration | ✅ Complete | Rich formatting support |
| Voice/IVR | ✅ Complete | Text-to-speech in 12 languages |
| Multi-language | ✅ Complete | 12 Indian languages |
| Action Plans | ✅ Complete | Step-by-step guidance |
| Database | ✅ Complete | SQLite (dev), PostgreSQL-ready |
| Caching | ✅ Complete | Redis integration |
| Security | ✅ Complete | Encryption, JWT, rate limiting |
| Documentation | ✅ Complete | API docs, guides, tests |
| Docker Support | ✅ Complete | docker-compose ready |
| Monitoring | ✅ Complete | Prometheus metrics |

---

**Built with ❤️ for underserved communities across India**
