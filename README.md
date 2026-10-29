# 📚 Smart Study Tracking System  
Built using **React + TypeScript (Frontend)** and **Spring Boot + Java (Backend)**  
A complete DSA-based study organizer with priority scheduling, path planning, analytics, and weekly timetable system.

---

# 🚀 Overview

Smart Study Tracker is a productivity web application designed to help students:

- Plan study paths  
- Manage tasks based on priority (Max-Heap)  
- Track study logs  
- Generate weekly timetables  
- Manage unavailable time slots  
- Use undo/redo for actions  
- Visualize subject analytics  

This project also demonstrates multiple **DSA concepts** in a real-world project.

---

# 🧠 Data Structures Used

| Feature | Data Structure | Why Used? |
|--------|----------------|-----------|
| Task Priority | **Max-Heap (PriorityQueue)** | Always pick highest priority task in O(log n) |
| Subject Dependencies | **Directed Graph + Topological Sort (Kahn’s Algorithm)** | Generate correct learning order |
| Time Blocking | **Interval Tree** | Detect overlapping time intervals efficiently |
| Undo / Redo | **Two Stacks** | Reverse or reapply previous actions |
| Weekly Timetable | **Heap Copy + Greedy Algorithm** | Assign best tasks to time slots |

---

# ✨ Key Features

### ✅ Task Management  
- Add tasks  
- Priority score (1–100)  
- Auto-schedule review tasks  
- Complete tasks and log duration  

### ✅ Study Path Planner  
- Add dependencies between subjects  
- Uses **Topological Sort** to generate recommended learning order  

### ✅ Time Blocking  
- Add unavailable time blocks  
- Overlap detection using **Interval Tree**  
- Prevents conflicts  

### ✅ Weekly Timetable Generator (NEW)  
- 7-day plan  
- 3 study slots per day  
- Uses **priority-based task selection**  
- Does NOT modify your actual task queue  

### ✅ Study Analytics  
- Total hours studied per subject  
- Visual progress bars  

### ✅ Undo / Redo  
- Undo task add  
- Undo dependency add  
- Undo task complete  
- Redo all above actions  

---

# 🏗 Project Structure

```
📦 Study Tracker
 ┣ 📂 backend (Spring Boot)
 ┃ ┣ 📂 config
 ┃ ┣ 📂 data.models
 ┃ ┣ 📂 service
 ┃ ┃ ┣ 📂 data_structures
 ┃ ┃ ┣ StudyTrackerService.java
 ┃ ┣ 📂 web (Controllers)
 ┃ ┣ StudyTrackerApplication.java
 ┣ 📂 frontend (React + Vite)
 ┃ ┣ src/pages/Index.tsx
 ┃ ┣ src/components/ui
 ┃ ┣ App.tsx
 ┃ ┣ vite.config.ts
```

---

# 🛠 Backend Setup (Spring Boot)

### 📌 Requirements
- Java 17+
- Maven
- IntelliJ IDEA (recommended)

### ▶️ Start Backend

1. Open IntelliJ  
2. Load the backend folder as a Maven project  
3. Wait for `pom.xml` dependencies to download  
4. Run the main file:

```
src/main/java/com/aditya/Study/Tracker/StudyTrackerApplication.java
```

5. Server starts at:

```
http://localhost:8080
```

You should see:

```
Tomcat started on port 8080
```

---

# 🎨 Frontend Setup (React + Vite)

### 📌 Requirements
- Node.js 18+  
- npm or yarn

### ▶️ Start Frontend

Open terminal inside the frontend folder:

```
cd frontend
npm install
npm run dev
```

The UI opens at:

```
http://localhost:8081
```

---

# 🔗 API Endpoints (Important)

### **Tasks**
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/v1/tasks` | Add new task |
| GET | `/api/v1/tasks/top` | Get highest priority task |
| POST | `/api/v1/tasks/complete` | Complete top task |

### **Logs**
| Method | Endpoint |
|--------|----------|
| POST | `/api/v1/logs` |
| GET | `/api/v1/logs/summary` |

### **Dependencies**
| Method | Endpoint |
|--------|----------|
| POST | `/api/v1/subjects/dependency` |
| GET | `/api/v1/subjects/path` |

### **Time Blocking**
| Method | Endpoint |
|--------|----------|
| POST | `/api/v1/schedule/block` |

### **Weekly Plan**
| Method | Endpoint |
|--------|----------|
| POST | `/api/v1/schedule/weekly-plan` |

---

# 📅 Weekly Timetable Logic (Easy Explanation)

This is inside:

```
StudyTrackerService.java
```

### ✔ How it works

1. Copy the priority queue (Max-Heap)  
2. Loop through 7 days (Mon–Sun)  
3. Each day has 3 slots  
4. For each slot → pick the **highest priority task**  
5. Build result and return to frontend  

### 💡 DSA used:  
- **Heap (Priority Queue)**  
- **Greedy Slot Filling**  

---

# 🧪 Testing

Once both servers run:

### Visit the frontend:
```
http://localhost:8081
```

You can test:

✔ Adding tasks  
✔ Completing tasks  
✔ Adding dependencies  
✔ Weekly plan  
✔ Analytics  
✔ Time-blocking  

---

# 🖼 Screenshots 


<img width="1913" height="798" alt="Screenshot 2025-11-14 023531" src="https://github.com/user-attachments/assets/39001553-e29f-4296-ad3e-8690e6a48f76" />
<img width="1870" height="859" alt="Screenshot 2025-11-14 023651" src="https://github.com/user-attachments/assets/2857af96-0e6b-4b79-9a96-d42d4df24b47" />
<img width="1872" height="851" alt="Screenshot 2025-11-14 030002" src="https://github.com/user-attachments/assets/5eead3bd-5bbe-4a19-8f54-bceead6fd040" />
<img width="1919" height="1079" alt="Screenshot 2025-11-14 040303" src="https://github.com/user-attachments/assets/721d45eb-c3ab-4363-80dd-404cef1bcdbe" />
<img width="1847" height="853" alt="Screenshot 2025-11-14 040356" src="https://github.com/user-attachments/assets/d4cf0c14-9413-44c6-9211-aaa1b258742d" />




---

# 🙌 Author  
**Faizan Khan**  
Smart Study Tracker — DSA-Based Project

---
