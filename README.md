🚀 Project Overview
The Real‑Time Reassignment of Audit Instruction system automates the reassignment of field audits when unexpected disruptions occur—such as auditor unavailability, store closures, or incomplete audits.
Instead of planners manually reshuffling assignments, this solution delivers real-time detection, AI-assisted auditor matching, and continuous audit flow, ensuring operational efficiency and high-quality audit planning.

🎯 Key Features
✅ 1. Automatic Disruption Detection

Identifies events such as auditor sick leave, store closure, ownership change, and unfinished audits.
Instantly triggers reassignment workflows.

🤖 2. AI-Powered Auditor Matching
Powered by Python + OpenAI, matching is based on:

Geo-proximity
Auditor workload and capacity
Skills & qualification tags
Historical scheduling patterns

🔄 3. Real-Time Reassignment Engine

Spring Boot backend performs dynamic reassignment.
Maintains audit continuity without losing progress.
Allows planner overrides.

📊 4. Streamlit Dashboard
A user-friendly UI for:

Viewing audit plans
Handling disruption alerts
Approving/rejecting AI suggestions

📡 5. REST API Layer

Full CRUD operations for audits, auditors, assignments.
Tested and validated using Postman.
Webhooks for instant event updates.


🏗️ System Architecture
                         ┌──────────────────────────┐
                         │     Streamlit UI          │
                         │  (Planner Dashboard)      │
                         └─────────────┬────────────┘
                                       │
                         ┌─────────────▼─────────────┐
                         │      Spring Boot API       │
                         │ (Audit + Reassignment Svc) │
                         └─────────────┬─────────────┘
                                       │
                   ┌───────────────────┼───────────────────┐
                   │                   │                   │
┌──────────────────▼──────┐   ┌────────▼────────┐   ┌─────▼────────────────┐
│ PostgreSQL Database      │   │ Python Matching  │   │ Disruption Event Bus │
│ (Audits / Auditors /     │   │ Engine (OpenAI)  │   │ (Triggers + Logs)   │
│ Assignments / Events)    │   └──────────────────┘   └──────────────────────┘
└──────────────────────────┘


📈 Impact & Results
Metric Improvement Manual Effort ↓ 40% Match Accuracy ↑ 30% Audit Continuity 95% uninterrupted operations Planner Efficiency Significant improvement

🧪 Sample API Endpoints
Plain Texthttp isn’t fully supported. Syntax highlighting is based on Plain Text.GET /api/audits/pendingPOST /api/audits/reassignGET /api/auditors/availabilityPOST /api/events/disruptionShow more lines

🛠️ Tech Stack
Backend: Java 17, Spring Boot
AI Engine: Python, OpenAI
Database: PostgreSQL
Frontend / UI: Streamlit
Testing: JUnit, Postman
Deployment: Docker

⚙️ Local Setup
1️⃣ Clone the Repository
Shellgit clone https://github.com/yourusername/audit-reassignment.gitcd audit-reassignmentShow more lines

2️⃣ Backend – Spring Boot
Install & Run:
Shellmvn clean installmvn spring-boot:runShow more lines

3️⃣ AI Engine – Python
Install Dependencies:
Shellpip install -r requirements.txtShow more lines
Run:
Shellpython app.pyShow more lines

4️⃣ Streamlit Dashboard
Shellstreamlit run dashboard.pyShow more lines

🔐 Environment Variables
Create a .env or export the variables:
OPENAI_API_KEY=your_key_here
DB_URL=jdbc:postgresql://localhost:5432/audit
DB_USER=postgres
DB_PASS=your_password


📁 Project Structure (Simplified)
/
├── backend/
│   ├── src/main/java/...
│   ├── src/main/resources/
│   └── pom.xml
│
├── ai-engine/
│   ├── app.py
│   ├── matching.py
│   └── requirements.txt
│
├── ui-dashboard/
│   └── dashboard.py
│
├── postman/
│   └── audit_apis.postman_collection.json
│
└── README.md


🤝 Contributing
Pull requests are welcome!
For major changes, please open an issue first to discuss what you would like to improve.
