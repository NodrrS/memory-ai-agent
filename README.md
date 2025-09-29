# 🧠 Memory AI Agent

A Streamlit-based AI assistant with persistent memory capabilities using Pinecone vector database and OpenAI. This agent can remember your preferences, past conversations, and personal information to provide more personalized and contextual responses over time.

## ✨ Features

- **Persistent Memory**: Uses Pinecone vector database to store and retrieve memories
- **Semantic Search**: Finds relevant memories using OpenAI embeddings and vector similarity
- **Interactive Chat Interface**: Clean Streamlit web interface for conversations
- **Context-Aware Responses**: Incorporates relevant memories into AI responses
- **Memory Management**: Automatically saves important user preferences and information

## 🏗️ Architecture

- **Frontend**: Streamlit web application (`app.py`)
- **AI Agent**: OpenAI GPT-4o-mini with function calling (`agent/agent.py`)
- **Memory System**: Pinecone vector database for storing embeddings (`agent/tools.py`)
- **Prompt Engineering**: Dynamic system prompts with memory integration (`agent/prompts.py`)

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- OpenAI API key
- Pinecone API key and configured index

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/memory-ai-agent.git
cd memory-ai-agent
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Set up environment variables:
Create a `.env` file in the root directory with:
```env
OPENAI_API_KEY=your_openai_api_key
PINECONE_API_KEY=your_pinecone_api_key
PINECONE_INDEX_NAME=your_index_name
PINECONE_NAMESPACE=your_namespace
```

4. Run the application:
```bash
streamlit run app.py
```

## 🔧 Configuration

### Pinecone Setup

1. Create a Pinecone account at [pinecone.io](https://www.pinecone.io/)
2. Create a new index with:
   - Dimensions: 1536 (for OpenAI text-embedding-ada-002)
   - Metric: cosine
   - Cloud: AWS or GCP (your preference)
3. Note your API key, index name, and namespace

### Environment Variables

| Variable | Description |
|----------|-------------|
| `OPENAI_API_KEY` | Your OpenAI API key |
| `PINECONE_API_KEY` | Your Pinecone API key |
| `PINECONE_INDEX_NAME` | Name of your Pinecone index |
| `PINECONE_NAMESPACE` | Namespace within your index |

## 📁 Project Structure

```
memory-ai-agent/
├── agent/
│   ├── agent.py          # Core AI agent with function calling
│   ├── prompts.py        # System prompt generation with memories
│   └── tools.py          # Memory storage and retrieval functions
├── app.py                # Streamlit web application
├── requirements.txt      # Python dependencies
├── Developer_Guide.ipynb # Tutorial on embeddings and vector databases
└── README.md            # This file
```

## 🛠️ How It Works

1. **User Interaction**: User sends a message through the Streamlit interface
2. **Memory Retrieval**: System queries Pinecone for relevant memories based on semantic similarity
3. **Prompt Enhancement**: Retrieved memories are injected into the system prompt
4. **AI Response**: OpenAI GPT-4o-mini generates a response with memory context
5. **Memory Storage**: Important information from the conversation is extracted and stored as new memories

### Memory System

The agent uses a vector-based memory system:
- **Storage**: Converts text to embeddings using OpenAI's `text-embedding-ada-002`
- **Retrieval**: Uses semantic similarity search to find relevant memories
- **Metadata**: Each memory includes timestamp, user ID, and contextual information
- **Filtering**: Memories are filtered by user ID and type for privacy and relevance

## 🎯 Usage Examples

- **Personal Preferences**: "I prefer coffee over tea" → Agent remembers for future recommendations
- **Important Information**: "My birthday is March 15th" → Agent can reference this later
- **Context Continuity**: Previous conversation topics influence current responses
- **Personalized Recommendations**: Agent suggests activities based on remembered preferences

## 🔍 Developer Guide

Check out `Developer_Guide.ipynb` for a comprehensive tutorial on:
- Understanding embeddings and vector databases
- How Pinecone stores and queries vectors
- Step-by-step implementation examples
- Memory storage and retrieval workflows

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [OpenAI](https://openai.com) for the powerful language models and embeddings
- [Pinecone](https://www.pinecone.io) for the vector database service
- [Streamlit](https://streamlit.io) for the easy-to-use web framework

## 🐛 Issues & Support

If you encounter any issues or have questions, please [open an issue](https://github.com/yourusername/memory-ai-agent/issues) on GitHub.
