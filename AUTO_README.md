# 🤖 Project Overview
  RepoAgent automatically generates repository-level documentation by analyzing your codebase.
  It scans source files, extracts classes/functions, and writes structured Markdown docs to `markdown_docs/`.

This README combines all per-file docs into one simple overview.


## ⚙️ Quick Start (Install & Run)
    ```bash
# 1) create & activate venv
python -m venv venv
source venv/bin/activate
# 2) install RepoAgent
pip install repoagent
# 3) (optional) use Ollama for local models
open -a Ollama
export OPENAI_API_KEY=ollama
export OPENAI_BASE_URL=http://localhost:11434/v1
# 4) generate docs
repoagent run --target-repo-path "$(pwd)" --markdown-docs-path "$(pwd)/markdown_docs"
```


## 📂 Repository Structure
    ```
RepoAgent/
  repo_agent/
    __init__.py
    __main__.py
    utils/
      gitignore_checker.py
      meta_info_utils.py
    chat_with_repo/
      __init__.py
      __main__.py
```

## 🧱 Key Modules & Responsibilities
| Module | Summary | Docs |
|---|---|---|
| **ClassDef ChangeDetector** | **Documentation:** | [open file](./markdown_docs/repo_agent/change_detector.md) |
| **ClassDef ChatEngine** | **ChatEngine**: The function of ChatEngine is to generate documentation for a given item by building and returning system and user prompts based on the provided content. | [open file](./markdown_docs/repo_agent/chat_engine.md) |
| **ClassDef GradioInterface** | **GradioInterface**: The function of GradioInterface is to establish an interface for user interaction through a graphical user interface (GUI) using the Gradio library. | [open file](./markdown_docs/repo_agent/chat_with_repo/gradio_interface.md) |
| **ClassDef JsonFileProcessor** | **JsonFileProcessor**: The function of JsonFileProcessor is to process JSON files by reading their contents, extracting relevant data, and searching for specific information within the data. | [open file](./markdown_docs/repo_agent/chat_with_repo/json_handler.md) |
| **FunctionDef main** | **Documentation: Target Object** | [open file](./markdown_docs/repo_agent/chat_with_repo/main.md) |
| **ClassDef RepoAssistant** | **RepoAssistant**: The function of RepoAssistant is to facilitate a conversational interface between users and a repository of information, utilizing natural language processing techniques to generate… | [open file](./markdown_docs/repo_agent/chat_with_repo/rag.md) |
| **ClassDef TextAnalysisTool** | **TextAnalysisTool**: The function of TextAnalysisTool is to analyze text inputs and generate various outputs based on predefined analysis tools. | [open file](./markdown_docs/repo_agent/chat_with_repo/text_analysis_tool.md) |
| **ClassDef VectorStoreManager** | **VectorStoreManager**: The function of VectorStoreManager is to create and manage a vector store for storing and retrieving document embeddings. | [open file](./markdown_docs/repo_agent/chat_with_repo/vector_store_manager.md) |
| **ClassDef EdgeType** | **EdgeType**: The function of EdgeType is to define distinct types of edges that can be used to represent relationships between objects in a system. | [open file](./markdown_docs/repo_agent/doc_meta_info.md) |
| **ClassDef FileHandler** | **Documentation:** | [open file](./markdown_docs/repo_agent/file_handler.md) |
| **ClassDef InterceptHandler** | **InterceptHandler**: The function of InterceptHandler is to intercept and redirect standard logging output to loguru for consistent handling across the application. | [open file](./markdown_docs/repo_agent/log.md) |
| **FunctionDef cli** | **cli**: The function of cli is to initiate a repository-level code documentation generation process using an LLM-powered framework. The cli function serves as the entry point for generating comprehen… | [open file](./markdown_docs/repo_agent/main.md) |

## 🔄 Data Flow / Call Relationships (High level)
    - High-level flow:
  - **Runner** orchestrates scanning and doc generation.
  - **FileHandler** reads files and writes markdown.
  - **ChangeDetector** tracks file changes and updates docs.
  - **ProjectManager** builds structure trees.
  - **ChatEngine** composes prompts and docs.
  - Output stored in `markdown_docs/`.

## 🚧 Limitations & Future Work
  - Add multi-language parsing (Java/C++).
  - Enhance diagrams/visuals for relationships.
  - Integrate with CI/pre-commit for auto updates.

## 📜 License
  - Apache License

*Generated automatically via `tools/generate_readme.py`.*
