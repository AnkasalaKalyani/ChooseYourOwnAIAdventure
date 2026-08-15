# 🧙‍♀️ AI Choose Your Own Adventure

An interactive **AI-powered story generator** that creates dynamic, 
personalized choose-your-own-adventure stories based on a theme provided by the user.

The application uses **OpenAI's GPT model** to generate stories, characters, story paths, and choices. 
Users can make decisions throughout the story, creating their own unique adventure.

## 🚀 Live Demo

**Deployed using [WSO2 Choreo](https://wso2.com/choreo/)**

🔗 **Live Application:**
`https://8334b335-3e04-4d55-9e78-e5b322dd04a1.e1-us-east-azure.choreoapps.dev`
---

## ✨ Features

* 🤖 AI-generated interactive stories
* 🎭 Multiple story themes
* 🌳 Dynamic branching story paths
* 🎯 User-driven story choices
* 🏆 Winning and ending conditions
* 💾 Story and story-node persistence
* 🔄 Backend API for story generation and navigation
* 🌐 Interactive frontend interface
* ☁️ Cloud deployment using WSO2 Choreo
* 🔐 Secure AI API configuration through Choreo connections

---

## 🏗️ Project Architecture

The project consists of two main components:

```text
AI Choose Your Own Adventure
│
├── frontend/
│   └── React-based user interface
│
├── backend/
│   ├── FastAPI application
│   ├── Story generation logic
│   ├── OpenAI / LangChain integration
│   ├── Database models
│   └── API endpoints
│
└── .choreo/
    └── Choreo deployment configuration
```

### 🔹 Frontend

The frontend provides the user interface where users can:

1. Enter a story theme.
2. Start a new adventure.
3. Read the generated story.
4. Select from available choices.
5. Continue through different story paths.
6. Reach different endings.

### 🔹 Backend

The backend is responsible for:

* Generating stories using an LLM.
* Processing story nodes.
* Managing story branches.
* Storing stories and story nodes.
* Providing APIs to the frontend.
* Communicating with the AI service.

The backend is built using **Python and FastAPI**.

---

## 🤖 AI Integration

The application uses:

* **OpenAI GPT**
* **LangChain**
* **LangChain OpenAI**
* **Pydantic**
* **FastAPI**

The story generator sends the selected theme to the AI model and receives a structured story containing:

* Story title
* Story content
* Story options
* Next story nodes
* Ending status
* Winning-ending status

The structured response is then stored and used to create the interactive adventure.

---

## 🔐 OpenAI Connection

Instead of exposing an OpenAI API key directly in the source code, the deployed application uses a **Choreo connection** to securely provide the required configuration to the backend.

The backend retrieves the required Choreo connection values through environment variables.

Example:

```python
choreo_api_key = os.getenv("CHOREO_CONNECTION_OPENAI_APIKEY")
service_url = os.getenv("CHOREO_CONNECTION_OPENAI_SERVICEURL")

if choreo_api_key and service_url:
    return ChatOpenAI(
        model="gpt-4o-mini",
        api_key=choreo_api_key,
        base_url=service_url
    )
```


---

## ☁️ Deployment with WSO2 Choreo

This project was deployed using **WSO2 Choreo**, a cloud platform for building, deploying, and managing cloud-native applications.

The deployment includes:

* Frontend deployment
* Backend deployment
* Backend REST API endpoint
* OpenAI service connection
* Environment configuration
* GitHub-based source deployment

The project is connected to GitHub, allowing the deployed application to be built and deployed from the repository.

Choreo supports building and deploying services from source repositories and provides environments for application deployment.
[Choreo Documentation](https://wso2.github.io/docs-choreo-dev/quick-start-guides/deploy-your-first-service/)

---

## 🛠️ Technologies Used

| Technology   | Purpose                   |
| ------------ | ------------------------- |
| Python       | Backend development       |
| FastAPI      | REST API                  |
| SQLAlchemy   | Database interaction      |
| SQLite       | Database                  |
| LangChain    | LLM application framework |
| OpenAI GPT   | AI story generation       |
| Pydantic     | Data validation           |
| React        | Frontend                  |
| JavaScript   | Frontend development      |
| Git & GitHub | Version control           |
| WSO2 Choreo  | Cloud deployment          |

---

## 📁 Project Structure

```text
Choose-Your-Own-Adventure-AI/
│
├── backend/
│   ├── core/
│   │   ├── prompts.py
│   │   ├── models.py
│   │   └── story_generator.py
│   │
│   ├── models/
│   │   └── story.py
│   │
│   ├── main.py
│   ├── requirements.txt
│   └── .choreo/
│
├── frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── ...
│
└── README.md
```

---

## ⚙️ Running Locally

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd Choose-Your-Own-Adventure-AI
```

### 2. Set up the backend

```bash
cd backend
```

Create and activate a virtual environment:

```bash
python -m venv venv
```

Activate it:

**Windows:**

```bash
venv\Scripts\activate
```

**macOS/Linux:**

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

### 3. Configure environment variables

Create a `.env` file in the backend directory.

Example:

```env
DATABASE_URL=sqlite:///./database.db
API_PREFIX=/api
DEBUG=True
ALLOWED_ORIGINS=http://localhost:5173
OPENAI_API_KEY=your_api_key_here
```

> Never commit your `.env` file or API keys to GitHub.

### 4. Start the backend

```bash
python main.py
```

The backend will run on:

```text
http://localhost:8000
```

### 5. Start the frontend

Open another terminal:

```bash
cd frontend
npm install
npm run dev
```

The frontend will normally be available at:

```text
http://localhost:5173
```

---

## 🎮 How It Works

```text
User
  │
  ▼
Select Story Theme
  │
  ▼
Frontend
  │
  ▼
FastAPI Backend
  │
  ▼
Story Generator
  │
  ▼
LangChain + OpenAI GPT
  │
  ▼
Structured Story Response
  │
  ▼
Database
  │
  ▼
Story Nodes + Choices
  │
  ▼
User Selects a Choice
  │
  ▼
Next Story Node
  │
  ▼
Continue Adventure
```

---

## 📌 Learning & Development

This project was developed as a practical project to explore:

* Generative AI
* Large Language Models
* LangChain
* Prompt engineering
* Structured LLM outputs
* FastAPI backend development
* React frontend development
* REST API integration
* Database integration
* Cloud deployment
* Choreo connections
* Secure API configuration

---
## 👩‍💻 Project Author
Kalyani Ankasala