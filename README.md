# ImpactLens – NGO Impact Reporting Copilot

**ImpactLens** is an AI-powered platform that helps NGOs transform raw field data—such as beneficiaries, funding, demographics, and geographical reach—into professional, donor-ready impact reports.

It combines automated KPI extraction, interactive data visualization, AI-powered storytelling, and PDF report generation into a single workflow.

---

## ✨ Features

### 📊 Automated KPI Extraction

Upload raw **CSV or Excel datasets** and automatically extract important impact metrics, including:

- Total beneficiaries
- Funds utilized
- Cost per beneficiary
- Gender distribution
- Geographical reach
- Resource allocation
- Other relevant program KPIs

### 📈 Interactive Storytelling Dashboard

Explore your organization's impact through a responsive dashboard featuring:

- Interactive charts and visualizations
- Geographical reach analysis
- Resource allocation trends
- KPI summary cards
- Light and Dark mode
- Responsive design for different screen sizes

### 🤖 AI Report Generator

Generate complete, donor-ready impact reports using **Groq LLaMA 3.3**.

Reports are generated across **8 structured sections** and can be customized based on the intended audience:

- **Formal** – Professional and data-focused
- **Concise** – Short and executive-friendly
- **Storyline** – Narrative-driven and impact-focused

### 📄 PDF Export

Export the generated impact report as a professionally formatted PDF containing:

- KPI summary tables
- Key impact metrics
- AI-generated narrative
- Program insights
- Donor-ready formatting

---

## 🏗️ Architecture

```text
                    ┌─────────────────────┐
                    │       User          │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Next.js Frontend  │
                    │                     │
                    │ • Dashboard         │
                    │ • Data Upload       │
                    │ • Visualizations    │
                    │ • Report Generation │
                    └──────────┬──────────┘
                               │
                               │ REST API
                               ▼
                    ┌─────────────────────┐
                    │    FastAPI Backend  │
                    │                     │
                    │ • Data Processing   │
                    │ • KPI Extraction    │
                    │ • AI Integration    │
                    │ • PDF Generation    │
                    └──────┬───────┬──────┘
                           │       │
                ┌──────────┘       └──────────┐
                ▼                             ▼
       ┌────────────────┐            ┌────────────────┐
       │    MongoDB     │            │   Groq LLaMA   │
       │                │            │      3.3       │
       │ Application    │            │ AI Reporting   │
       │ Data           │            │                │
       └────────────────┘            └────────────────┘
```

---

## 🛠️ Tech Stack

### Frontend

