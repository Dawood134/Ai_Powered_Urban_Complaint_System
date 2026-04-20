# 🏙️ AI-Powered Urban Problem Reporting & Resolution System

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![Status](https://img.shields.io/badge/status-In%20Development-yellow.svg)
![Stack](https://img.shields.io/badge/stack-MERN-green.svg)
![License](https://img.shields.io/badge/license-MIT-orange.svg)

**A smart web-based system that allows citizens to report urban issues and uses AI to classify, prioritize, and route complaints to relevant government departments.**

</div>

---

## 📑 Table of Contents

- [About Project](#-about-project)
- [Team Members](#-team-members)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [API Endpoints](#-api-endpoints)
- [Database Collections](#-database-collections)
- [Getting Started](#-getting-started)
- [Development Phases](#-development-phases)
- [Module Division](#-module-division)

---

## 🎯 About Project

Ye system citizens ko urban issues jaise **potholes, water leakage, broken street lights** etc. report karne ki facility deta hai.

### ✨ Key Features

```
✅ User Registration & Authentication
✅ Urban Issue Reporting (Text + Image)
✅ AI-Based Issue Classification (Phase 2)
✅ Auto Priority Detection (Phase 2)
✅ Auto Department Routing (Phase 2)
✅ Real-time Complaint Tracking
✅ Officer & Admin Dashboard
✅ Analytics & Reports
✅ Feedback System
```

---

## 👥 Team Members

| Member | Role | Modules |
|--------|------|---------|
| Member 1 | Full Stack | Auth + Complaint Submission |
| Member 2 | Full Stack | Tracking + Department + Feedback |
| Member 3 | Full Stack | Admin Dashboard + Analytics |

---

## 🛠️ Tech Stack

```
Frontend    →  React.js (Vite)
Backend     →  Node.js + Express.js
Database    →  MongoDB (Mongoose)
AI Engine   →  Python + Django REST - Phase 2
Image Store →  Cloudinary
Auth        →  JWT (JSON Web Tokens)
```

---

## 📁 Project Structure

```
urban-problem-system/
│
├── 📁 frontend/                         (React - Vite)
│   ├── public/
│   └── src/
│       │
│       ├── 📁 pages/
│       │   │
│       │   ├── 📁 Auth/                 → Member 1
│       │   │   ├── Login.jsx
│       │   │   └── Register.jsx
│       │   │
│       │   ├── 📁 Complaints/           → Member 1
│       │   │   ├── SubmitComplaint.jsx
│       │   │   └── MyComplaints.jsx
│       │   │
│       │   ├── 📁 Tracking/             → Member 2
│       │   │   ├── TrackComplaint.jsx
│       │   │   └── ComplaintDetail.jsx
│       │   │
│       │   ├── 📁 Officer/              → Member 2
│       │   │   ├── OfficerDashboard.jsx
│       │   │   └── UpdateStatus.jsx
│       │   │
│       │   ├── 📁 Feedback/             → Member 2
│       │   │   └── FeedbackForm.jsx
│       │   │
│       │   └── 📁 Admin/                → Member 3
│       │       ├── AdminDashboard.jsx
│       │       ├── AllComplaints.jsx
│       │       ├── Analytics.jsx
│       │       └── ManageUsers.jsx
│       │
│       ├── 📁 components/               → All Members
│       │   ├── Navbar.jsx
│       │   ├── Sidebar.jsx
│       │   ├── ComplaintCard.jsx
│       │   └── ProtectedRoute.jsx
│       │
│       ├── 📁 context/
│       │   └── AuthContext.jsx          → Member 1
│       │
│       ├── 📁 services/
│       │   ├── authService.js           → Member 1
│       │   ├── complaintService.js      → Member 1
│       │   ├── trackingService.js       → Member 2
│       │   └── adminService.js          → Member 3
│       │
│       └── App.jsx
│
├── 📁 backend/                          (Node.js + Express)
│   │
│   ├── 📁 config/
│   │   └── db.js                        → All Members
│   │
│   ├── 📁 models/
│   │   ├── User.model.js                → Member 1
│   │   ├── Complaint.model.js           → Member 1
│   │   ├── Department.model.js          → Member 2
│   │   ├── Assignment.model.js          → Member 2
│   │   ├── StatusHistory.model.js       → Member 2
│   │   ├── Feedback.model.js            → Member 2
│   │   └── AdminLog.model.js            → Member 3
│   │
│   ├── 📁 routes/
│   │   ├── auth.routes.js               → Member 1
│   │   ├── complaint.routes.js          → Member 1
│   │   ├── tracking.routes.js           → Member 2
│   │   ├── department.routes.js         → Member 2
│   │   ├── feedback.routes.js           → Member 2
│   │   └── admin.routes.js              → Member 3
│   │
│   ├── 📁 controllers/
│   │   ├── auth.controller.js           → Member 1
│   │   ├── complaint.controller.js      → Member 1
│   │   ├── tracking.controller.js       → Member 2
│   │   ├── department.controller.js     → Member 2
│   │   ├── feedback.controller.js       → Member 2
│   │   └── admin.controller.js          → Member 3
│   │
│   ├── 📁 middleware/
│   │   ├── auth.middleware.js           → Member 1
│   │   └── role.middleware.js           → Member 1
│   │
│   └── server.js                        → All Members
│
└── 📁 ai_engine/                        (Phase 2 - Django REST)
    │
    ├── 📁 ai_project/                   (Django Main Config)
    │   ├── __init__.py
    │   ├── settings.py
    │   ├── urls.py
    │   └── wsgi.py
    │
    ├── 📁 classifier/                   → Member 1
    │   ├── migrations/
    │   ├── __init__.py
    │   ├── apps.py
    │   ├── views.py
    │   ├── urls.py
    │   └── text_classifier.py
    │
    ├── 📁 routing/                      → Member 2
    │   ├── migrations/
    │   ├── __init__.py
    │   ├── apps.py
    │   ├── views.py
    │   ├── urls.py
    │   └── auto_routing.py
    │
    ├── 📁 priority/                     → Member 3
    │   ├── migrations/
    │   ├── __init__.py
    │   ├── apps.py
    │   ├── views.py
    │   ├── urls.py
    │   └── priority_detector.py
    │
    ├── manage.py
    └── requirements.txt
```

---

## 🔗 API Endpoints

### 👤 Auth Routes — `Member 1`

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | New user register |
| POST | `/api/auth/login` | User login + JWT token |
| POST | `/api/auth/logout` | User logout |
| GET | `/api/auth/me` | Get current user info |

### 📋 Complaint Routes — `Member 1`

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/complaints/submit` | Submit new complaint |
| GET | `/api/complaints/my` | Get my complaints |
| GET | `/api/complaints/:id` | Get single complaint |
| PUT | `/api/complaints/:id` | Update complaint |

### 📍 Tracking Routes — `Member 2`

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/tracking/:complaintId` | Track complaint status |
| POST | `/api/tracking/update-status` | Update complaint status |

### 🏢 Department Routes — `Member 2`

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/departments/all` | Get all departments |
| POST | `/api/departments/assign` | Assign complaint to dept |

### ⭐ Feedback Routes — `Member 2`

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/feedback/submit` | Submit feedback |
| GET | `/api/feedback/:complaintId` | Get complaint feedback |

### 🔧 Admin Routes — `Member 3`

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/admin/complaints/all` | Get all complaints |
| GET | `/api/admin/complaints/filter` | Filter complaints |
| PUT | `/api/admin/complaints/priority` | Set priority manually |
| GET | `/api/admin/analytics/summary` | Analytics summary |
| GET | `/api/admin/analytics/reports` | Generate reports |

---

## 🗄️ Database Collections

```
📦 MongoDB Collections:

├── 👤 users              →  User accounts & roles
├── 📋 complaints         →  Submitted complaints
├── 🏢 departments        →  Government departments
├── 🔗 assignments        →  Complaint-Department mapping
├── 📊 statushistories    →  Status change history
├── ⭐ feedbacks          →  User ratings & comments
└── 📝 adminlogs          →  Admin activity logs
```

---

## 🚀 Getting Started

### ✅ Prerequisites

```
Node.js     v18+
npm         v9+
MongoDB     Atlas Account (Free)
Git         Latest
Python      3.10+ (Phase 2 only)
```

---

### 📥 Step 1 — Clone Repository

```bash
git clone https://github.com/your-username/urban-problem-system.git
cd urban-problem-system
```

---

### ⚙️ Step 2 — Backend Setup

```bash
# Backend folder mein jao
cd backend

# Dependencies install karo
npm init -y
npm install express mongoose dotenv bcryptjs jsonwebtoken cors multer
npm install --save-dev nodemon
```

**Backend `.env` File**

```env
PORT=5000
MONGO_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net/urbandb
JWT_SECRET=your_super_secret_key_here
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
```

**Backend `package.json` Scripts**

```json
{
  "scripts": {
    "start": "node server.js",
    "dev": "nodemon server.js"
  }
}
```

**Backend Start**

```bash
npm run dev
# Server running on → http://localhost:5000
```

---

### 🎨 Step 3 — Frontend Setup

```bash
# Frontend folder mein jao
cd frontend

# React app create karo (Vite)
npm create vite@latest . -- --template react

# Dependencies install karo
npm install
npm install axios react-router-dom
npm install react-toastify chart.js react-chartjs-2
```

**Frontend `.env` File**

```env
VITE_API_BASE_URL=http://localhost:5000/api
```

**Frontend Start**

```bash
npm run dev
# App running on → http://localhost:5173
```

---

### 🤖 Step 4 — AI Engine Setup `(Phase 2)`

```bash
# AI Engine folder mein jao
cd ai_engine

# Virtual environment banao
python -m venv venv

# Activate karo (Windows)
venv\Scripts\activate

# Activate karo (Mac/Linux)
source venv/bin/activate

# Dependencies install karo
pip install django djangorestframework
pip install scikit-learn pandas numpy
pip install transformers torch
pip install pillow requests
pip install django-cors-headers

# requirements.txt mein save karo
pip freeze > requirements.txt

# Database migrate karo
python manage.py migrate

# Django AI Server start karo
python manage.py runserver 8000
# AI running on → http://localhost:8000
```

**AI Engine `.env` File**

```env
DEBUG=True
SECRET_KEY=your_django_secret_key
ALLOWED_HOSTS=localhost,127.0.0.1
```

---

## 📅 Development Phases

### 🔵 Phase 1 — Manual System `(Week 1 - Week 8)`

| Week | Task | Members |
|------|------|---------|
| Week 1-2 | Project Setup + DB Design | All |
| Week 3-4 | Auth + Complaint + Department Base | All |
| Week 5-6 | Tracking + Feedback + Admin Panel | All |
| Week 7-8 | Integration + Testing + Bug Fixes | All |

### 🟢 Phase 2 — AI Integration `(Week 9 - Week 14)`

| Week | Task | Members |
|------|------|---------|
| Week 9-10 | NLP Text Classifier + Auto Routing | M1 + M2 |
| Week 11-12 | Image Analysis + Priority Detection | M1 + M3 |
| Week 13-14 | Final Integration + Presentation | All |

---

## 👨‍💻 Module Division

### 👤 Member 1 — Auth & Complaint Module

```
Backend:
  ├── User.model.js
  ├── Complaint.model.js
  ├── auth.routes.js + auth.controller.js
  ├── complaint.routes.js + complaint.controller.js
  ├── auth.middleware.js + role.middleware.js
  └── AuthContext.jsx

Frontend:
  ├── Login.jsx
  ├── Register.jsx
  ├── SubmitComplaint.jsx
  ├── MyComplaints.jsx
  ├── authService.js
  └── complaintService.js

AI - Phase 2 (Django):
  └── classifier/ app
```

---

### 🔄 Member 2 — Tracking, Department & Feedback Module

```
Backend:
  ├── Department.model.js
  ├── Assignment.model.js
  ├── StatusHistory.model.js
  ├── Feedback.model.js
  ├── tracking.routes.js + tracking.controller.js
  ├── department.routes.js + department.controller.js
  └── feedback.routes.js + feedback.controller.js

Frontend:
  ├── TrackComplaint.jsx
  ├── ComplaintDetail.jsx
  ├── OfficerDashboard.jsx
  ├── UpdateStatus.jsx
  ├── FeedbackForm.jsx
  └── trackingService.js

AI - Phase 2 (Django):
  └── routing/ app
```

---

### 📊 Member 3 — Admin Dashboard & Analytics Module

```
Backend:
  ├── AdminLog.model.js
  ├── admin.routes.js
  └── admin.controller.js

Frontend:
  ├── AdminDashboard.jsx
  ├── AllComplaints.jsx
  ├── Analytics.jsx
  ├── ManageUsers.jsx
  └── adminService.js

AI - Phase 2 (Django):
  └── priority/ app
```

---

## 🤝 Git Workflow

```bash
# Apni branch banao
git checkout -b feature/member1-auth

# Kaam karo, phir commit karo
git add .
git commit -m "feat: add user registration API"

# Push karo
git push origin feature/member1-auth

# Pull Request banao → main branch mein merge karo
```

### 🌿 Branch Names

| Member | Branch Names |
|--------|-------------|
| Member 1 | `feature/member1-auth` `feature/member1-complaints` |
| Member 2 | `feature/member2-tracking` `feature/member2-feedback` |
| Member 3 | `feature/member3-admin` `feature/member3-analytics` |

---

<div align="center">

**Built with ❤️ by Team — Final Year Project**

*Pehle Manual, Phir Smart* 🚀

</div>
