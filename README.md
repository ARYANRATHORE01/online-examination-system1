# 🧠 Online Examination System

A Spring Boot–based application for managing online exams — built as part of my learning journey with **Spring Boot** and **Spring Security**.  
This project demonstrates **exam creation**, **question management**, **authentication**, and **result processing** — all using a simple RESTful backend and an **H2 in-memory database**.

---

## 🚀 Features

- **Create exams** with multiple-choice questions  
- **Submit answers** and auto-calculate results  
- **View all exams and results** through REST API endpoints  
- **Spring Security authentication** (in-memory users)  
- **H2 Console** for database inspection and manual data insertion  

---

## 🧩 Tech Stack

| Layer | Technology |
|-------|-------------|
| Language | Java 21 |
| Framework | Spring Boot 3 |
| Database | H2 (In-memory) |
| Security | Spring Security |
| ORM | Spring Data JPA |
| IDE | IntelliJ IDEA |

---

## 📁 Project Structure

src/

├── main/

│ ├── java/com/example/exam

│ │ ├── controller/

│ │ ├── entity/

│ │ ├── repository/

│ │ └── service/

│ └── resources/

│ ├── application.properties

│ └── data.sql

└── test/

yaml
Copy code

---

## ⚙️ How to Run Locally

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/aryanrathore01/online-examination-system.git
cd online-examination-system
2️⃣ Run the Application
From terminal:

bash
Copy code
./mvnw spring-boot:run
Or, in IntelliJ IDEA, run:
ExamApplication.java

By default, the app runs on port 9999.
You can change this in application.properties.

🔗 Useful URLs
Resource	URL
API Root	http://localhost:9999/exams
H2 Console	http://localhost:9999/h2-console
JDBC URL	jdbc:h2:mem:testdb
Username	sa
Password	(leave blank)

🔐 Default Login (Spring Security)
Username	Password
user	password

🧾 Example API Endpoints
Method	Endpoint	Description
GET	/exams	List all exams with questions
POST	/exams	Create a new exam (JSON body)
POST	/exams/{id}/submit	Submit answers and save result
GET	/exams/results	View all exam results

🧠 Example: Submit Exam (POST)
json
Copy code
{
  "username": "aryan",
  "answers": [
    { "questionId": 1, "answer": "extends" },
    { "questionId": 2, "answer": "main()" }
  ]
}
💾 Demo SQL for H2 Console
sql
Copy code
INSERT INTO EXAM (title) VALUES ('Java Basics Exam');

INSERT INTO QUESTION (text, optionA, optionB, optionC, optionD, correct_answer, exam_id)
VALUES ('Which keyword is used to inherit a class in Java?', 'this', 'super', 'extends', 'import', 'extends', 1);

INSERT INTO RESULT (username, exam_id, score)
VALUES ('aryan', 1, 2);
1️⃣ Exam API Response
(Example JSON Response)

arduino
Copy code
{
  "id": 1,
  "title": "Java Basics Exam",
  "questions": [...]
}
2️⃣ H2 Database Console
Manage data easily at http://localhost:9999/h2-console.

🧭 Future Enhancements
Add user registration and role-based access

Support subjective questions and grading

Integrate with MySQL / PostgreSQL

Build a React/Angular frontend

👨‍💻 Author
Aryan Rathore
🌐 GitHub: @aryanrathore01

📜 License
This project is created for learning and demonstration purposes.
Feel free to use, modify, or enhance it for educational or personal projects.
