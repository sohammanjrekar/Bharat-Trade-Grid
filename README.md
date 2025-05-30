# 🇮🇳 Bharat Trade Grid

### 🔗 National Industrial Intelligence + B2B Vendor Matchmaking Platform

> Empowering India to reduce import dependency, accelerate domestic manufacturing, and seamlessly connect exporters, vendors, and MSMEs through data-driven insights and AI-enabled trade matchmaking.

---

## 📌 Project Overview

**Bharat Trade Grid** is an advanced, AI-powered web platform designed to address critical national priorities by:

- 📊 Analyzing and visualizing India’s import dependencies and identifying domestic manufacturing gaps  
- 📈 Guiding entrepreneurs and policymakers with actionable investment insights  
- 🤝 Facilitating direct connections between MSMEs, raw material vendors, skilled labor pools, and exporters  
- 📑 Automating complex export/import documentation to reduce compliance burdens  
- 🚚 Enabling smarter, collaborative B2B order placement, negotiation, and export logistics  

This platform aims to create an integrated ecosystem where Indian industries and exporters collaborate efficiently, ultimately reducing reliance on imports and boosting the **“Make in India”** initiative.

---

## 🚀 Core Features & Modules

| Module                                 | Description                                                                                                                        |
|--------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| 📈 **Import Intelligence Dashboard** | Visualize top imported products, import volumes, cost trends, and identify states/sectors relying heavily on imports. Enables targeting of manufacturing gaps. |
| 🗺️ **Sectoral Heatmap**               | Interactive map showing strong and weak industrial clusters in India, labor availability, infrastructure, and PLI eligibility to guide new factory setups. |
| 🧑‍🏭 **Vendor & MSME Matchmaking Engine** | Connect MSMEs with raw material vendors, skilled labor pools (from Skill India DB), and exporters for bulk orders and shared logistics. |
| 📃 **Auto Documentation & Compliance Engine** | Auto-generate GST invoices, export/import documentation, government subsidy eligibility checks, and track compliance timelines to reduce bureaucratic friction. |
| 💬 **Smart Order & Negotiation Platform** | In-app chat, automated price comparisons, MOQ control, and transparent negotiation history for faster and smarter B2B transactions. |
| 🌐 **Collaborative Exporter Network** | Allows exporters to bundle shipments, share containers, and negotiate joint deals to reduce shipping costs and enhance export competitiveness. |

---

## 🧩 System Architecture Overview

**Frontend:**  
- Built with **React.js / Next.js** for fast, SEO-friendly, and responsive user experiences.

**Backend:**  
- Developed using **FastAPI (Python)** for high-performance RESTful APIs, asynchronous processing, and easy AI model integration.

**Database:**  
- Uses **PostgreSQL** for relational data management with ACID compliance.  
- Employs **Redis** for caching frequently accessed data and session management to optimize performance.

**AI/ML Components:**  
- Implements **Scikit-learn** for data clustering and matchmaking algorithms.  
- Integrates **OpenAI GPT APIs** for negotiation assistance and intelligent communication.

**Mapping and Visualization:**  
- Utilizes **Mapbox** and **D3.js** for dynamic geographical visualizations such as heatmaps and trade flows.

**Deployment:**  
- Services containerized with **Docker**, orchestrated by **Kubernetes** for scalability and fault tolerance.  
- Hosted on cloud providers like **AWS** or **GCP** for reliability and global accessibility.

---

## 🔌 APIs & External Data Sources

