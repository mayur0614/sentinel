# Sentinel: Autonomous Brand Defense Ecosystem
### *A Self-Healing Digital Immune System for Businesses*

---

## 🖼️ System Architecture
![Sentinel Architecture Diagram](sentinel.png)
> **Note to Judges:** The diagram above illustrates the end-to-end flow from data ingestion to autonomous action, highlighting the "Sentinel Brain" as the central reasoning engine.

---

## 📌 Project Overview
**Sentinel** is an agentic AI system designed to move brand protection from **reactive** to **autonomous**. Instead of waiting for a human to report a phishing site or a fake social media account, Sentinel acts as a digital workforce—continuously scanning, deciding, and neutralizing threats in real-time.

---

## 🏗️ Technical Architecture

### 1. The Sentinel Brain (Core Engine)
The architecture is built on a "Observe-Orient-Decide-Act" (OODA) loop powered by Agentic Intelligence:

* **Ingestion Layer:** Connects to Web Crawlers, Social Media APIs (X, Meta), and Domain Registrars to pull live data.
* **Reasoning Layer:** Uses LLMs to analyze visual and textual content. It asks: *"Is this logo used legally? Is this tone consistent with the brand? Is this a phishing link?"*
* **Action Layer:** Automatically generates and sends DMCA takedown requests, reports accounts via API, and notifies brand owners.

### 2. Database Schema (The Knowledge Base)
Sentinel uses a relational structure to track threats from discovery to resolution.

| Table | Description | Key Fields |
| :--- | :--- | :--- |
| **Brands** | Client profiles & authorized assets. | `brand_id`, `name`, `official_domains`, `logo_hash` |
| **Monitored_Sources** | Tracks the "where/when" of scans. | `source_id`, `url_pattern`, `platform_type`, `last_scan` |
| **Threats_Detected** | Records every suspicious finding. | `threat_id`, `brand_id`, `type`, `confidence_score` |
| **Actions_Taken** | Logs the autonomous response. | `action_id`, `threat_id`, `action_type`, `status`, `result` |

---

## 🔄 System Relationships

1.  **Brand → Sources (1:N):** One brand monitors multiple platforms (Web, X, IG).
2.  **Source → Threats (1:N):** One platform (e.g., X) can contain multiple scam accounts.
3.  **Threat → Action (1:N):** One detected threat can trigger multiple actions (e.g., Send Takedown + Notify Brand + Blacklist IP).

---

## 🛠️ Technical Stack (Proposed)
* **Language:** Python 3.11+
* **AI Orchestration:** LangChain / CrewAI (for agentic workflows)
* **LLM:** Gemini 1.5 Pro (for multi-modal vision & reasoning)
* **Database:** PostgreSQL (Metadata) + Pinecone (Vector storage for logo matching)
* **Infrastructure:** Docker / Google Cloud Run

---

## 🚀 The Competitive Edge
* **Latency:** Response time drops from **days** (manual) to **seconds** (autonomous).
* **Scalability:** A single instance of Sentinel can protect 1,000+ brands simultaneously.
* **Agentic Reasoning:** It understands *context*—distinguishing between a parody account and a malicious phishing attempt.
