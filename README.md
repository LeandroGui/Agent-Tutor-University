# 🎓 Python Tutor Agentic System

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![LangGraph](https://img.shields.io/badge/Orchestration-LangGraph-orange)
![Gemini](https://img.shields.io/badge/AI-Google%20Gemini%202.5-4285F4)
![Weave](https://img.shields.io/badge/Observability-Weave-yellow)

Un sistema agéntico inteligente diseñado para actuar como tutor universitario de programación en Python. Utiliza una arquitectura de grafos para clasificar, razonar, generar código y validarlo mediante ejecución real.

## 🌟 Características Principales

* **🧠 Arquitectura Agéntica:** Implementado sobre **LangGraph** para un flujo de control determinista y robusto.
* **👀 Multimodalidad Nativa:** Capaz de recibir **Imágenes** (capturas de ejercicios, errores) y **Texto** simultáneamente.
* **🛡️ Ejecución Segura (Sandbox):** Incluye un nodo `PythonREPL` que ejecuta el código generado por la IA para verificar su correctitud antes de entregarlo al usuario.
* **📊 Observabilidad Completa:** Integración con **Weave (W&B)** para trazas detalladas de latencia, inputs y outputs.
* **🎯 Enrutamiento Estricto:** Utiliza **Pydantic** para clasificar consultas estrictamente dentro del programa de estudio oficial.

## 🏗️ Arquitectura Lógica

El sistema funciona como una máquina de estados finitos. A continuación se detalla el flujo de decisión:

```mermaid
graph TD
    Start([Input Usuario <br> Texto/Imagen]) --> Router{Clasificador}
    
    Router -- "Es Teoría" --> Expert[Experto Teórico <br> Gemini 2.5 Flash]
    Router -- "Es Práctica" --> Coder[Programador <br> Gemini 2.5 Flash]
    
    Coder --> Executor[Ejecutor <br> Python REPL]
    Executor --> Synthesis[Sintetizador de Respuesta]
    
    Expert --> End([Respuesta Final])
    Synthesis --> End

🛠️ Stack Tecnológico
LLM: Google Gemini 2.5 Flash (Optimizado para velocidad y código).

Framework: LangChain & LangGraph.

Validación: Pydantic.

Tracing: Weights & Biases (Weave).

Entorno: Google Colab / Jupyter Notebook.

📋 Casos de Uso Demostrados
1.Resolución de Ejercicios Visuales: El agente extrae datos de una imagen PNG y genera el script para resolverlo.

2.Consultas Conceptuales: Explicaciones pedagógicas sobre estructuras de datos.

3.Debugging Automático: Generación y prueba de scripts en tiempo real.

🚀 Cómo Ejecutar
1.Clonar el repositorio.

2.Instalar dependencias:
pip install google-genai langchain langchain-google-genai langgraph langchain-experimental pydantic weave
3.Configurar API Keys (Google AI Studio & W&B).

4.Ejecutar el notebook Agente_Tutor_Universitario.ipynb.

📈 Trazabilidad (Weave)
Este proyecto implementa monitoreo de trazas para auditoría de IA. Ver Dashboard de Ejemplo en W&B (https://www.google.com/url?q=https%3A%2F%2Fwandb.ai%2Fteamlg-ai%2Fagente_tutor_python%2Fweave%2Ftraces%3Fview%3Dtraces_2025-12-12_05-41-48-915)

Author: Leandro Guiñazu Proyecto desarrollado como parte del portfolio de Ingeniería de IA Generativa.

