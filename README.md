# Multi-Agent Humanitarian Aid Router

## Executive Summary
The **Multi-Agent Humanitarian Aid Router** is a high-fidelity, frontend-only research platform engineered for humanitarian field workers and NGO staff operating in disaster zones. 

In crises, responders face "information overload"—massive volumes of dense policy manuals (SPHERE, IASC, UNHAS)—and high-stress environments where connectivity is unreliable or non-existent. This tool uses a **NotebookLM-inspired RAG (Retrieval-Augmented Generation) architecture** to allow workers to synthesize protocols into actionable, cited, and visualized plans in seconds, ensuring that aid delivery remains compliant, safe, and effective.

---

## The Humanitarian Problem
Standard LLM interfaces are often insufficient for NGOs because:
1. **Hallucination Risk:** Generative AI can invent dangerous medical/logistical protocols.
2. **Context Fragmentation:** Information is scattered across disparate PDFs, DOCX, and text files.
3. **Bandwidth Poverty:** Field operations often occur in environments with 2G/3G speeds or satellite-only connections, rendering framework-heavy (React/Angular) applications unusable.

---

## Technical Architecture
This application is built with a **"Brutalist Academic"** philosophy—prioritizing function, speed, and reliability.

*   **Zero-Dependency Core:** Pure vanilla HTML5, CSS3, and ES6 JavaScript. No external frameworks. This ensures instant load times even on heavily degraded connections.
*   **Browser-Native Document Intelligence:**
    *   Uses **PDF.js** and **Mammoth.js** to parse documents entirely on the client side. No sensitive NGO documentation ever leaves the device unencrypted to a server.
*   **Agentic Orchestration:**
    *   The system simulates a **Master Control Agent** pattern. When a user queries the system, the architecture visually stages the reasoning process—Retrieval, Strategy Generation, and Review—before synthesizing the final plan.
*   **Integrated Visualization:**
    *   Utilizes **Mermaid.js** to allow the AI to generate live, interactive process flowcharts, turning dense protocols into immediate, visual SOPs.

---

## Key Capabilities
*   **Source-Grounded Reasoning:** The system enforces citation-based responses. Every claim made by the AI includes a source badge (e.g., `[DOC-1]`) that links back to the original text.
*   **Multi-Document Synthesis:** Users toggle documents on or off in the sidebar to define the AI's "context window." This prevents cross-contamination of unrelated protocols.
*   **Human-in-the-Loop (HITL) Safety:** Implements a visual confidence threshold warning. If the system's internal synthesis confidence drops below a specific margin, the UI flags a mandatory human verification banner.
*   **Exportable Field Data:** Once a strategy is finalized, the system aggregates the chat history to generate a standardized **UN Situation Report (SitRep)**, which can be downloaded instantly as a text file for headquarters reporting.
*   **Offline-First:** All API configurations, uploaded document text, and session preferences are persisted via `localStorage`, ensuring the tool remains functional even after a browser refresh.

---

## Installation & Deployment
1.  **Clone the repository** or download the `index.html` file.
2.  **Deploy:** Since this is a single-file application, it can be hosted on any static file server or simply opened locally (`file://`) for field use.
3.  **Authenticate:** Once opened, input a valid Google Gemini API Key in the header. The application will immediately establish a secure, encrypted session.

---

## Design Philosophy
The UI utilizes a "Nature-Themed Brutalism" aesthetic. 
*   **Color Palette:** Sage greens, forest darks, and earth tones provide a calming, professional environment for high-stress work.
*   **Typography:** Strict use of Courier New and Serif stacks to match the feel of academic archives (Sci-Hub/arXiv), ensuring the text is readable and accessible in harsh sunlight or low-power screens.

---

## Disclaimer
*This tool is a field-ready prototype designed to assist in decision-making and research. All AI-generated protocols, medical triage, or transport routing suggestions must be vetted by a human subject matter expert (SME) before implementation in a disaster setting.*
