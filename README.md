# VoyageVista AI

VoyageVista AI is a multi-agent travel planning web app built with FastAPI, LangGraph, Groq, PostgreSQL, Tavily, and AviationStack. It takes a natural-language travel request and turns it into a structured trip plan with flight information, hotel suggestions, a day-by-day itinerary, and budget guidance, with all costs presented in Rs.

## Highlights

- Multi-agent orchestration for flight search, hotel search, itinerary generation, and final response formatting.
- FastAPI backend with a clean Jinja2-rendered frontend.
- Conversational travel planning through a simple web interface.
- Budget-aware output designed for practical trip planning.
- PDF download support for saving the generated plan.
- Persistent thread handling for repeated conversations.

## Tech Stack

- Python 3.11+
- FastAPI
- LangGraph
- LangChain
- Groq LLM
- PostgreSQL with `langgraph-checkpoint-postgres`
- Tavily search
- AviationStack API
- Jinja2 templates
- Vanilla JavaScript, HTML, and CSS

## Project Structure

```text
.
├── app.py
├── backend.py
├── requirements.txt
├── templates/
│   └── index.html
├── static/
│   ├── script.js
│   └── style.css
└── tools/
	├── flight_tool.py
	└── tavily_tool.py
```

## Features

- Natural-language travel requests
- Flight search and route-based travel insights
- Hotel discovery using web search
- Trip itinerary generation
- Budget presentation in Rs
- Copy and PDF export for the final response
- Responsive UI with a professional landing page

## Getting Started

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd Travel_planner_Multi_Agent
```

### 2. Create and activate a virtual environment

On Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Create a `.env` file

Add your API keys and database URL in a `.env` file at the project root:

```dotenv
GROQ_API_KEY=your_groq_key
AVIATIONSTACK_API_KEY=your_aviationstack_key
TAVILY_API_KEY=your_tavily_key
DATABASE_URL=your_postgres_connection_string
DEFAULT_ORIGIN_IATA=CMB
LANGSMITH_TRACING=true
LANGSMITH_ENDPOINT=https://api.smith.langchain.com
LANGSMITH_API_KEY=your_langsmith_key
LANGSMITH_PROJECT=VoyageVista
```

### 5. Run the app

```bash
python app.py
```

Open the app in your browser at `http://127.0.0.1:8000`.

## Example Prompt

Try a request like this:

```text
Plan a 7 day Japan trip from Bangladesh including flights, hotels, sightseeing, and a budget under Rs 2,00,000.
```

## API Endpoints

- `GET /` - Web UI
- `POST /api/travel` - Generate a travel plan
- `GET /health` - Health check

## Example Response Flow

1. User enters a trip request.
2. The flight agent gathers route and flight-related information.
3. The hotel agent searches for suitable hotel options.
4. The itinerary agent creates a day-by-day plan.
5. The final agent formats a clear travel recommendation.

## Why This Project Stands Out

VoyageVista AI demonstrates practical AI application design, multi-agent orchestration, API integration, web UI development, and structured response generation. It is a good portfolio project because it shows both backend system design and frontend presentation skills.

## Future Improvements

- Live currency conversion for deterministic Rs totals
- Better hotel filtering by rating, budget, and location
- Map integration for destination planning
- User authentication and saved trips
- Deployment-ready configuration for production hosting
