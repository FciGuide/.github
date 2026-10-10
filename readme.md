# 🎓 FCI Guide | دليل كلية الحاسبات والمعلومات - جامعة دمنهور

**FCI Guide** هو تطبيق موبايل متكامل مع خدمات خلفية سحابية، تم تصميمه خصيصاً لمساعدة طلاب كلية الحاسبات والمعلومات بجامعة دمنهور. يهدف التطبيق إلى تحسين التجربة الأكاديمية عبر توفير بيئة ذكية وتفاعلية تجمع بين التوجيه المهني، تنظيم الأوقات، المواد الدراسية، الذكاء الاصطناعي، والخرائط ثلاثية الأبعاد.

---

## 🚀 Tech Stack (التقنيات المستخدمة)

*   **Frontend (Mobile App):** React Native (مع Expo)
*   **Backend:** Node.js & Express.js
*   **Database:** SQL Database (PostgreSQL / MySQL)
*   **Cloud Services:** AWS (EC2, S3, RDS)

---

## 🌟 Key Features (أبرز المميزات)

1. **🗺️ Roadmaps & Track Flowcharts**
   * مسارات تعليمية واضحة لمختلف تخصصات الحاسبات (AI, Software Engineering, Cyber Security, Data Science, Web, Mobile).
   * ترشيحات لأفضل الكورسات والمصادر المجانية والمدفوعة.

2. **📅 Timetable Creation & View**
   * إنشاء جدول دراسي شخصي تفاعلي وتنسيقه مع الجدول الدراسي العام.
   * التنبيه بمواعيد المحاضرات والأماكن.

3. **📚 College Materials & Summaries**
   * مكتبة شاملة لكل فرقة دراسية تحتوي على المحاضرات، السكاشن، والملخصات الموثوقة.

4. **📝 Question Bank & Exam Simulator**
   * بنك أسئلة شامل لكل مادة مع اختبارات تجريبية لتسهيل مراجعة الامتحانات.

5. **🤖 AI Study Assistant**
   * مساعد ذكي يولد أسئلة تلائم المنهج، ينشئ اختبارات قصيرة، ويساعد الطلاب في فهم النقاط المعقدة.

6. **🏛️ Interactive 3D Campus Map**
   * خريطة 3D تفاعلية لمبنى الكلية توضح القاعات والمدرجات.
   * إمكانية معرفة المحاضرة القائمة الآن، القاعة المقامة فيها، واسم المحاضر/الدكتور.

7. **📢 Official Announcements**
   * لوحة إعلانات موحدة للأخبار الرسمية للكلية، جداول الامتحانات، والتنبيهات الهامة.

8. **💬 Interactive Chat Groups**
   * مجموعات تواصل متخصصة تجمع الطلاب وأعضاء هيئة التدريس لمناقشة المواد الدراسية.

---

## 🏗️ Project Architecture (معمارية المشروع)

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

---

## 📁 Repository Structure (هيكلة المشروع)

```text
fci-guide/
├── mobile/                  # React Native Application
│   ├── assets/              # Images, Fonts, 3D Models (.gltf/.glb)
│   ├── src/
│   │   ├── components/      # Shared components
│   │   ├── screens/         # App screens (Home, Map, Timetable, etc.)
│   │   ├── navigation/      # React Navigation setup
│   │   ├── services/        # API Request Layer
│   │   └── utils/           # Helper functions
│   └── App.js
│
├── server/                  # Node.js Backend API
│   ├── src/
│   │   ├── config/          # DB & AWS configuration
│   │   ├── controllers/     # Business Logic
│   │   ├── routes/          # API Routes
│   │   ├── middlewares/     # Auth & Error middlewares
│   │   └── models/          # SQL Database Models / Queries
│   └── index.js
│
└── README.md
```

---

## 🛠️ Getting Started (التشغيل المحلي)

### Prerequisites (المتطلبات الأساسية)
* [Node.js](https://nodejs.org/) (v18 or higher)
* [Expo CLI](https://docs.expo.dev/get-started/installation/)
* SQL Database (MySQL / PostgreSQL)

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/fci-guide.git
cd fci-guide
```

### 2. Backend Setup
```bash
cd server
npm install

# Create environment file
cp .env.example .env

# Run database migrations / scripts
npm run db:setup

# Start server
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

## ☁️ AWS Cloud Services Setup
* **AWS EC2:** استضافة سيرفر الـ Node.js Backend.
* **AWS RDS:** تشغيل قاعدة بيانات SQL بحماية وأداء مرتفع.
* **AWS S3:** تخزين الملفات الحجمها كبير مثل الملخصات وتصاميم الخريطة الـ 3D.

---

## 👨‍💻 Contributors (فريق العمل)
* **محمد اللقاني (Mohamed Ellakany)** - Full-Stack Developer

---

## 📄 License
هذا المشروع خاص بكلية الحاسبات والمعلومات - جامعة دمنهور.