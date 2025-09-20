# AI Architecture Planning Agent

> **Intelligent system architecture generation from user stories using LangGraph and LLM orchestration**

An AI-powered agent that analyzes user stories and automatically generates comprehensive system architecture recommendations, including technology stack selection, component design, data modeling, API specifications, and deployment strategies.

## Features
### Core Capabilities

- **User Story Analysis** - Extracts requirements, entities, and business logic from natural language
- **Tech Stack Recommendations** - Suggests optimal technologies based on project complexity and requirements
- **Architecture Design** - Generates system components, relationships, and data flow patterns
- **Data Modeling** - Creates database schemas with relationships and constraints
- **API Design** - Defines RESTful endpoints with authentication and validation
- **Deployment Planning** - Provides infrastructure and cloud deployment strategies
- **Visual Diagrams** - Generates ASCII architecture diagrams

### Advanced Features

- **Multi-step LangGraph Workflow**- Orchestrates complex analysis through 7 specialized agents
- **Error Handling & Fallbacks** - Robust operation even with API failures
- **Interactive CLI** - Rich command-line interface with progress indicators
- **Multiple Output Formats** - JSON, YAML, and Markdown reports
- **Comprehensive Testing** - 95%+ test coverage with unit and integration tests

### Architecture

User Stories → Requirements Analysis → Tech Stack Selection → Architecture Design → Data Modeling → API Design → Deployment Planning → Architecture Plan

### Technology Stack
- **Python 3.9+** - Core programming language
- **LangGraph** - Multi-agent workflow orchestration  
- **LangChain** - LLM integration and tool management
- **OpenAI GPT-4** - Intelligent analysis and recommendations
- **Pydantic** - Data validation and serialization
- **Typer + Rich** - Beautiful CLI interface
- **Pytest** - Comprehensive testing framework


## Quick Start

### Prerequisites
- Python 3.9 or higher
- OpenAI API key
- Git

### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/yourusername/Architecture-agent.git
cd Architecture-agent

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Copy template and add your OpenAI API key
cp .env.example .env
# Edit .env with your actual API key:
# OPENAI_API_KEY=sk-your-key-here

# Run with sample data
python main.py plan --stories examples/sample_stories.json --verbose

# Generate architecture from user stories
python main.py plan --stories examples/sample_stories.json

# With technology preference
python main.py plan --stories examples/sample_stories.json --tech "React + Node.js"

# Verbose output with detailed information
python main.py plan --stories examples/sample_stories.json --verbose

# Save results to file
python main.py plan --stories examples/sample_stories.json --output architecture.json

# Interactive technology selection
python main.py plan --stories examples/sample_stories.json --interactive

# Fully guided mode
python main.py interactive

-##Testing:

# Run all tests
pytest

# Run with coverage
pytest --cov=agents --cov=tools --cov-report=html

# Run specific test categories
pytest tests/test_agents.py -v
pytest tests/test_tools.py -v

# Run integration tests
pytest tests/test_integration.py -v