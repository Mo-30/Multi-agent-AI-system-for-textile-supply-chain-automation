# Multi-agent-AI-system-for-textile-supply-chain-automation

> **Automating textile procurement from fabric selection to compliance validation using multi-agent AI architecture.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![React 18](https://img.shields.io/badge/react-18.x-61dafb.svg)](https://reactjs.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-009688.svg)](https://fastapi.tiangolo.com/)

---

## Overview


Multi-agent-AI-system-for-textile-supply-chain-automation is an intelligent supply chain management system designed to automate the entire textile procurement workflow. Built with the growing local fashion industry in mind, this system addresses a critical challenge: supply chain decisions that are traditionally fragmented, slow, and heavily dependent on manual processes.

The system employs five specialized AI agents, each handling a specific stage of the procurement workflow—from selecting raw materials to validating supplier compliance. What traditionally takes 4-6 weeks can now be accomplished in minutes.

---

## Features

- **Multi-Agent Architecture** — Five autonomous AI agents working in sequence
- **Vision-Based Quality Control** — VLM-powered sample inspection using Ollama
- **Economic Order Optimization** — EOQ algorithms with safety stock calculations
- **Compliance Automation** — Certification and ESG validation
- **Human-in-the-Loop** — Manual override capabilities at critical decision points
- **Real-Time Workflow Tracking** — Visual progress indicators across all stages
- **Modern UI** — Glassmorphism design with dark theme

---

## The Five AI Agents

### Agent 1: Textile Selection Engine

Analyzes the textile catalog and recommends fabrics based on user specifications.

| Input | Processing | Output |
|-------|------------|--------|
| Target price | Weighted scoring algorithm | Ranked textile recommendations |
| Durability requirement (1-10) | Price-performance analysis | Match scores |
| Target season | Sustainability metrics evaluation | Availability status |

### Agent 2: Manufacturer Selection

Evaluates and ranks suppliers using multi-criteria decision analysis.

| Input | Processing | Output |
|-------|------------|--------|
| Selected textile | Vendor reliability scoring | Ranked manufacturers |
| Order quantity | Capacity utilization analysis | Lead time estimates |
| Delivery constraints | Geographic optimization | Price tier classification |
| Priority (cost/quality/speed) | Historical performance weighting | Composite scores |

### Agent 3: Sample Quality Evaluation

Deploys a Vision Language Model to analyze fabric samples for quality assurance.

| Input | Processing | Output |
|-------|------------|--------|
| Sample image | Weave consistency analysis | Quality score (0-100) |
| Textile specifications | Color accuracy measurement | Defect probability |
| Reference standards | Surface defect detection | Pass/Fail recommendation |
| | Fiber alignment evaluation | Detailed findings report |

### Agent 4: Order Quantity Optimization

Calculates optimal order quantities using operations research techniques.

| Input | Processing | Output |
|-------|------------|--------|
| Forecasted demand | EOQ formula implementation | Optimal order quantity |
| Current inventory | Safety stock calculation | Reorder point |
| Holding costs | Service level optimization | Orders per year |
| Setup costs | Lead time factoring | Total annual cost projection |

### Agent 5: Compliance & Sustainability Validator

Cross-references supplier certifications and validates ESG compliance.

| Input | Processing | Output |
|-------|------------|--------|
| Selected supplier | Certification verification | Compliance status |
| Required certifications | ESG score validation | Gap analysis |
| ESG threshold | Policy cross-referencing | Approval/Escalation decision |

---

## Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        FRONTEND (React)                         │
│  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐  │
│  │ Agent 1 │ │ Agent 2 │ │ Agent 3 │ │ Agent 4 │ │ Agent 5 │  │
│  │Textile  │ │Manufact.│ │ Sample  │ │  Order  │ │Compliance│  │
│  └────┬────┘ └────┬────┘ └────┬────┘ └────┬────┘ └────┬────┘  │
│       │           │           │           │           │        │
└───────┼───────────┼───────────┼───────────┼───────────┼────────┘
        │           │           │           │           │
        ▼           ▼           ▼           ▼           ▼
┌─────────────────────────────────────────────────────────────────┐
│                     BACKEND (FastAPI)                           │
│  ┌──────────────────────────────────────────────────────────┐  │
│  │                  REST API Endpoints                       │  │
│  │  /agent/textile-selection    /agent/sample-evaluation    │  │
│  │  /agent/manufacturer         /agent/order-optimization   │  │
│  │  /agent/compliance                                        │  │
│  └──────────────────────────────────────────────────────────┘  │
│                              │                                  │
│              ┌───────────────┼───────────────┐                 │
│              ▼               ▼               ▼                 │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐         │
│  │   Scoring    │  │     EOQ      │  │    Ollama    │         │
│  │  Algorithms  │  │ Optimization │  │     VLM      │         │
│  └──────────────┘  └──────────────┘  └──────────────┘         │
└─────────────────────────────────────────────────────────────────┘
                               │
                               ▼
┌─────────────────────────────────────────────────────────────────┐
│                      DATA LAYER (MySQL)                         │
│  ┌────────────┐  ┌────────────┐  ┌────────────┐                │
│  │  Materials │  │  Vendors   │  │  Orders    │                │
│  │   Catalog  │  │   Master   │  │   & POs    │                │
│  └────────────┘  └────────────┘  └────────────┘                │
└─────────────────────────────────────────────────────────────────┘
```

---

## Tech Stack

### Frontend
- **React 18** — Component-based UI
- **Material UI** — Modern component library
- **Framer Motion** — Animations and transitions
- **Axios** — HTTP client

### Backend
- **FastAPI** — High-performance Python web framework
- **Pydantic** — Data validation
- **Uvicorn** — ASGI server
- **Python 3.10+** — Core language

### AI/ML
- **Ollama** — Local LLM/VLM inference
- **LLaVA** — Vision Language Model for sample analysis
- **NumPy** — Numerical computations
- **Custom scoring algorithms** — Multi-criteria decision analysis

### Database
- **MySQL/MariaDB** — Relational data storage
- **SQLAlchemy** — ORM (optional)

---

## Installation

### Prerequisites

- Python 3.10 or higher
- Node.js 18 or higher
- Ollama installed locally (for VLM features)
- MySQL/MariaDB (optional, can use mock data)

---

## Usage

### Starting the Application

1. Start the backend server:
```bash
cd backend && uvicorn main:app --reload --port 8000
```

2. Start the frontend:
```bash
cd frontend && npm start
```

3. Open your browser at `http://localhost:3000`

### Workflow Demonstration

1. **Agent 1** — Set price ($25), durability (7), season (Winter) → Run Agent → Select a textile
2. **Agent 2** — Set quantity (5000), delivery (30 days), priority (balanced) → Run Agent → Select manufacturer
3. **Agent 3** — Upload fabric sample image → Run Inspection → Review VLM analysis
4. **Agent 4** — Configure demand parameters → Run Optimization → Review EOQ results
5. **Agent 5** — Select required certifications → Run Validation → Confirm compliance

---

## API Reference

### Health Check
```
GET /health
```

### Agent Endpoints

#### Textile Selection
```
POST /agent/textile-selection
Content-Type: application/json

{
  "price": 25.0,
  "durability": 7,
  "season": "Winter"
}
```

#### Manufacturer Selection
```
POST /agent/manufacturer-selection
Content-Type: application/json

{
  "textile_id": "T100",
  "quantity": 5000,
  "max_delivery_days": 30,
  "priority": "balanced"
}
```

#### Sample Evaluation
```
POST /agent/sample-evaluation
Content-Type: multipart/form-data

file: <image_file>
textile_id: "T100"
manufacturer_id: "M100"
```

#### Order Optimization
```
POST /agent/order-optimization
Content-Type: application/json

{
  "forecasted_demand": 10000,
  "current_inventory": 2000,
  "holding_cost": 2.5,
  "setup_cost": 50,
  "lead_time_days": 14,
  "service_level": 95
}
```

#### Compliance Validation
```
POST /agent/compliance-validation
Content-Type: application/json

{
  "supplier_id": "M100",
  "certifications": ["OEKO-TEX", "ISO-9001"],
  "sustainability_threshold": 70
}
```

---

## Configuration

### Environment Variables

Create a `.env` file in the backend directory:

```env
# Database
DATABASE_URL=mysql://user:password@localhost:3306/nexus_ai

# Ollama
OLLAMA_HOST=http://localhost:11434
OLLAMA_MODEL=llava

# API
API_HOST=0.0.0.0
API_PORT=8000
DEBUG=true
```

---

## Project Structure

```
nexus-ai-textile/
├── backend/
│   ├── main.py              # FastAPI application & endpoints
│   ├── agents/
│   │   ├── textile.py       # Agent 1 logic
│   │   ├── manufacturer.py  # Agent 2 logic
│   │   ├── sample.py        # Agent 3 logic (VLM)
│   │   ├── order.py         # Agent 4 logic (EOQ)
│   │   └── compliance.py    # Agent 5 logic
│   ├── models/
│   │   └── schemas.py       # Pydantic models
│   ├── data/
│   │   └── mock_data.py     # Sample datasets
│   ├── requirements.txt
│   └── .env
│
├── frontend/
│   ├── public/
│   │   └── index.html
│   ├── src/
│   │   ├── components/
│   │   │   ├── TextileAgent.jsx
│   │   │   ├── ManufacturerAgent.jsx
│   │   │   ├── SampleAgent.jsx
│   │   │   ├── OrderAgent.jsx
│   │   │   └── ComplianceAgent.jsx
│   │   ├── services/
│   │   │   └── api.js
│   │   ├── App.js
│   │   ├── index.js
│   │   └── index.css
│   └── package.json
│
├── docs/
│   └── PRESENTATION.md
│
├── LICENSE
└── README.md
```

---

## Future Roadmap

- [ ] Integration with ERP systems via OData APIs
- [ ] Fine-tuned VLM on textile-specific defect datasets
- [ ] Real-time market price feeds for dynamic cost optimization
- [ ] Multi-language support (Arabic, French)
- [ ] Mobile application (React Native)
- [ ] Blockchain-based compliance audit trail
- [ ] Integration with IoT sensors for real-time quality monitoring

---

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

Please ensure your code follows the existing style and includes appropriate tests.

---

## License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

- Inspired by the growing local fashion industry in Egypt
- Built with modern AI/ML techniques for real-world manufacturing challenges
- Special thanks to the open-source community for the amazing tools

---

## Contact

**Mohamed** — [LinkedIn](https://linkedin.com/in/mohamedsherifelian) — [Email](mailto:mosherifelian@gmail.com)

Project Link: [https://github.com/yourusername/
Multi-agent-AI-system-for-textile-supply-chain-automation](https://github.com/M0-30/
Multi-agent-AI-system-for-textile-supply-chain-automation)

---

<p align="center">
  <b>Built with ❤️</b>
</p>