| API / Data Source                         | Purpose & Usage                                                                                     |
|------------------------------------------|---------------------------------------------------------------------------------------------------|
| [DGCIS](https://www.dgciskol.gov.in/)           | Detailed import/export statistics for trade intelligence and demand-supply analysis.               |
| [DGFT](https://www.dgft.gov.in/)                 | Export licensing data, duty structures, and government schemes for exports, enabling compliance automation. |
| [GSTN](https://www.gst.gov.in/)                  | Auto-generate GST-compliant invoices and monitor tax compliance.                                   |
| [GeM](https://gem.gov.in/)                        | MSME vendor data and government procurement opportunities to enhance vendor discovery.            |
| MCA, NSDC, Skill India DBs                       | Verify company registrations, map skilled labor availability, and support vendor matchmaking.     |

---

## 🛠️ Setup Instructions (Local Development)

Follow these steps to get the Bharat Trade Grid platform running locally for development or testing.

### Prerequisites

- Python 3.9 or higher  
- Node.js (v14+) and npm  
- PostgreSQL database (v12+)  
- Redis server  
- Docker and Docker Compose (for containerized services)  
- RabbitMQ (optional for async job processing)

---

### Backend Setup

```bash
# Clone the repository
git clone https://github.com/yourusername/bharat-trade-grid.git
cd bharat-trade-grid/backend

# Create and activate virtual environment
python3 -m venv env
source env/bin/activate

# Install required packages
pip install -r requirements.txt

# Set environment variables (example)
export DATABASE_URL=postgresql://user:password@localhost:5432/bharat_trade
export REDIS_URL=redis://localhost:6379/0
export SECRET_KEY='your-secret-jwt-key'

# Run database migrations
alembic upgrade head

# Start FastAPI server with auto-reload
uvicorn main:app --reload --host 0.0.0.0 --port 8000
```
### Frontend Setup

```bash
cd ../frontend

# Install dependencies
npm install

# Run development server
npm run dev

```
Open [http://localhost:3000](http://localhost:3000/) to access the frontend.

### 🧱 Project Structure Overview
```bash
bharat-trade-grid/
├── backend/
│   ├── app/
│   │   ├── api/               # REST API routes & versioning
│   │   ├── core/              # Configs, settings, security
│   │   ├── models/            # Database models (ORM)
│   │   ├── services/          # Business logic & external API clients
│   │   ├── main.py            # FastAPI app entry point
│   ├── tests/                 # Backend unit and integration tests
│   ├── requirements.txt       # Python dependencies
│   └── Dockerfile             # Backend container image
├── frontend/
│   ├── components/            # React components UI
│   ├── pages/                 # Next.js pages/routes
│   ├── public/                # Static assets
│   ├── styles/                # CSS/SCSS files
│   ├── package.json           # Frontend dependencies
│   └── next.config.js         # Next.js config
├── docker-compose.yaml        # Docker multi-service orchestration
└── README.md                  # Project documentation

```

🔐 Authentication & Security
----------------------------

*   🔐 OAuth2 with JWT tokens for stateless, secure authentication
    
*   🛡️ Role-based access control (Admin, Vendor, Exporter, MSME)
    
*   🔑 Password hashing with bcrypt
    
*   📡 HTTPS enforced in production via NGINX reverse proxy
    
*   🛠️ Rate limiting and request validation to prevent abuse
    

🐳 Containerization & Orchestration
-----------------------------------

*   🐳 Backend and frontend services containerized using Docker
    
*   📩 Messaging queue with RabbitMQ for async tasks (document generation, notifications)
    
*   ⚙️ Kubernetes manifests for deployment, autoscaling, and service discovery
    
*   🌐 NGINX used as ingress controller and load balancer
    

📈 Monitoring & Logging
-----------------------

*   📊 Prometheus for metrics collection (CPU, memory, request rates)
    
*   📉 Grafana dashboards for real-time system health and business KPIs
    
*   🪎 Centralized logging with ELK stack or alternatives (optional)
    

🚀 Deployment & CI/CD
---------------------

*   🧪 Automated builds and tests triggered on Git pushes via GitHub Actions
    
*   🐙 Docker images published to GitHub Container Registry or DockerHub
    
*   🔄 Kubernetes rolling updates managed via Helm charts
    
*   🔔 Slack notifications for deployment status
    
*   🚢 Optional GitOps integration with ArgoCD or FluxCD
    

🤝 Contribution Guidelines
--------------------------

We welcome contributions! Please:

*   🔀 Fork the repo and create feature branches
    
*   ✍️ Write clear commit messages and document new features
    
*   🧪 Include unit and integration tests for new functionality
    
*   📄 Submit pull requests for review and discussion
    

📄 License
----------

This project is licensed under the **MIT License** — see the LICENSE file for details.

📨 Contact & Support
--------------------

For questions or help:

*   GitHub Issues: [https://github.com/yourusername/bharat-trade-grid/issues](https://github.com/yourusername/bharat-trade-grid/issues)
    
*   Email: 📧 [support@bharattradegrid.in](mailto:support@bharattradegrid.in)
