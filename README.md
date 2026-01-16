# 🤖 TrackFlow : AI Personal Assistant with Vision & Analytics

An **AI-powered personal analytics platform** that helps users track daily life data (health, nutrition, water, habits, finance, etc.), analyze patterns, and generate intelligent insights using **LLMs, vision models, and autonomous agents**.

This system combines **Groq-powered LLMs**, **CrewAI agents**, **LangChain tools**, and a **MySQL-backed data layer**, exposed through a **Flask web application** with dashboards and visualizations.

---

## ✨ Key Features

* 🧠 **Autonomous AI Agent** for reasoning, tracking, and analysis
* 🖼️ **Vision Support** — upload images (food, activities, objects) and extract actionable data
* 🗄️ **Life Tracking Database** — nutrition, water, habits, health, or any custom table
* 📊 **AI-Generated Dashboards** — charts, insights, and improvement strategies
* 🔄 **Stateful Memory System** — conversation context, cached schemas, and image memory
* 🛠️ **Tool-Augmented Reasoning** — safe SQL generation, schema introspection, correlations
* 🌐 **REST API + Web UI** built with Flask

---

## 🧠 AI & Agent Stack

### Large Language Models (via Groq)

* **llama-3.3-70b-versatile**

  * Core reasoning
  * CrewAI agent execution
  * Dashboard insights & recommendations
* **llama-4-scout-17b-16e-instruct**

  * Vision model for image understanding

### Agent Framework

* **CrewAI** — task orchestration and autonomous execution
* **LangChain** — LLM abstraction, SQL tools, and tool calling

---

## 🖼️ Vision Pipeline

1. User uploads an image (e.g., food or activity)
2. Groq Vision model generates a detailed description
3. The agent combines:

   * Image description
   * User intent
   * Conversation context
4. Relevant data is logged, analyzed, or visualized

Example:

> Upload a pizza image → Ask to track nutrition → AI estimates macros → Stores in MySQL

---

## 🗄️ Database & Data Layer

* **MySQL** — structured storage for all tracking data
* **LangChain SQL Tools**

  * List tables
  * Inspect schemas
  * Validate queries
  * Execute safe SQL
* **Direct MySQL Connector** for analytics dashboards

Supports:

* Automatic table creation
* Date-based tracking
* Cross-table correlation analysis

---

## 📊 Analytics & Visualization

* **Matplotlib** (server-side rendering)
* Supported chart types:

  * Line
  * Bar
  * Pie
  * Area
* Charts returned as **base64 images** via API
* AI decides:

  * What to visualize
  * Which SQL queries to run
  * What insights to surface

---

## 🧠 Memory & State Management

Custom memory system includes:

* Conversation history (last N turns)
* Cached table names & schemas
* Last image description
* Pending intents (e.g., visualization choices)
* API call tracking

This enables **context-aware, multi-turn interactions**.

---

## 🌐 Backend Architecture

* **Python**

* **Flask**

  * `/chat` — main conversational endpoint (text + image)
  * `/dashboard` — AI-powered analytics dashboards
  * `/stats` — system statistics
  * `/history` — conversation history
  * `/clear` — reset conversation state

* **dotenv** for configuration

* **Session-based state handling**

---

## 🔐 Configuration

### Environment Variables

```env
GROQ_API_KEY=your_groq_api_key
```

### Database Configuration (example)

```python
MYSQL_HOST = "localhost"
MYSQL_USER = "root"
MYSQL_PASSWORD = "password"
MYSQL_DB = "ai_agent"
MYSQL_PORT = 3306
```

---

## 🚀 Getting Started

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/ai-personal-assistant.git
cd ai-personal-assistant
```

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Set Up Environment Variables

Create a `.env` file:

```env
GROQ_API_KEY=your_groq_api_key
```

### 4️⃣ Start MySQL

Ensure MySQL is running and the database exists.

### 5️⃣ Run the Server

```bash
python app.py
```

Visit:

```
http://localhost:5000
```

---

## 🧪 Example Use Cases

* 📸 Upload food images → Track nutrition automatically
* 💧 Log and visualize daily water intake
* 🏃 Track workouts and correlate with sleep or diet
* 📊 Generate AI dashboards with actionable insights
* 🧠 Ask natural language questions about your data

---

## 🏗️ Architecture Style

* Agent-first design
* Tool-augmented LLM reasoning
* Multimodal (text + image) pipeline
* Stateful conversational analytics
* AI-driven data visualization

---

## 🔮 Future Improvements

* Authentication & multi-user support
* Frontend framework (React / Next.js)
* Time-series forecasting
* Notification & reminder system
* Exportable reports (PDF/CSV)

---

## 📄 License

MIT License

---

## ⭐ One-Line Summary

> An AI-powered personal analytics platform using Groq LLMs, CrewAI agents, vision models, and MySQL to track life data, analyze patterns, and generate intelligent dashboards.
