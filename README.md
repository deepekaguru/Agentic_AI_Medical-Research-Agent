**Smart Medical Research Agent**

A stateful, privacy-focused AI assistant designed to retrieve and summarize real-world clinical trial data. By combining LangGraph orchestration with a local Llama 3.2 instance, this agent provides researchers with grounded, verifiable data directly from the National Institutes of Health (NIH).


**Key Technical Features**

Agentic Orchestration: Utilizes LangGraph to manage a cyclic workflow, allowing the agent to "reason" about search results before presenting them to the user.

Real-Time Data Integration: Connects to the ClinicalTrials.gov API v2 to fetch live, authoritative study data, avoiding the "hallucination" issues common in standard LLMs.

Medical Safety Guardrails: Features a dedicated Safety Node that intercepts high-risk queries (e.g., dosage requests) and enforces regulatory disclaimers.

Privacy-First Execution: Designed to run entirely on local hardware (optimized for i7-1355U) using Ollama, ensuring sensitive research queries never leave the local machine.

Professional UI: Built with Streamlit, featuring custom CSS for data visualization and direct source linking to NIH records.

**Technical Stack**

Framework: LangGraph

LLM: Llama 3.2 (Local via Ollama)

API: ClinicalTrials.gov API v2

UI: Streamlit

Language: Python 3.10+

**Agentic Architecture**

The agent follows a rigorous logical flow to ensure data integrity:

Start: Captures user query regarding a medical condition.

Assistant Node: Determines if external research is required and calls the search tool.

Search Tool: Fetches up to 5 live trials, including NCT IDs and recruitment statuses.

Safety Node: Evaluates the response for medical advice triggers and appends necessary disclaimers.

Output: Displays formatted results with clickable links to official NIH study pages.
