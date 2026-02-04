# 💰 FinanceAdvisor AI

A secure, local-first **Retrieval-Augmented Generation (RAG)** chatbot designed to answer questions about financial documents (PDFs) without sending data to the cloud.

![Java](https://img.shields.io/badge/Java-21-orange) ![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.2-green) ![React](https://img.shields.io/badge/React-18-blue) ![Ollama](https://img.shields.io/badge/Ollama-Local-black) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL-pgvector-336791)

## 🚀 Features

* **Full Privacy:** Runs 100% locally using **Ollama** and **Llama 3.1**. No API keys required.
* **RAG Architecture:** Vector search using **PostgreSQL (pgvector)** to retrieve relevant context from financial PDFs.
* **Streaming Responses:** Real-time text generation (Server-Sent Events) for a ChatGPT-like experience.
* **Modern UI:** A clean, dark-mode interface built with **React**, **Tailwind CSS**, and **Lucide Icons**.

## 🏗️ Tech Stack

### Backend
* **Framework:** Spring Boot 3 + Spring AI
* **Database:** PostgreSQL + pgvector extension
* **LLM Engine:** Ollama (running `llama3.1:8b`)
* **Embeddings:** `nomic-embed-text`

### Frontend
* **Framework:** React.js
* **Styling:** Tailwind CSS
* **Icons:** Lucide React

---

## 🛠️ Prerequisites

Before running the project, ensure you have the following installed:

1.  **Java 21+** (Required for Spring AI)
2.  **Node.js & npm**
3.  **Docker** (Optional, only if running DB via container)
4.  **Ollama** (Installed locally)

---

## ⚙️ Setup & Installation

### 1. Configure Ollama (AI Models)
Make sure Ollama is running and pull the necessary models:
```bash
ollama pull llama3.1:8b
ollama pull nomic-embed-text
```

###2. Configure Database (PostgreSQL)
Ensure you have a PostgreSQL database running. You can run one via Docker:

```Bash
docker run -d --name postgres-vector -e POSTGRES_PASSWORD=root -p 5432:5432 -d ankane/pgvector
Or manually create a database named market and enable the extension:
```

###SQL
```
CREATE DATABASE market;
CREATE EXTENSION vector;
```
###3. Backend Setup (Spring Boot)
Navigate to the backend folder:

```Bash
cd backend
```
Place your financial PDF documents in the src/main/resources/docs folder (or wherever your ingestion logic points).

Run the application:

```Bash
./mvnw spring-boot:run
```
###4. Frontend Setup (React)
Navigate to the frontend folder:

```Bash
cd frontend
Install dependencies:
```

```Bash
npm install
Start the development server:
```

```Bash
npm start
```
📸 Usage
Open your browser to http://localhost:3000.

Type a question related to the documents you ingested (e.g., "What is the market outlook for Q4?").

The bot will retrieve the relevant context from the vector store and stream the answer back to you.

🤝 Contributing
Contributions are welcome! Please fork the repository and submit a pull request.

📄 License
This project is licensed under the MIT License.


```bash
git add README.md
git commit -m "Add project documentation"
git push
