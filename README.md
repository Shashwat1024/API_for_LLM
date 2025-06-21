# 🔐 FastAPI AI Text Generator with API Key and Credit System

This project is a lightweight FastAPI-based REST API that uses the Ollama API (Mistral model) to generate AI-based responses to user prompts. It implements a basic API key verification system with credit limits for added control.

## 🚀 Features

- **API Key Authentication** via headers
- **Credit Limiting**: Each key is allocated 5 credits by default
- **Ollama Integration** using the `mistral` model
- **Simple REST API** using FastAPI
- **Testing Script** to quickly verify the API

## 🧾 Requirements

- Python 3.8+
- Ollama with `mistral` model installed locally
- `.env` file with your `API_KEY`

### Install Dependencies

```bash
pip install -r requirements.txt
```

## 🧪 Usage

### 1. Set up `.env` file

Create a `.env` file in the root directory:

```env
API_KEY=your_api_key_here
```

### 2. Start the Server

```bash
uvicorn main:app --reload
```

### 3. Make a Request

You can use the `test-api.py` script to make a request:

```bash
python test-api.py
```

Or use `curl`:

```bash
curl -X POST "http://127.0.0.1:8000/generate?prompt=Tell me about AI"   -H "x-api-key: your_api_key_here"
```

## 🔐 Authentication and Credit System

- Each request requires the `x-api-key` header.
- Each API key starts with 5 credits.
- Each request deducts 1 credit.
- Once the credits reach 0, access is denied with a `401 Unauthorized`.

## 📁 Project Structure

```
.
├── main.py           # FastAPI app with endpoint and credit control
├── test-api.py       # Test script to send a request
├── requirements.txt  # Dependencies
└── .env              # Environment variables (not committed)
```

## 🧠 Powered By

- [FastAPI](https://fastapi.tiangolo.com/)
- [Ollama](https://ollama.com/)
- [Mistral Model](https://ollama.com/library/mistral)
- [Dotenv](https://pypi.org/project/python-dotenv/)

## 📜 License

This project is open-source and available under the MIT License.
