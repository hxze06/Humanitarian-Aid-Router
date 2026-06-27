# Humanitarian-Aid-Router
Multi-Agent Humanitarian Aid Router

Overview

The Multi-Agent Humanitarian Aid Router is a lightweight, frontend-only application designed to serve as a multi-document research assistant for field workers, NGOs, and crisis responders.

Operating in disaster zones often means dealing with severely degraded bandwidth and high-stress cognitive loads. This tool solves this by using a NotebookLM-inspired architecture, allowing users to upload complex Standard Operating Procedures (SOPs) and query an agentic AI system to receive synthesized, directly cited action plans in seconds.

This project was developed as a capstone submission for a highly accredited certification program, emphasizing zero-dependency performance, strict source grounding, and accessible design.

Key Features

Zero-Overhead Architecture: Built entirely with vanilla HTML5, CSS3, and ES6 JavaScript. No heavy frameworks (React/Vue/Angular) are used, ensuring immediate load times on 2G/3G satellite connections.

Client-Side Document Parsing: Privacy-first file handling. Users can upload .txt, .pdf, and .docx files. Parsing happens entirely within the browser using lightweight web workers, ensuring sensitive NGO data never leaves the local machine unencrypted.

Multi-Document Context Window: Users can toggle specific documents on or off to actively manage the LLM's context window, forcing the AI to synthesize answers only from verified, active SOPs.

Agentic Workflow Simulation: The UI visually maps a multi-agent reasoning process (Master Routing -> Knowledge Retrieval -> Strategy Generation -> Safety Review) before delivering an answer, building trust with the end-user.

Brutalist Academic Design: Utilizes a high-contrast, strictly functional aesthetic inspired by academic repositories (arXiv/Sci-Hub), paired with a calming, nature-inspired color palette (Forest, Sage, Earth).

System Architecture (RAG)

The application utilizes a specialized Retrieval-Augmented Generation (RAG) workflow:

Ingestion: Local parsing of uploaded documents via pdf.js and mammoth.js.

Context Construction: The system dynamically concatenates all "Active" document texts into an injected prompt.

Agentic Prompting: The Gemini 2.5 Flash API is called via REST with strict system instructions to act as a Humanitarian Orchestrator. It is constrained to answer only using the provided context and must cite sources using Document IDs (e.g., [DOC-1]).

Delivery: The response is formatted into a highly readable, brutalist chat interface.

Installation & Usage

Because this application relies on a serverless, single-file architecture, setup is instantaneous.

Prerequisites

A modern web browser (Chrome, Firefox, Safari, Edge).

A valid Google Gemini API Key.

Running the Application

Clone this repository or download the index.html file.

Double-click index.html to open it directly in your web browser. No local server (npm start, python -m http.server) is strictly required, though it can be used.

Authenticate: Enter your Gemini API key in the top navigation bar and click "Connect". (Note: The key is stored temporarily in session memory and is never saved to a database).

Manage Sources: Use the left pane to view default Humanitarian Standards (SPHERE, UNHAS, IASC) or click + Upload File to add your own PDFs and DOCX files.

Query the System: Ask the Orchestrator a question in the right pane (e.g., "What is the protocol for water sanitation near living areas?").

Technical Stack

Frontend UI: HTML5, CSS3 (CSS Grid/Flexbox), ES6 JavaScript.

LLM Provider: Google Gemini 2.5 Flash API (REST).

PDF Parsing: pdf.js (v3.11.174)

DOCX Parsing: mammoth.js (v1.6.0)

Certification Highlights & Architectural Decisions

Hallucination Mitigation: Standard chatbots are dangerous in crisis scenarios. By enforcing a "Source Library" paradigm, the agent is mathematically constrained by the prompt structure to rely only on uploaded guidelines.

Memory Management: Implemented Set() structures in JavaScript to handle active document contexts efficiently without duplicating payload data.

Accessibility (WCAG): The UI enforces high contrast ratios between the text (#1A1C1A) and the background (#F4F6F4), utilizing readable Serif fonts for document viewing and Monospace for system logs.

Disclaimer

This tool is a functional prototype developed for educational and certification purposes. While it parses real documents and connects to a live LLM, any outputs generated during a real-world humanitarian crisis should be reviewed by a human expert before execution.
