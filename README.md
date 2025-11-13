# 📱 StudySmart

A modern Android study-tracking app built with **Kotlin, Jetpack Compose, Room, Hilt**, and a clean MVVM architecture.  
StudySmart helps students organize their subjects, manage tasks, track study sessions, and monitor long-term learning progress with an intuitive dashboard.

---

## 🚀 Features

### 🎯 Subject Management
- Create, edit, and delete subjects  
- Custom gradient colors  
- Set study goal hours  
- Card-based modern UI  

### 📝 Task Management
- Add tasks with title, description, and due dates  
- Mark tasks as complete  
- Upcoming tasks auto-displayed on dashboard  
- State updates fully synced with Room DB  

### ⏱️ Study Session Tracking
- Smart timer with foreground service  
- Accurate session time tracking  
- Handles background/foreground transitions  
- Recent sessions shown with delete support  

### 📊 Dashboard Overview
- Total studied hours  
- Subject count  
- Goal progress  
- Recent sessions  
- Upcoming tasks  
- Clean UI built with Jetpack Compose  

---

### Key features Screen shots
<img width="271" height="585" alt="스크린샷 2025-11-13 오후 8 20 55" src="https://github.com/user-attachments/assets/8affc9ef-e902-42d4-a29d-ec5f05603eca" /><img width="271" height="585" alt="스크린샷 2025-11-13 오후 8 21 06" src="https://github.com/user-attachments/assets/b8a328e6-3c04-4c95-b01a-999281edcbf4" /><img width="271" height="585" alt="스크린샷 2025-11-13 오후 8 21 14" src="https://github.com/user-attachments/assets/86efb809-0376-490d-859a-0c17b755be51" />




## 🏛 Architecture Overview

StudySmart uses a clean and scalable modular structure:

```text
app/
├── data/
│   ├── local/
│   │   ├── AppDatabase.kt
│   │   ├── SubjectDao
│   │   │── SessionDao
│   │   │── TaskDao
│   │   │── ColorListConverter
│   │   
│   │        
│   └── repository/
│       ├── SubjectRepositoryImpl.kt
│       ├── TaskRepositoryImpl.kt
│       └── SessionRepositoryImpl.kt
│
├── domain/
│   ├── model/
│   │   ├── Subject.kt
│   │   ├── Task.kt
│   │   └── Session.kt
│   └── repository/
│       ├── SubjectRepository.kt
│       ├── TaskRepository.kt
│       └── SessionRepository.kt
│
├── presentation/
│   ├── dashboard/
│   ├── subject/
│   ├── task/
│   ├── session/
│   └── components/
│
├── di/
│   ├── DatabaseModule.kt
│   ├── RepositoryModule.kt
│   └── NotificationModule.kt
│
├── util/
       └── StudySmartApp.kt
       └── MainActivity.kt


```
---

## 🔌 Key Dependencies

Core libraries used in this project:

- androidx.compose.material3

- androidx.navigation.compose

- com.google.dagger:hilt-android

---

## 🚀 Getting Started

### Prerequisites
- Android Studio (Koala / Iguana or newer)
- JDK 17+
- Android device or emulator (API 24+ recommended)

### Run the App

Clone the repository:

```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
```

Open the project in **Android Studio**  
Sync Gradle  
Run the `app` module on an emulator or physical device  


---

## 🏗 Architecture Overview

The app follows a layered approach:

### **data/**
- Local persistence using Room  
  - `AppDatabase`  
  - DAOs (SubjectDao, TaskDao, SessionDao)  
  - Converters (ColorListConverter)  
- Repository implementations  
  - `SubjectRepositoryImpl`  
  - `TaskRepositoryImpl`  
  - `SessionRepositoryImpl`

### **domain/**
- Plain Kotlin data models (`Subject`, `Task`, `Session`)
- Repository interfaces to isolate UI from data layer

### **presentation/**
- Jetpack Compose UI for dashboard, subjects, tasks, sessions
- Shared UI elements inside `components/`
- ViewModels for each feature package

### **di/**
Hilt modules for dependency injection:
- `DatabaseModule`
- `RepositoryModule`
- `NotificationModule`

### **StudySmartApp.kt**
- Root composable / entry point  
- Sets up navigation graph and global theming  


---

## 🔔 Study Session Timer Service

The study session feature runs on a **foreground service**:

- Timer continues even when app is backgrounded  
- Uses `NotificationChannel` + `NotificationManager`  
- Injected using Hilt for clean architecture  
- Built for long-running study session tracking  


---

## 📌 TODO / Future Improvements

- Add statistics view for total study time per subject
- Add reminders / notifications for upcoming tasks
- Support Pomodoro and other study interval modes
- Improve dark mode styling and contrast adjustments


- androidx.room:room-runtime

- androidx.lifecycle:lifecycle-viewmodel-compose

- io.github.raamcosta.compose-destinations

