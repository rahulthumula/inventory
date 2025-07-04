# Restaurant Inventory Assistant

A smart, AI-powered assistant for restaurant inventory management that leverages RAG (Retrieval-Augmented Generation), fine-tuned models, and vector search to provide personalized inventory insights and recommendations.

## Features

- **AI-Powered Inventory Insights**: Get intelligent answers to queries about your restaurant inventory data
- **Fine-Tuned LLM**: Uses a custom fine-tuned GPT-4o model trained on restaurant inventory management techniques
- **RAG Architecture**: Combines vector search with generative AI for accurate, context-aware responses
- **Web Interface**: Clean, modern UI with both text and voice interaction capabilities
- **Multi-User Support**: Maintains separate inventory indices for different users

## Architecture

The system consists of the following components:

- **FastAPI Backend**: RESTful API service for all inventory queries
- **RAG Implementation**: Combines vector search and LLM generation
- **Azure Cosmos DB**: Store for restaurant inventory data
- **Azure Cognitive Search**: Vector database for semantic search
- **Fine-Tuned OpenAI Model**: Restaurant management specific model

## Technical Stack

- **Backend**: Python, FastAPI, AsyncIO
- **Database**: Azure Cosmos DB
- **Vector Store**: Azure Cognitive Search
- **AI/ML**: OpenAI API, embedding models
- **Frontend**: HTML, CSS, JavaScript

## Installation

### Prerequisites

- Python 3.9+
- Azure Cosmos DB account
- Azure Cognitive Search service
- OpenAI API key with access to embedding and completion models

### Environment Setup

1. Clone the repository:
```bash
git clone https://github.com/your-username/restaurant-inventory-assistant.git
cd restaurant-inventory-assistant
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Create a `.env` file in the project root with the following variables:
```
# Azure Cosmos DB configuration
COSMOS_ENDPOINT=your_cosmos_endpoint
COSMOS_KEY=your_cosmos_key
COSMOS_DATABASE=your_database_name
COSMOS_CONTAINER=your_container_name

# OpenAI configuration
OPENAI_API_KEY=your_openai_api_key
OPENAI_EMBEDDING_MODEL=text-embedding-3-small

# Azure Cognitive Search configuration
SEARCH_SERVICE_ENDPOINT=your_search_endpoint
SEARCH_SERVICE_KEY=your_search_key
SEARCH_INDEX_NAME=inventory-index
```

## Usage

### Running the Backend

Start the FastAPI server:

```bash
uvicorn main:app --reload
```

The server will be available at `http://localhost:8000`.

### API Endpoints

- `POST /initialize/{user_id}`: Initialize inventory data for a user
- `POST /query`: Process inventory queries
- `POST /refresh/{user_id}`: Refresh the user's inventory data
- `GET /status/{user_id}`: Check index status for a user
- `GET /health`: API health check

### Web Interface

Open `index.html` in a web browser to access the user interface. The interface allows for:

- Text-based queries about inventory
- Voice input for hands-free operation
- Viewing and managing conversation history
- Settings customization

## Fine-Tuning (Optional)

The system includes scripts for fine-tuning a custom model with OpenAI:

1. Prepare training data:
```bash
python converttojsonl.py
```

2. Run the fine-tuning job:
```bash
python finetunedmodel.py
```

3. Check the job status:
```bash
python jobstatus.py
```

## Testing

Run the embedding test to verify your setup:

```bash
python test.py
```

## Project Structure

- `main.py`: FastAPI application and endpoints
- `rag.py`: RAG implementation
- `database.py`: Cosmos DB connections
- `embeddings.py`: Embedding generation
- `search.py`: Vector search implementation
- `config.py`: Configuration and environment variable handling
- `models.py`: Pydantic models for data validation
- `converttojsonl.py`: Convert restaurant management Q&A to JSONL for fine-tuning
- `finetunedmodel.py`: Create fine-tuning job
- `jobstatus.py`: Check fine-tuning job status
- `index.html`: Web interface

## Example Queries

You can ask questions like:

- "What dairy items are most expensive?"
- "Which items should I buy in bulk?"
- "Show me all produce items with low inventory"
- "What's our current inventory value?"
- "Which suppliers do we order meat products from?"
- "How can I optimize my inventory management system?"

## Extending the System

### Adding Custom Questions

To extend the system with custom inventory management questions:

1. Add your Q&A pairs to `Inventory Management Questions.txt`
2. Run `python converttojsonl.py` to convert to JSONL
3. Fine-tune a new model using `python finetunedmodel.py`
4. Update the model name in `config.py`

### Customizing the Frontend

The `index.html` file contains the entire frontend. You can modify:

- UI layout and styling
- Voice interaction settings
- Display preferences
- Color scheme and branding

## License

[MIT License](LICENSE)

## Acknowledgments

- OpenAI for the GPT-4o model
- Azure Cognitive Services for vector search capabilities
- FastAPI for the backend framework
#   i n v o i c e  
 #   i n v o i c e  
 #   i n v e n t o r y _ _ a s s i s t a n t  
 #   i n v e n t o r y  
 #   i n v e n t o r y  
 #   i n v e n t o r y  
 