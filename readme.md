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
[![](https://mermaid.ink/img/pako:eNq1WFtz4jYU_isePZMMJAsJfkt3e5nZzUzbbV86zGiEfTBqZMnVZQMl-e89Ehh8kVOYtDxhzvG5fufTETuSqRxISkB_4qzQrFzohUzw87sBbZJd_eg_XNqE58nPn5s_Gqu5LJKVE4JKVkJEBiXjIvJ7xYx5Vjqna2bWEblWomXO8hKMZWWVZBqYhZwyW8tf_Zf64at1OUgbCd9hVjTkMEp--NyV5lAxbUt81ev05Vtgmgr4Bq1sVkIxmxQVi8bySWVW6f80lEN51GrFM6DSlUvQrTrBxiZLrqLxPOQllxeFU3cLdMmN4Uqadg3a6R7jvgA8XdyEBHIwmeaVRYdRTx-V0wYu8OKRfoZzbwLxlXNL197FeSDwEgMen-1evNXLVjq_KpaXrLogH8utgPf4ol8tnOXQ_6gP70QHIwu9iMuwIhXFKT_VpRXLIw6y5kycG8eQq6Gi1PzEBVCnxZDIbqteLV2Fk50jzSy3HWdnM9FPTIgLWrpmwyy6dFzk-KVrC-lH6SjcsehcYnSG3ubR6H7DNCxbCnhv8b0sxB6V5IECB1uWsy1VK_oM8BSRYpm1pb7gsZNF5j1RfEZbeX_h34B-gcw6fXbqtq7VJdkvFR5hTCbcUJZZ9Brrk9Paj6tVFc_iIHNV_hbIfnGohzRJv2Py6Z2dDNT7V23QP8VOnsDKJgo6TCazlEnzHDmUYFMJhpBscHoTCNyfaE7YbTTN7zes_L9YIsDU6RAZxQPS4dREDoXQhRYb9CKkdTcioYKXDx75x6r3NPpOHqyFsrLnlqN2HGPnsCr1hfutxmBDB3Yw45Ylt2_A8kFK5WQGFy4Dvd4E5GRKWrTTNcKcXceoJUws0wVYGj-vz2bwj2tm6Y9aueodC80QJFueghP6CH6di_gqgngQPcP72ynVPxWXw5k-gjGsOJsQj_FEQIW8DHqAXMq9mx63NJDlATkQ5P5a8vJydaVeTnt-miwINwlbkKhevYP_i9phNe5rNZfaoLtrul6CULIwSOBv6J9COEu9Xm7TAHzGT2QbUT6ujqm_E8BpZa2tHPROq1aK59WQVmMpSHH-15A7gaDhckC_ffr0A-6o71n8rQCaE5cmGkRYYU7lOpY-ktZ-ZTPdy1csNQsMkzMRJOw61JUmlVsKbhra3RjapIzG2dOA6faUp2Em45rHeUzDQJn2ThlLaa2Mjau1N56OZsPGgDqyWlE0gLVvYjP306mXIgVkAstj4vvJ0Fv9uTjiuo3zw7Wl76eDo666nxtcNGPEPtCbJkb72o3-1JgnI1JonpPUagcjUuKVmflHsvNWFsSuEVIL4hkGb5huc5Uz_XSVKYEbPFnIV3y_YvIPpcraBHos1iRdIbzxab8IHv6pOaoEtsXkpSXpLFgg6Y5sSDqZ3F9P57fj6Xw8nt_dze8mI7Il6fh6OpnO5jcfJuPJ9Pbmw2zyOiJ_B6fj67v76f30ZnY3ns3m0-l09voPOJrN9w?type=png)](https://mermaid.live/edit#pako:eNq1WNtu4zYQ_RWBz0lgJysn1lu62wuwG6Dtti-FAYKWxjIbilR52cR18u8d0patC5XaSOsnyzOa65nDobckVwWQjID-xFmpWbXQC5ng53cD2iTb5tF_uLQJL5KfP7d_NFZzWSYrJwSVrIKIDCrGReT3mhnzpHRB18ysI3KtRMec5RUYy6o6yTUwCwVltpG_-i_Nw1frCpA2Er7DrGjI4SL54XNfWkDNtK3wVa8zlG-AaSrgG3SyWQnFbFLWLBrLJ5Vbpf_TUPblUasVz4FKVy1Bd-oEzzZZchWN576ouDwrnKZboCtuDFfSdGvQTfcQ9xng6eMmJFCAyTWvLTqMevqonDZwhheP9BOcexOIr4JbuvYuTgOBlxjw-Oz24q1edtL5VbGiYvUZ-VhuBbzHF_1q4SSH_ke9fyc6GHnoRVyGFakpTvmxLp1YHnCQNWfi1DjGXI0VpeEnLoA6LcZEdlMPaulqnOwCaWa56Tk7mYl-YkKc0dI1G2fRpeOiwC99W0g_SkfhjkXnEqMz9KaIRvcbpmHZUsB7i-9lIfaopAgUONqygm2oWtEngMeIFMusLfUFj50sshiI4jPayfsL_wb0C-TW6ZNTt02tzsl-qfAIYzLhhrLcotdYn5zWflytqnkeB5mri7dA9otDPaRJ-h2Tj-_sZKDevxqD_il28gRWNlHQYTK5pUyap8ihBM-1YAjJFqe3gcD9ieaE3UTT_P6ZVf8XSwSYOh0io3hAOpyayKEQutBhg0GEtOlGJFTw8tEj_1D1gcbQyb21UNX21HI0jmPsHFaloXC31Rhs6MgOZtyy4vYNWN5LqZzM4cxlYNCbgJxcSYt2-kaYs-sYtYSJZboES-Pn9ckM_nHNLP1RK1e_Y6EZg2THU3BCH8CvcxFfZRCPomd8fzum-qficjzTBzCGlScT4iGeCKiQl0GPkEu1czPglhayPCBHgtxdS15eLi_Vy3HPz5IF4SZhCxLVa3bwf1Hbr8ZDrfZSG3S3bddLEEqWBgn8Df1jCCepN8ttFoDP-JFsI8qH1THzdwI4rqyNlb3ecdXK8Lwa02otBRnO_xoKJxA0XI7od0-fYcA99R2LvxVAe-KyRIMIK8yxXIfSR9LarWymf_mKpWaBYXImgoRtj7qypHZLwU1Lux9Dl5TROHscMd2d8izMZFzzMI9ZGCjT3SljKa2VsXG17sbT02zZGFFHVivLFrB2TWznfjz1MqSAXGB5THw_GXtrOBcHXHdxvr-2DP30cNRX93ODi2aM2Ed608boULvVnwbz5IKUmhcks9rBBanwysz8I9l6Kwti1wipBfEMgzdM93xZMP14mSuBGzxZyFd8v2byD6WqxgR6LNckWyG88Wm3CO7_qTmoBLbF5KUlWRoskGxLnkk2nd5dpfObSTqfTOa3t_Pb6QXZkGxylU7T2fz6w3QyTW-uP8ymrxfk7-B0cnV7l96l17PbyWw2T9N09voPOEjN9g)
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
