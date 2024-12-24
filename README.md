# Graph RAG Implementation with LangChain, Neo4j, and Mistral AI

This project demonstrates a Graph Retrieval-Augmented Generation (RAG) pipeline implemented using [LangChain](https://langchain.com/), [Neo4j](https://neo4j.com/), and [Mistral AI](https://mistral.ai/). It leverages the power of graph databases and advanced AI models to provide contextual and accurate responses.

## Features

- **Graph-based Retrieval:** Utilizes Neo4j as a graph database to store and retrieve knowledge efficiently.
- **AI-Powered Generation:** Employs Mistral AI for generating high-quality, context-aware responses.
- **LangChain Integration:** Combines the modularity and functionality of LangChain for chaining multiple LLM and retrieval operations.
- **Scalability:** Designed for flexible expansion with additional nodes and knowledge.

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Installation](#installation)
3. [Configuration](#configuration)
4. [Usage](#usage)
5. [Architecture](#architecture)
6. [Contributing](#contributing)
7. [License](#license)

---

## Prerequisites

Ensure you have the following installed:

- Python 3.8+
- Neo4j Community or Enterprise Edition
- Mistral AI model (setup instructions below)
- pip (Python package manager)

## Installation

Clone the repository and navigate to the project directory:

```bash
git clone https://github.com/your-username/graph-rag-langchain.git
cd graph-rag-langchain
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Set up your Neo4j instance and start the database server.

## Configuration

1. **Neo4j Connection:**
   Update the `config.py` file with your Neo4j credentials:

   ```python
   NEO4J_URI = "bolt://localhost:7687"
   NEO4J_USER = "neo4j"
   NEO4J_PASSWORD = "your_password"
   ```

2. **Mistral AI API Key:**
   Obtain your API key from Mistral AI and update the `config.py` file:

   ```python
   MISTRAL_API_KEY = "your_api_key"
   ```

3. **LangChain Settings:**
   Configure LangChain parameters in the `config.py` file as needed.

## Usage

### Ingesting Data into Neo4j

Populate the Neo4j graph database with your data:

```bash
python data_ingestion.py --data path/to/your/data.json
```

### Running the Application

Start the RAG pipeline:

```bash
python app.py
```

Interact with the application via the provided interface (CLI, API, or web interface).

### Query Example

```bash
Enter your query: "What is the relationship between X and Y?"
```

The system retrieves relevant information from Neo4j and generates a response using Mistral AI.

## Architecture

### Workflow

1. **Query Input:** User inputs a natural language query.
2. **Graph Retrieval:** Relevant nodes and relationships are retrieved from the Neo4j database.
3. **AI Generation:** Context is provided to Mistral AI for generating a response.
4. **Response Output:** The generated response is displayed to the user.

### Component Diagram

```text
+-------------+       +------------+       +---------------+
|  User Input | ----> |   LangChain| ----> |   Neo4j Graph |
+-------------+       +------------+       +---------------+
                                       \
                                        +---------------+
                                        | Mistral AI    |
                                        +---------------+
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork this repository.
2. Create a new branch: `git checkout -b feature-name`.
3. Commit your changes: `git commit -m 'Add feature'`.
4. Push to the branch: `git push origin feature-name`.
5. Submit a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

---

Feel free to report issues or suggest features by opening an issue in this repository.

Happy coding!

