# Aero-Engine-Reliability-Hub

🚀 Azure Product Stack for Your Pipeline

🧩 1. Real-Time CRM → AEM Ingestion

Goal: Capture field failure events instantly

<img width="2567" height="1681" alt="mermaid-diagram" src="https://github.com/user-attachments/assets/cbd596e0-58cc-48de-8597-172061f90074" />



Azure Services Used:

Azure Event Hubs → High-throughput event ingestion
Azure Functions → Parse & transform incoming JSON
Azure SQL Database → Store data in AEM

👉 Why:

Handles spikes (engine events can burst)
Serverless = low cost + scalable
🔄 2. MRAC → AEM Integration (NEW CORE PART)

Goal: Bring external/global data into central hub

Azure Services Used:

Azure Data Factory → Scheduled pipelines (delta ingestion)
Azure SQL Database → Source (MRAC) + Target (AEM)
Azure Key Vault → Secure DB credentials

👉 Why:

Reliable batch ingestion
Supports watermark-based incremental loads
🧠 3. AEM Processing & Analyst Layer

Goal: Root Cause analysis + manual updates

Azure Services Used:

Azure App Service → AEM Web Portal
Azure SQL Database → Central data hub
Azure Active Directory → User authentication

👉 Why:

Secure, enterprise-grade access for analysts
Direct CRUD operations on AEM
🔁 4. AEM → MRAC Sync

Goal: Push curated/validated data back to global system

Azure Services Used:

Azure Data Factory → Batch sync pipelines
Azure SQL Database → MRAC storage

👉 Why:

Controlled, scheduled synchronization
Handles merge + upsert logic cleanly
🧪 5. AEM → FEM Distribution

Goal: Provide final dataset for modeling / downstream usage

Azure Services Used:

Azure Data Factory → Data movement
Azure SQL Database or
Azure Data Lake Storage → FEM storage

👉 Why:

Structured DB → reporting
Data Lake → advanced analytics / ML
⚖️ 6. Data Reconciliation & Mismatch Detection

Goal: Ensure consistency across AEM & MRAC

Azure Services Used:

Azure Functions → Recon engine
Azure SQL Database → Store mismatch logs
Azure Monitor → Alerting & logging

👉 Why:

Lightweight compute for comparisons
Real-time alerting when mismatches occur
🔧 7. Override API (Critical System)

Goal: Force sync across all systems (AEM, MRAC, FEM)

Azure Services Used:

Azure Functions → API backend
Azure API Management → Secure API exposure
Azure SQL Database → Transaction updates

👉 Why:

Centralized control
Secure + governed API layer
📊 8. Data Consumption & Visualization

Goal: Enable end users to consume combined or separate datasets

Azure Services Used:

Power BI → Dashboards & reports
Azure Synapse Analytics (optional) → Advanced querying

👉 Why:

Flexible reporting:
Combined view (AEM hub)
MRAC-only view
FEM output

🔐 Security & Governance
Azure Key Vault
Azure Active Directory
📦 Data Lake Layer (Medallion Architecture)
Azure Data Lake Storage
Bronze → Raw
Silver → Clean
Gold → Curated
📈 Monitoring
Azure Monitor
Application Insights

🧠 Final Architecture Summary
Layer	Azure Service
Streaming	Event Hubs
Processing	Functions
Orchestration	Data Factory
Storage	Azure SQL / Data Lake
API	Functions + API Management
UI	App Service
Monitoring	Azure Monitor
Analytics	Power BI