- [Next.js](https://nextjs.org/) – React framework
- React
- [Tailwind CSS](https://tailwindcss.com/) – Styling
- [Recharts](https://recharts.org/) – Data visualization
- [Lucide React](https://lucide.dev/) – Icons

### Backend

- [FastAPI](https://fastapi.tiangolo.com/) – REST API
- Python
- [Motor](https://motor.readthedocs.io/) – Async MongoDB driver
- [Groq](https://groq.com/) – AI inference
- [Pandas](https://pandas.pydata.org/) – Data processing
- [ReportLab](https://www.reportlab.com/) – PDF generation

### Database

- [MongoDB](https://www.mongodb.com/)

---

## 📁 Project Structure

```text
Ngo-impact-copilot/
│
├── backend/
│   ├── app/
│   │   ├── main.py
│   │   └── ...
│   ├── requirements.txt
│   └── ...
│
├── frontend/
│   ├── app/
│   ├── components/
│   ├── public/
│   ├── package.json
│   └── ...
│
├── .gitignore
└── README.md
```

> The exact structure may vary depending on the current implementation.

---

# 🚀 Getting Started

Follow the steps below to run ImpactLens locally.

## Prerequisites

Make sure you have the following installed:

- **Python 3.10+**
- **Node.js 18+**
- **npm**
- **MongoDB** – local instance or MongoDB Atlas
- **Groq API key**

---

## 1. Clone the Repository

```bash
git clone https://github.com/varunkumar3286/Ngo-impact-copilot.git
cd Ngo-impact-copilot
```

---

# 🔧 Backend Setup

Navigate to the backend directory:

```bash
cd backend
```

### Create a Virtual Environment

#### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

#### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Configure Environment Variables

Create a `.env` file inside the `backend` directory:

```env
MONGODB_URL=your_mongodb_connection_string
GROQ_API_KEY=your_groq_api_key
```

Replace the placeholder values with your actual credentials.

### Start the Backend

```bash
uvicorn app.main:app --reload --port 8000
```

The FastAPI backend should now be available at:

```text
http://localhost:8000
```

FastAPI's interactive API documentation is available at:

```text
http://localhost:8000/docs
```

---

# 💻 Frontend Setup

Open another terminal and navigate to the frontend:

```bash
cd frontend
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

The frontend will be available at:

```text
http://localhost:3000
```

---

# 🔐 Environment Variables

ImpactLens requires the following backend environment variables:

| Variable | Description | Required |
|---|---|---|
| `MONGODB_URL` | MongoDB connection string | Yes |
| `GROQ_API_KEY` | API key for Groq LLaMA models | Yes |

### Example

```env
MONGODB_URL=mongodb+srv://username:password@cluster.mongodb.net/impactlens
GROQ_API_KEY=your_api_key_here
```

> Never commit your `.env` file or API keys to GitHub.

---

# 📋 How It Works

The typical ImpactLens workflow is:

```text
1. Upload Dataset
       ↓
2. Process Raw Data
       ↓
3. Extract KPIs
       ↓
4. Explore Dashboard
       ↓
5. Select Report Tone
       ↓
6. Generate AI Report
       ↓
7. Review Impact Narrative
       ↓
8. Export PDF
```

### Step 1 — Upload Data

Upload a CSV or Excel file containing your organization's field-level data.

### Step 2 — KPI Extraction

ImpactLens processes the dataset and extracts relevant metrics such as beneficiary counts, funding utilization, demographic ratios, and cost efficiency.

### Step 3 — Explore Your Impact

Use the interactive dashboard to understand program performance and resource allocation.

### Step 4 — Generate the Report

Select your preferred reporting tone and let the AI generate the structured impact narrative.

### Step 5 — Export

Download the completed report as a professionally formatted PDF suitable for sharing with donors and stakeholders.

---

# 📊 Example KPIs

ImpactLens can work with metrics such as:

| KPI | Example |
|---|---:|
| Total Beneficiaries | 12,450 |
| Funds Utilized | ₹25,00,000 |
| Cost per Beneficiary | ₹201 |
| Female Beneficiaries | 58% |
| Male Beneficiaries | 42% |
| Districts Reached | 12 |

*Examples are illustrative.*

---

# 🤖 AI Reporting

ImpactLens uses **Groq LLaMA 3.3** to transform structured program data into readable impact narratives.

The generated report can be adapted to different communication requirements:

### Formal

Best suited for:

- Donor reports
- Institutional stakeholders
- Government submissions
- Annual reports

### Concise

Best suited for:

- Executive summaries
- Leadership updates
- Internal reviews
- Quick donor briefings

### Storyline

Best suited for:

- Impact storytelling
- Campaign communications
- Donor engagement
- Public-facing narratives

---

# 📄 Report Output

Generated reports combine quantitative and qualitative information into a single document.

A typical report includes:

1. Executive Summary
2. Program Overview
3. Beneficiary Impact
4. Geographic Reach
5. Demographic Analysis
6. Resource Utilization
7. Key Outcomes & Insights
8. Conclusion & Impact Narrative

---

# 🔮 Future Improvements

Potential future enhancements include:

- Multi-language report generation
- Additional AI models
- Advanced geographic mapping
- Automated donor-specific report templates
- Historical impact comparisons
- Year-over-year analytics
- Organization-level user accounts
- Role-based access control
- Cloud deployment
- Automated email delivery
- Additional file formats
- Custom NGO branding and logos

---

# 🤝 Contributing

Contributions, issues, and feature requests are welcome.

### 1. Fork the repository

```bash
git clone https://github.com/varunkumar3286/Ngo-impact-copilot.git
```

### 2. Create a feature branch

```bash
git checkout -b feature/your-feature-name
```

### 3. Commit your changes

```bash
git commit -m "Add your feature"
```

### 4. Push your branch

```bash
git push origin feature/your-feature-name
```

### 5. Open a Pull Request

Please provide a clear description of the changes and their purpose.

---

# 👨‍💻 Contributors

- **Varun Kumar** — Project Contributor

---

# 📌 Project Links

- **Repository:** https://github.com/varunkumar3286/Ngo-impact-copilot
- **Releases:** https://github.com/varunkumar3286/Ngo-impact-copilot/releases
- **Contributors:** https://github.com/varunkumar3286/Ngo-impact-copilot/graphs/contributors

---

# 📜 License

Add your project's license information here.

If this project is intended to be open source, consider adding a `LICENSE` file to the repository and updating this section accordingly.

---

## 🌍 ImpactLens

**Turning NGO data into measurable impact, meaningful stories, and donor-ready reports.**
