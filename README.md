# 🌾 KisanMitra

### Agentic AI Farming Assistant for Indian Farmers

KisanMitra is an **Agentic AI-powered agricultural assistant** designed to help Indian farmers make better day-to-day farming decisions using their actual farm information, real weather data, real agricultural market information, crop knowledge, and government resources.

Unlike a conventional chatbot, KisanMitra follows an **agentic workflow** where the AI understands the farmer's situation, identifies the information required, dynamically selects tools, retrieves real data, analyzes the results, creates an actionable plan, saves decisions, and schedules follow-ups.

---

## 🚜 What is KisanMitra?

Farmers often need to make decisions based on multiple factors such as:

* 🌱 Crop condition
* 🌦️ Weather
* 💧 Irrigation
* 🌾 Soil
* 📍 Farm location
* 📈 Market prices
* 🏛️ Government schemes
* 📅 Crop stage
* 🐛 Pest and disease symptoms

KisanMitra brings these factors together into one intelligent farming assistant.

A farmer can ask:

> "My tomato leaves are turning yellow and rain is expected. What should I do?"

KisanMitra can:

```text
Understand the farmer's situation
        ↓
Load farmer profile
        ↓
Identify location and crop
        ↓
Retrieve real weather information
        ↓
Retrieve crop knowledge
        ↓
Analyze the situation using Gemini
        ↓
Create an action plan
        ↓
Save the recommendation
        ↓
Schedule a follow-up
        ↓
Give the farmer a simple answer
```

---

# 🤖 Agentic AI Architecture

KisanMitra is designed as a real tool-using AI agent.

```text
                    👨‍🌾 FARMER
                         │
                         ▼
                ┌─────────────────┐
                │    UNDERSTAND   │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ LOAD FARMER     │
                │ CONTEXT         │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ GEMINI AGENT    │
                │ REASONING       │
                └────────┬────────┘
                         │
                Dynamic Tool Selection
                         │
          ┌──────────────┼──────────────┐
          ▼              ▼              ▼
      🌦️ Weather     🌾 Crop        📈 Market
                       Knowledge
          │              │              │
          └──────────────┼──────────────┘
                         ▼
                ┌─────────────────┐
                │ ANALYZE REAL    │
                │ RESULTS         │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ ACTION PLAN     │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ SAVE DECISION   │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ FOLLOW-UP       │
                └────────┬────────┘
                         │
                         ▼
                   👨‍🌾 FARMER
```

---

# ✨ Key Features

## 🤖 Agentic AI

KisanMitra dynamically determines which information is required for a farmer's question.

Available tools include:

* `get_farmer_profile()`
* `get_land_details()`
* `get_weather()`
* `get_crop_knowledge()`
* `get_market_prices()`
* `get_government_schemes()`
* `create_action_plan()`
* `schedule_followup()`

The agent does **not** blindly execute every tool for every request.

For example:

```text
Weather question
      ↓
Weather Tool
```

While:

```text
Crop health question
      ↓
Farmer Profile
      ↓
Crop Knowledge
      ↓
Weather
      ↓
Gemini Analysis
      ↓
Action Plan
```

---

# 🌦️ Real Weather Intelligence

KisanMitra is designed to retrieve weather information from real weather services, with **India Meteorological Department (IMD)** as the primary official source where configured.

Weather information can include:

* Temperature
* Humidity
* Wind
* Rainfall
* Forecast
* Rain probability
* Weather warnings
* District rainfall
* Agricultural weather information
* Observation/forecast time
* Data source

The agent uses the farmer's actual location information whenever available.

If live weather information cannot be retrieved, KisanMitra reports that the data is unavailable instead of generating a fake value.

---

# 📈 Real Agricultural Market Prices

KisanMitra can retrieve agricultural market information from real sources such as:

* AGMARKNET
* Government Open Data
* e-NAM
* Official agricultural market sources where available

Market information can include:

* Commodity
* Variety
* Grade
* Market
* State
* District
* Date
* Minimum price
* Maximum price
* Modal price
* Arrival quantity
* Unit

For example:

```text
Farmer:
"I have 500 kg tomatoes ready to sell."

        ↓

KisanMitra

        ↓

Identify crop
Identify quantity
Identify location
Retrieve current market information
Compare available prices
Calculate estimated gross value
Explain market factors
```

Any calculated value is presented as an **estimate**, because actual realization can depend on quality, grade, transport, commission, fees, and negotiated price.

---

# 🌱 Crop Intelligence

KisanMitra supports agricultural knowledge across a wide range of crops.

Examples include:

### Cereals

* Rice
* Wheat
* Maize
* Ragi
* Jowar
* Bajra

### Pulses

* Red Gram
* Green Gram
* Black Gram
* Chickpea

### Oilseeds

* Groundnut
* Sunflower
* Soybean
* Sesame
* Mustard

### Vegetables

* Tomato
* Potato
* Onion
* Garlic
* Carrot
* Cabbage
* Cauliflower
* Capsicum
* Chilli
* Brinjal
* Okra
* Beans
* Cucumber
* Pumpkin
* Bottle Gourd
* Bitter Gourd
* Ridge Gourd

