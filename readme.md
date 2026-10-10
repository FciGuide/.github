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
## 📊 Database ERD (Entity-Relationship Diagram)

erDiagram
    Users {
        int id PK
        string full_name
        string email
        string password_hash
        string role
        timestamp created_at
    }

    Students {
        int user_id PK, FK
        int department_id FK
        int year_level
        float gpa
    }

    Doctors {
        int user_id PK, FK
        int department_id FK
        string office_number
        text bio
    }

    Admins {
        int user_id PK, FK
        string permissions_level
    }

    Departments {
        int id PK
        string name
        text description
    }

    Courses {
        int id PK
        string code
        string name
        int credit_hours
        int year_level
        int semester
        int department_id FK
    }

    Roadmaps {
        int id PK
        string title
        int department_id FK
    }

    Roadmap_Steps {
        int id PK
        int roadmap_id FK
        int course_id FK
        int step_order
    }

    Materials {
        int id PK
        int course_id FK
        string title
        string file_url
        string file_type
        int uploaded_by FK
        timestamp created_at
    }

    Halls {
        int id PK
        string hall_name
        string building
        int floor
        string coordinates_3d
    }

    Timetables {
        int id PK
        int course_id FK
        int hall_id FK
        int doctor_id FK
        string day_of_week
        string start_time
        string end_time
        int year_level
    }

    Live_Lectures {
        int id PK
        int timetable_id FK
        int hall_id FK
        boolean is_active
        string current_topic
        timestamp updated_at
    }

    Question_Bank {
        int id PK
        int course_id FK
        text question_text
        string options
        string correct_answer
        text explanation
        string difficulty
    }

    Exams {
        int id PK
        int course_id FK
        string title
        int duration_minutes
        int created_by FK
    }

    Exam_Questions {
        int exam_id PK, FK
        int question_id PK, FK
    }

    Exam_Attempts {
        int id PK
        int exam_id FK
        int student_id FK
        float score
        timestamp submitted_at
    }

    Announcements {
        int id PK
        string title
        text content
        int author_id FK
        int target_year_level
        timestamp created_at
    }

    Chat_Groups {
        int id PK
        string name
        int course_id FK
    }

    Group_Members {
        int group_id PK, FK
        int user_id PK, FK
        timestamp joined_at
    }

    Messages {
        int id PK
        int group_id FK
        int sender_id FK
        text message_text
        timestamp sent_at
    }

    Users ||--o| Students : "is a"
    Users ||--o| Doctors : "is a"
    Users ||--o| Admins : "is a"
    Departments ||--o{ Students : belongs_to
    Departments ||--o{ Doctors : belongs_to
    Departments ||--o{ Courses : contains
    Departments ||--o{ Roadmaps : offers
    Courses ||--o{ Materials : has
    Courses ||--o{ Timetables : scheduled_in
    Courses ||--o{ Question_Bank : contains
    Courses ||--o{ Exams : has
    Courses ||--o{ Chat_Groups : relates_to
    Students ||--o{ Materials : uploads
    Doctors ||--o{ Timetables : teaches
    Users ||--o{ Announcements : publishes
    Students ||--o{ Exam_Attempts : takes
    Users ||--o{ Group_Members : joins
    Users ||--o{ Messages : sends
    Halls ||--o{ Timetables : hosts
    Halls ||--o{ Live_Lectures : hosts
    Timetables ||--o{ Live_Lectures : triggers
    Exams ||--o{ Exam_Questions : includes
    Question_Bank ||--o{ Exam_Questions : belongs_to
    Roadmaps ||--o{ Roadmap_Steps : includes
    Courses ||--o{ Roadmap_Steps : part_of
    Chat_Groups ||--o{ Group_Members : has
    Chat_Groups ||--o{ Messages : contains
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
