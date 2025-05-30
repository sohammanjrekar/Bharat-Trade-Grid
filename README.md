# 🇮🇳 Bharat Trade Grid

### 🔗 National Industrial Intelligence + B2B Vendor Matchmaking Platform

> Helping India reduce imports, strengthen manufacturing, and connect exporters, vendors & MSMEs.

---

## 📌 Overview

**Bharat Trade Grid** is an AI-driven web platform designed to:
- Identify India's import dependencies and market gaps
- Guide industrial investment decisions
- Connect MSMEs with raw vendors, labor pools, and exporters
- Automate export/import documentation
- Facilitate collaborative exports and smart B2B trade

---

## 🚀 Core Features

| Module                    | Description                                                                 |
|---------------------------|-----------------------------------------------------------------------------|
| 📈 Import Intelligence     | Track top imported products, volumes, trends, and usage by state/sector    |
| 🗺️ Sectoral Heatmap       | Map India's strong/weak manufacturing zones; suggest optimal setup regions |
| 🧑‍🏭 Vendor Matchmaking    | MSMEs connect with suppliers, labor pools, and exporters                   |
| 📃 Auto Documentation      | Generate GST, export/import docs, and check subsidy eligibility            |
| 💬 Smart Order Platform    | Chat, negotiate prices, share MOQs, and group export shipments             |
| 🌐 Exporter Collaboration  | Bundle shipments and negotiate international orders as a group             |

---

## 🧩 System Architecture

- **Frontend:** React.js / Next.js  
- **Backend API:** FastAPI (Python)  
- **Database:** PostgreSQL + Redis (caching)  
- **AI/ML:** Scikit-learn / GPT APIs (matchmaking + negotiation assist)  
- **Mapping:** Mapbox / D3.js for heatmaps & demand-supply overlays  
- **Hosting:** AWS or GCP (Dockerized services)  

---

## 🔌 APIs and Data Sources

| Source          | Use                                                                 |
|-----------------|----------------------------------------------------------------------|
| [DGCIS](https://www.dgciskol.gov.in/)       | Import/export data (Govt. of India)                            |
| [DGFT](https://www.dgft.gov.in/)           | Licensing, duty, and export schemes                           |
| [GSTN](https://www.gst.gov.in/)            | GST document auto-generation                                 |
| [GeM](https://gem.gov.in/)                | Government eMarketplace MSME data                            |
| MCA, NSDC, Skill India DBs                 | Company registration, labor skill mapping                    |

---

## 🛠️ Setup Instructions (Local Dev)

```bash
# Clone repo
git clone https://github.com/yourusername/bharat-trade-grid.git
cd bharat-trade-grid

# Create virtual environment
python3 -m venv env
source env/bin/activate

# Install backend dependencies
cd backend
pip install -r requirements.txt

# Start FastAPI backend
uvicorn main:app --reload

# Install frontend dependencies
cd ../frontend
npm install

# Start React frontend
npm run dev
