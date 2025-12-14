# AGENTS.md

> **Standard Version:** 1.0 (Agentic AI Foundation)

> **Agent Name:** Python Tutor Agentic System

> **Author:** Leandro Guiñazu

> **Description:** Multimodal AI Agent for Python Tutoring with Code Execution Capabilities.

## 🤖 System Overview
Este sistema agéntico actúa como un tutor inteligente especializado en programación Python. Utiliza una arquitectura de grafo (StateGraph) para distinguir entre consultas teóricas y ejercicios prácticos, ejecutando código real en un entorno seguro.

## 🧠 Capabilities
* **Multimodal Input Processing:** Analysis of text and base64 encoded images.
  
* **Strict Routing:** Classification of queries into specific Python syllabus modules.
  
* **Code Generation & Execution:** Real-time Python script generation and validation via `PythonREPL`.

* **Theoretical Reasoning:** Context-aware explanations for conceptual questions.

## 🛠️ Tools & Architecture
* **Orchestrator:** LangGraph.

* **Model:** `gemini-2.5-flash` (via `langchain-google-genai`).

* **Tools:**
  
    * `PythonREPL`: For executing generated code.
      
    * `Weave`: For observability and tracing.

## 📥 Input Schema
```json
{
  "input_usuario": "string (The student's query)",
  "input_imagen": "string (Optional: Base64 encoded image string)"
}
```
## 📤 Output Schema
```json
{
  "respuesta_final": "string (Markdown formatted explanation + code + result)",
  "codigo_generado": "string (Raw Python code)",
  "clasificacion": {
    "tipo_tarea": "TEORIA | PRACTICA",
    "modulo": "Identified Module Name"
  }
}
```
