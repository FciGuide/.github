# 🎓 FCI Guide | Damanhour University

**FCI Guide** is a comprehensive mobile application supported by cloud backend services, custom-built for students of the Faculty of Computers and Information at Damanhour University. The application aims to elevate the academic experience by providing an intelligent and interactive ecosystem that merges career guidance, schedule management, academic resources, AI study tools, and interactive 3D campus mapping.

---

## 🚀 Tech Stack

* **Frontend (Mobile App):** React Native (powered by Expo)
* **Backend:** Node.js & Express.js
* **Database:** Relational SQL Database (PostgreSQL / MySQL)
* **Cloud Services:** AWS (EC2, S3, RDS)

---

## 🌟 Key Features

1. **🗺️ Roadmaps & Track Flowcharts**
   * Clear learning paths for major CS fields (AI, Software Engineering, Cybersecurity, Data Science, Web & Mobile Development).
   * Recommended free and paid courses, resources, and topic progressions.

2. **📅 Timetable Creation & Schedule Viewer**
   * Interactive personal schedule builder synced with the university's master timetable.
   * Notifications and reminders for upcoming lectures, halls, and labs.

3. **📚 Academic Materials & Summaries Hub**
   * Centralized resource hub organized by academic year containing lecture slides, section notes, and peer-reviewed summaries.

4. **📝 Question Bank & Exam Simulator**
   * Comprehensive bank of past questions and practice tests for each subject to assist in exam preparation.

5. **🤖 AI-Powered Study Assistant**
   * Intelligent assistant capable of generating subject-specific quizzes, explaining complex concepts, and creating tailored practice exams.

6. **🏛️ Interactive 3D Campus Map**
   * 3D visualization of the faculty campus showcasing lecture halls and labs.
   * Real-time info indicating which lecture is currently taking place, the assigned hall, and the lecturer/doctor in charge.

7. **📢 Official Announcements Channel**
   * A unified feed for official faculty announcements, exam schedules, and urgent updates.

8. **💬 Interactive Chat Groups**
   * Dedicated discussion channels connecting students and faculty members for academic support and peer interaction.

---

## 🏗️ Project Architecture

```text
               +-----------------------------------+
               |     React Native App (Expo)       |
               +-----------------+-----------------+
                                 |
                                 v  (HTTP / WebSockets)
               +-----------------+-----------------+
               |       Node.js / Express API       |
               +--------+----------------+---------+
                        |                |
           +------------+                +------------+
           |                                          |
           v                                          v
+----------+----------+                    +----------+----------+
|  AWS RDS (SQL DB)   |                    |   AWS S3 (Files &   |
|   Users, Schedule   |                    |    3D Assets Hub)  |
+---------------------+                    +---------------------+
```
<p align="center">
  <img src="./assets/fci_guide_erd.svg" alt="FCI Guide ERD" width=100%>
</p>
## 📁 Repository Structure

```text
fci-guide/
├── mobile/                  # React Native Application
│   ├── assets/              # Images, Fonts, 3D Models (.gltf/.glb)
│   ├── src/
│   │   ├── components/      # Shared UI components
│   │   ├── screens/         # App screens (Home, Map, Timetable, etc.)
│   │   ├── navigation/      # React Navigation setup
│   │   ├── services/        # API Request Layer
│   │   └── utils/           # Utility functions
│   └── App.js
│
├── server/                  # Node.js Backend API
│   ├── src/
│   │   ├── config/          # DB & AWS configurations
│   │   ├── controllers/     # Business logic
│   │   ├── routes/          # API endpoints
│   │   ├── middlewares/     # Auth & error handling middlewares
│   │   └── models/          # SQL Database models and queries
│   └── index.js
│
└── README.md
```

---

## 🛠️ Getting Started

### Prerequisites

* [Node.js](https://nodejs.org/) (v18 or higher)
* [Expo CLI](https://docs.expo.dev/get-started/installation/)
* SQL Database instance (MySQL / PostgreSQL)

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/fci-guide.git
cd fci-guide
```

### 2. Backend Setup

```bash
cd server
npm install

# Configure environment variables
cp .env.example .env

# Run database setup scripts/migrations
npm run db:setup

# Start development server
npm run dev
```

### 3. Mobile Setup

```bash
cd ../mobile
npm install

# Start Expo development server
npx expo start
```

---

## ☁️ AWS Cloud Setup

* **AWS EC2:** Hosts the Node.js/Express REST API backend.
* **AWS RDS:** Managed SQL database for secure, high-performance data operations.
* **AWS S3:** Storage bucket for academic PDFs, user media, and 3D map assets.

---

## 👨‍💻 Contributors

* **Mohamed Ellakany** - Full-Stack Developer

---

## 📄 License

This project is developed for the Faculty of Computers and Information - Damanhour University.
