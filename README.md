# UMAIR ACADEMY — LMS Web Application
### Learn DIT & CIT Online From Home

A modern, responsive, production-ready Learning Management System (LMS) specifically designed for students learning Diploma in Information Technology (DIT) and Certificate in Information Technology (CIT) online from home.

---

## ⚡ Zero Firebase Storage Architecture (100% Free Spark Plan Compatible)
This website **does NOT require Firebase Storage or any paid billing plan**:
- **Videos**: Streamed directly via external YouTube URLs (supporting standard URLs, shortened `youtu.be`, and embed URLs).
- **Study Notes & PDFs**: Accessed via external public URLs (Google Drive shared links, Dropbox public links, or any open web PDF).
- **Images & Course Thumbnails**: Loaded from fast CDN / public image URLs.
- **Certificates**: Generated dynamically via standard HTML/CSS with print/save-as-PDF browser functionality.
- **Data & Auth**: Powered by standard Firebase Authentication and Firestore Database within the free tier.

---

## 🚀 Features

### 1. Public Learning Portal
- **Home Page (`/`)**: Hero section, real-time Firestore metrics, available course cards, curriculum walkthrough, benefits, and FAQ.
- **Courses Catalog (`/courses`)**: Comprehensive list of DIT & CIT courses with syllabus, durations, and levels.
- **Course Detail (`/courses/:courseId`)**: 15 modular units, lesson playlists, and free student enrollment.
- **Certificate Verification (`/verify`)**: Public portal allowing students, employers, and government boards to verify authentic certificates via unique ID.
- **About & Contact (`/about`, `/contact`)**: Mission details, syllabus breakdown, helpline contact, and direct message inquiries.

### 2. Student Experience
- **Authentication (`/login`, `/register`, `/forgot-password`)**: Real Firebase Authentication with input validation, error alerts, and password reset.
- **Student Dashboard (`/dashboard`)**: Enrolled courses, dynamic completion percentage progress bar, completed lessons counter, recent questions, and earned diplomas.
- **Responsive Video Player (`/lessons/:lessonId`)**: YouTube embedded video lecture, summary notes link, next/prev navigation, completion toggle, and private "Ask Instructor a Question" panel.
- **Module MCQ Quizzes (`/quiz/:moduleId`)**: Multiple choice tests, automated grading, explanations, and instant scorecards.
- **Final Examination (`/exam/:examId`)**: Comprehensive end-of-program exam with passing percentage check and automatic certificate conferral.
- **Digital Certificates (`/certificates`)**: Printable and PDF-downloadable diploma with official seal and direct verification URL.

### 3. Administrator Console (`/admin`)
- **Protected Access**: Role-based access control (RBAC).
- **Courses Management**: Create, edit, and delete courses.
- **Module Management**: Add and reorder curriculum modules.
- **Lesson Management**: Add lectures with YouTube URLs and Google Drive PDF notes URLs (no storage fees).
- **MCQ Question Bank**: Add questions with 4 options, correct answer keys, marks, and explanations.
- **Student Q&A Desk**: Review and post instructor answers directly to student lesson queries.
- **Academic Reports**: Instant printable overview of academy performance, enrollment figures, and certificates issued.

---

## 💻 Tech Stack
- **Framework**: React 19 + TypeScript + Vite
- **Styling**: Tailwind CSS
- **Database & Auth**: Firebase Firestore + Firebase Authentication
- **Icons**: Lucide React
- **Celebrations**: Canvas Confetti

---

## 🛠️ Local Development & Setup

### 1. Install Dependencies
```bash
npm install
```

### 2. Configure Firebase Environment Variables
Create or edit your `.env` file:
```env
VITE_FIREBASE_API_KEY="your-api-key"
VITE_FIREBASE_AUTH_DOMAIN="your-app.firebaseapp.com"
VITE_FIREBASE_PROJECT_ID="your-project-id"
VITE_FIREBASE_STORAGE_BUCKET="your-app.appspot.com"
VITE_FIREBASE_MESSAGING_SENDER_ID="1234567890"
VITE_FIREBASE_APP_ID="1:1234567890:web:abcdef12345"
```

### 3. Start Development Server
```bash
npm run dev
```
Open `http://localhost:3000` in your browser.

### 4. Firestore Security Rules
Copy the rules from `firestore.rules` into your Firebase Console -> Firestore Database -> Rules tab and publish.

### 5. Seeding DIT & CIT Curriculum
When you first run the app, the seed service automatically creates:
- **DIT (1 Year Diploma)** with 15 complete modules, sample video lectures, and final exam questions.
- **CIT (6 Months Certificate)** with 15 modules and computer fundamentals lectures.
You can also manually click **"Seed Initial DIT / CIT Syllabus"** anytime inside `/admin`.

---

## 🎓 Verifying Certificates
Each student who scores 60% or higher on the Final Exam receives a unique ID (e.g. `UA-DIT-2026-XXXXXX`).
Anyone can verify this credential by visiting:
```
https://www.umairacademy.com/verify?id=UA-DIT-2026-XXXXXX
```

---

## 🌐 Custom Domain Setup (`www.umairacademy.com` & `www.umair032436.com`)
When deploying this web application with Firebase Hosting or your web server, point your custom domain DNS records:
- **Public Learning Portal**: `www.umairacademy.com`
  - CNAME `www` -> hosting deployment domain
- **Dedicated Admin Portal**: `www.umair032436.com`
  - CNAME `www` -> hosting deployment domain (routes to `/umair032436` or `/admin`)
- **A Records**: For apex domains `umairacademy.com` and `umair032436.com` pointing to your host server IP addresses.