### Fruits

* Banana
* Mango
* Papaya
* Pomegranate
* Grapes
* Guava
* Sapota
* Orange
* Watermelon

### Commercial and Plantation Crops

* Sugarcane
* Cotton
* Coffee
* Tea
* Coconut
* Arecanut
* Black Pepper
* Turmeric
* Ginger
* Cardamom
* Coriander
* Cumin

Crop knowledge can include:

* Crop stages
* Soil requirements
* Irrigation
* Water requirements
* Common pests
* Diseases
* Nutrient deficiencies
* Environmental stress
* Harvesting
* Storage

---

# 📷 AI Crop Image Analysis

Farmers can upload crop images for AI-assisted analysis.

Workflow:

```text
📷 Crop Image
      ↓
Gemini Vision
      ↓
Observed Symptoms
      ↓
Crop Knowledge
      ↓
Weather Context
      ↓
Agent Reasoning
      ↓
Recommended Actions
```

KisanMitra distinguishes between:

### AI Observations

What the image visibly shows.

### Possible Explanations

Potential causes based on the available evidence.

The system does not present AI image analysis as a laboratory-confirmed diagnosis.

---

# 🌾 Farmer Profile

Each farmer has an individual profile containing information such as:

* Name
* Mobile
* Email
* State
* District
* Taluk
* Village
* Farm size
* Crops
* Crop stage
* Irrigation
* Soil type
* Water source
* Previous problems
* Previous decisions

Farmer information is isolated by authenticated user.

---

# 🗺️ My Land

Farmers can maintain multiple land parcels.

Each parcel can contain:

* State
* District
* Taluk
* Hobli
* Village
* Survey number
* Hissa number
* RTC/Pahani reference
* Land area
* Land type
* Ownership type
* Owner/co-owner
* Soil type
* Irrigation
* Water source
* Current crop
* Previous crop
* Season
* Lease information
* Notes

Farm-entered information is clearly identified as:

```text
[USER ENTERED]
```

---

# 🏛️ Karnataka Land Records

KisanMitra provides access to official Karnataka land-record services.

### Karnataka Land Records

https://landrecords.karnataka.gov.in/service2/

### Karnataka Land Resources Information System

https://sujala3lri.karnataka.gov.in/

KisanMitra does not bypass:

* CAPTCHA
* Authentication
* Security controls

The intended workflow is:

```text
Farmer
  ↓
Open Official Portal
  ↓
Verify Own Land Record
  ↓
Enter Verified Information
  ↓
Save in My Land
```

---

# 🏛️ Government Schemes

KisanMitra helps farmers discover relevant government resources and schemes.

Information can include:

* Scheme name
* Government department
* Purpose
* Eligibility
* Required documents
* Application method
* Official source
* Verification date

Potential resources include:

* PM-KISAN
* Crop insurance services
* Karnataka agriculture services
* Raitamitra
* Seva Sindhu
* e-NAM
* Irrigation schemes
* Equipment subsidies

Government information is presented with appropriate official sources and should be re-verified when eligibility or application rules change.

---

# 📋 Action Planning

KisanMitra converts analysis into practical actions.

Example:

```text
HIGH PRIORITY
Inspect the affected tomato plants today.

Reason:
Yellowing symptoms combined with recent rainfall
may require further field observation.

Timeframe:
Today

Status:
Pending
```

Action plans are stored in the database and can be tracked later.

---

# 🔔 Follow-Ups

KisanMitra can schedule meaningful follow-up tasks.

Example:

```text
Task:
Inspect tomato field after rainfall.

Scheduled:
Tomorrow morning
```

Follow-ups are stored in SQLite and displayed on the farmer dashboard.

---

# 🌐 Multilingual Support

KisanMitra is designed to support:

* 🇬🇧 English
* 🇮🇳 Kannada
* 🇮🇳 Hindi

Example:

```text
ನನ್ನ ಟೊಮೇಟೊ ಬೆಳೆಯ ಎಲೆಗಳು ಹಳದಿಯಾಗುತ್ತಿವೆ.
```

The agent can respond in Kannada when Kannada is detected.

The same workflow applies to Hindi and English.

---

# 🎤 Voice Interaction

KisanMitra can optionally use browser speech recognition.

```text
🎤 Farmer speaks
        ↓
Speech-to-Text
        ↓
KisanMitra Agent
        ↓
Real Tools
        ↓
AI Analysis
        ↓
Farmer Response
```

The normal text interface remains available.

---

# 🔍 Agent Activity

KisanMitra exposes operational agent activity without exposing private chain-of-thought.

Example:

```text
✓ Request understood
✓ Farmer profile loaded
✓ Location identified
⟳ Calling weather service
✓ Weather data received
⟳ Retrieving crop knowledge
✓ Crop knowledge received
⟳ Gemini analyzing results
✓ Action plan created
✓ Follow-up scheduled
```

The displayed activity represents actual backend operations.

---

# 🧠 Technology Stack

