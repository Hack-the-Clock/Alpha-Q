

## 🏆 Challenge Track
**AI-Powered Innovation in Human Resources & Career Development**

---

## 📋 Problem Statement and Summary

### **The Problem**
- **60% of candidates exaggerate** on resumes, making traditional screening unreliable
- **HR teams miss critical signals** - body language, voice patterns, and emotional cues that reveal true potential
- **Rejected candidates receive generic feedback** with no actionable path to improvement
- **Soft skills are hard to measure** objectively, leading to subjective and potentially biased hiring decisions

### **Our Solution**
VentureView HR is a dual-portal AI-powered platform that revolutionizes hiring by analyzing **verbal, non-verbal, and cognitive signals** to create holistic candidate profiles.

**For Candidates:**
- AI-powered resume optimization with ATS scoring
- Smart job matching based on skills and experience
- Multi-stage assessments (Coding → Technical Interview → HR Interview)
- Personalized career roadmaps and skill development courses
- Detailed, actionable feedback on rejections

**For HR/Recruiters:**
- Multi-modal interview analysis dashboard
- Real-time emotion detection and confidence scoring
- Voice pattern analysis (pitch, tone, stress indicators)
- Gaze tracking for engagement measurement
- Comparative candidate scoring with bias detection
- Automated feedback generation

**Key Innovation:** We decode the **unspoken side** of interviews through:
- 😊 **Facial Expression Analysis** - Confidence, nervousness, authenticity detection
- 🎤 **Voice Analysis** - Pitch variation, speaking pace, stress patterns
- 👁️ **Gaze Tracking** - Eye contact as a proxy for engagement
- 💬 **Answer Evaluation** - Technical depth, clarity, and structure using LLMs

---

## 🛠️ Tech Stack and AI Tools Used

### **Frontend**
- **Next.js 14+** (React App Router)
- **Tailwind CSS** + **Shadcn UI** (Component library)
- **Recharts** (Data visualization)
- **MediaRecorder API** / **Daily.co SDK** (Video recording)
- **WebGazer.js** (Gaze tracking)

### **Backend**
- **Django 5.0** + **Django REST Framework**
- **PostgreSQL** (Database)
- **Celery** + **Redis** (Task queue for video processing)
- **AWS S3** / **Cloudinary** (Video and resume storage)

### **AI/ML Tools**
| Tool | Purpose |
|------|---------|
| **Claude Sonnet 4.5** | Technical answer evaluation, resume analysis, question generation |
| **Gemini API** | Resume parsing and optimization suggestions |
| **AssemblyAI** / **Deepgram** | Speech-to-text transcription with high accuracy |
| **Hume AI** | Facial emotion detection and voice analysis (prosody, stress) |
| **WebGazer.js** | Real-time eye tracking and gaze pattern analysis |
| **Judge0 API** | Coding challenge execution and evaluation |

### **Third-Party Integrations**
- **RapidAPI JSearch** / **Adzuna API** (Job listing aggregation)
- **SendGrid** / **Resend** (Email automation)
- **Roadmap.sh** (Career path generation)

---

## 🎥 Demo Link

**[Watch Our 2-Minute Demo Video](https://www.youtube.com/watch?v=YOUR_VIDEO_ID)**  
*Showcasing the complete candidate journey from resume upload to multi-modal interview analysis*

---

## 👥 Team Members

| Name | Email | Role |
|------|-------|------|
| **Kevin Doshi** | yourname@email.com | Full Stack Developer |
| **Kunj Pandya** | member2@email.com | AI/ML Engineer |
| **Mandar Bavdani** | member3@email.com | UI/UX Designer |

---

## 🚀 Setup / Run Instructions

### **Prerequisites**
- Node.js 18+ and npm
- Python 3.11+
- PostgreSQL 14+
- Redis

---

### **Backend Setup (Django)**

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/ventureview-hr.git
   cd ventureview-hr/backend
   ```

2. **Create and activate virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up environment variables**
   ```bash
   cp .env.example .env
   ```
   
   Edit `.env` with your API keys:
   ```env
   # Django
   SECRET_KEY=your_django_secret_key
   DEBUG=True
   
   # Database
   DATABASE_URL=postgresql://user:password@localhost:5432/ventureview
   
   # AI Services
   CLAUDE_API_KEY=your_claude_api_key
   GEMINI_API_KEY=your_gemini_api_key
   ASSEMBLYAI_API_KEY=your_assemblyai_key
   HUME_API_KEY=your_hume_ai_key
   
   # Storage
   AWS_ACCESS_KEY_ID=your_aws_key
   AWS_SECRET_ACCESS_KEY=your_aws_secret
   AWS_STORAGE_BUCKET_NAME=your_bucket_name
   
   # Other APIs
   SENDGRID_API_KEY=your_sendgrid_key
   JUDGE0_API_KEY=your_judge0_key
   RAPID_API_KEY=your_rapidapi_key
   ```

5. **Run database migrations**
   ```bash
   python manage.py migrate
   ```

6. **Create superuser (optional)**
   ```bash
   python manage.py createsuperuser
   ```

7. **Start Redis (in a separate terminal)**
   ```bash
   redis-server
   ```

8. **Start Celery worker (in a separate terminal)**
   ```bash
   celery -A ventureview worker -l info
   ```

9. **Run the development server**
   ```bash
   python manage.py runserver
   ```
   
   Backend will be available at `http://localhost:8000`

---

### **Frontend Setup (Next.js)**

1. **Navigate to frontend directory**
   ```bash
   cd ../frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   cp .env.local.example .env.local
   ```
   
   Edit `.env.local`:
   ```env
   NEXT_PUBLIC_API_URL=http://localhost:8000/api
   NEXT_PUBLIC_WEBSOCKET_URL=ws://localhost:8000/ws
   NEXT_PUBLIC_DAILY_API_KEY=your_daily_co_key
   ```

4. **Run the development server**
   ```bash
   npm run dev
   ```
   
   Frontend will be available at `http://localhost:3000`

---

### **Quick Start (All Services)**

Run all services together (requires 4 terminal windows):

```bash
# Terminal 1 - Redis
redis-server

# Terminal 2 - Celery
cd backend && celery -A ventureview worker -l info

# Terminal 3 - Django
cd backend && python manage.py runserver

# Terminal 4 - Next.js
cd frontend && npm run dev
```

---

### **Access Points**
- **Frontend (Candidate/HR Portal)**: http://localhost:3000
- **Backend API**: http://localhost:8000/api
- **Django Admin**: http://localhost:8000/admin
- **API Documentation**: http://localhost:8000/api/docs

---

### **Test Accounts**

**Candidate Login:**
- Email: candidate@test.com
- Password: Test@1234

**HR Login:**
- Email: hr@test.com
- Password: Test@1234

---

### **Troubleshooting**

**PostgreSQL Connection Error:**
- Ensure PostgreSQL is running: `sudo service postgresql start`
- Create database: `createdb ventureview`

**Redis Connection Error:**
- Start Redis: `redis-server` or `sudo service redis-server start`

**Port Already in Use:**
- Django: Use `python manage.py runserver 8001`
- Next.js: Use `npm run dev -- -p 3001`

**Missing Dependencies:**
- Backend: `pip install -r requirements.txt`
- Frontend: `rm -rf node_modules && npm install`

---

## 📞 Support

For any setup issues or questions:
- Open an issue on GitHub
- Email: contact@ventureview-hr.com

https://www.loom.com/share/fe80150dd70d45669364ed774293576f