| Technology       | Purpose                    |
| ---------------- | -------------------------- |
| Python           | Backend                    |
| FastAPI          | Web API                    |
| Google Gemini    | Agent reasoning and vision |
| Google GenAI SDK | Gemini integration         |
| SQLite           | Persistent database        |
| Pydantic         | Data validation            |
| HTTPX            | External API requests      |
| JavaScript       | Frontend interactions      |
| HTML/CSS         | User interface             |

---

# 📁 Project Structure

```text
KisanMitra/
│
├── kisanmitra.py
├── requirements.txt
├── .env
│
└── kisanmitra.db
```

The SQLite database is generated at runtime.

---

# ⚙️ Installation

## 1. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd KisanMitra
```

## 2. Create Virtual Environment

### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### Linux/macOS

```bash
python3 -m venv venv
source venv/bin/activate
```

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

# 🔐 Environment Configuration

Create a `.env` file:

```env
GEMINI_API_KEY=YOUR_REAL_GEMINI_API_KEY
GEMINI_MODEL=gemini-2.5-flash

IMD_API_KEY=YOUR_REAL_IMD_API_KEY

SECRET_KEY=YOUR_SECURE_SECRET_KEY

DATABASE_URL=sqlite:///./kisanmitra.db
```

Never commit `.env` to GitHub.

Add:

```text
.env
venv/
__pycache__/
*.pyc
kisanmitra.db
```

to `.gitignore`.

---

# ▶️ Running the Application

Run:

```bash
python kisanmitra.py
```

The application starts at:

```text
http://127.0.0.1:8000
```

Open the URL in your browser.

---

# 🔌 API Endpoints

## Authentication

```text
GET  /login
POST /api/login
POST /api/logout
POST /api/register
GET  /api/me
```

## Agent

```text
POST /api/chat
POST /api/agent/run
POST /api/analyze-image
GET  /api/agent/status
```

## Farmer

```text
GET /api/farmer/{id}
```

## Land

```text
GET    /api/land
POST   /api/land
PUT    /api/land/{id}
DELETE /api/land/{id}
```

## Agriculture

```text
GET /api/weather
GET /api/markets
GET /api/crops
GET /api/schemes
```

## Action Plans

```text
POST /api/action-plan
GET  /api/action-plans
```

## Follow-Ups

```text
POST /api/followup
GET  /api/followups
```

## Health

```text
GET /api/health
```

---

# 🔐 Security & Privacy

KisanMitra is designed with farmer data protection in mind.

Security measures include:

* Password hashing
* Secure sessions
* Authentication
* Authorization
* User-specific database queries
* Input validation
* Parameterized SQL queries
* Image validation
* File size limits
* API key protection
* No password hashes returned through APIs
* No unnecessary personal information collection

Sensitive API credentials are stored only on the backend.

---

# 🤝 Responsible AI

KisanMitra follows several responsible AI principles:

### No fabricated data

The system does not generate fake:

* Weather
* Market prices
* Land records
* Government information
* Farmer information
* Locations

### Uncertainty

The AI communicates uncertainty when evidence is insufficient.

### Crop health

The system provides possible explanations rather than claiming guaranteed diagnosis.

### Safety

High-risk agricultural situations should be referred to qualified agricultural experts.

### Privacy

Farmer information must remain isolated to the authenticated farmer.

---

# 🚫 Data Integrity Principle

The core principle of KisanMitra is:

```text
REAL DATA
    ↓
REAL TOOL
    ↓
REAL API
    ↓
REAL RESULT
    ↓
GEMINI REASONING
    ↓
REAL ACTION
```

If information cannot be retrieved:

```text
DATA UNAVAILABLE
```

The system must never replace missing information with fabricated values.

---

# 🎯 Project Goal

KisanMitra aims to transform a farmer's question from:

> "What should I do?"

into an intelligent workflow:

```text
Farmer Situation
       ↓
Context
       ↓
Real Data
       ↓
Agent Reasoning
       ↓
Action Plan
       ↓
Follow-Up
```

The goal is to provide farmers with a practical AI assistant that can combine agricultural knowledge with real-world information and help them make informed farming decisions.

---

# 🏆 Hackathon Highlights

KisanMitra demonstrates:

* 🤖 Agentic AI
* 🔧 Dynamic tool calling
* 🧠 Gemini reasoning
* 🌦️ Real weather integration
* 📈 Real agricultural market data
* 🌱 Crop intelligence
* 📷 AI image analysis
* 🗺️ Location-aware farming
* 🏛️ Government service discovery
* 📋 Automated action planning
* 🔔 Follow-up scheduling
* 🌐 Multilingual interaction
* 🎤 Voice interaction
* 🔐 Secure authentication
* 💾 Persistent farmer data

---

# 📌 Future Improvements

Potential extensions include:

* Satellite-based crop monitoring
* IoT soil sensors
* Smart irrigation recommendations
* Pest outbreak alerts
* Crop price trend analysis
* Voice-first farmer assistant
* Regional agricultural advisories
* Expert consultation
* WhatsApp integration
* SMS alerts
* More Indian language support

---

# 🌾 KisanMitra

### *Your Intelligent Farming Partner*

```text
Understand → Observe → Reason → Act → Follow Up
```

**Built for Indian Agriculture with Agentic AI.**
