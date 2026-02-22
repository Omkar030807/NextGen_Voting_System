# 🗳️ NextGen Voting System

<div align="center">

### A secure web-based college election platform developed using Java Servlets, JSP, and MySQL.

<br/>

![Java](https://img.shields.io/badge/Java-17-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![JSP](https://img.shields.io/badge/JSP-Dynamic%20Web-007396?style=for-the-badge&logo=java&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-Database-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Tomcat](https://img.shields.io/badge/Apache%20Tomcat%2011-Server-F8DC75?style=for-the-badge&logo=apachetomcat&logoColor=black)
![Eclipse](https://img.shields.io/badge/Eclipse%20IDE-Dynamic%20Web%20Project-2C2255?style=for-the-badge&logo=eclipseide&logoColor=white)
![Security](https://img.shields.io/badge/OTP-Verified%20Secure-28a745?style=for-the-badge&logo=shield&logoColor=white)

</div>

---

## 📌 Table of Contents

- About the Project  
- Features  
- Tech Stack  
- Project Structure  
- Database Setup  
- Installation & Setup  
- How It Works  
- Screenshots  
- Contributing  
- License  
- Author  

---

## 📖 About the Project

**NextGen Voting System** is a complete and secure online voting application specially built for **college-level elections**. This platform allows students to register, verify their identity using OTP, log in, and vote for candidates contesting various posts — all within a safe and transparent system.

The project consists of two major modules:

- 🎓 Student Module — Students can register, verify via OTP, log in, and vote securely.  
- 🛠️ Admin Module — Admin manages students, candidates, classes, and controls the election process.  

The main objective of this system is to replace traditional paper-based voting with a secure OTP-based digital voting system that ensures authenticity and prevents tampering.

---

## ✨ Features

### 🎓 Student Features

- Register using College ID, Email, and Password  
- OTP verification during registration  
- Secure login system  
- View candidates for each position  
- Cast vote securely  
- Change/reset password via OTP  
- Forgot password with OTP verification  

### 🛠️ Admin Features

- Secure admin login panel  
- Full election control:
  - Start election  
  - Stop election  
  - Reset election  
- Add/remove candidates  
- Add/manage students  
- Assign students to classes  
- Reset student passwords  
- View real-time vote count  
- View results by post  

### 🔒 Security Features

- OTP verification for sensitive actions  
- OTP-secured registration and login  
- Session-based authentication  
- Admin-only access to controls  

---

## 🛠️ Tech Stack

| Layer | Technology |
|------|-----------|
| Project Type | Dynamic Web Project (Eclipse IDE) |
| Backend | Java 17 — Servlets |
| Frontend | JSP, HTML, CSS, JavaScript |
| Database | MySQL 8+ |
| Server | Apache Tomcat 11 |
| Email / OTP | Jakarta Mail |
| Build | Eclipse Java EE Builder |

### External Libraries (WEB-INF/lib)

- angus-mail-2.0.2.jar  
- jakarta.activation-api-2.1.3.jar  
- jakarta.mail-2.0.1.jar  
- jakarta.mail-api-2.1.3.jar  
- jakarta.servlet-api-6.0.0.jar  
- mysql-connector-j-9.5.0.jar  

This is not a Maven project. All JARs are manually added to WEB-INF/lib.

---

## 📁 Project Structure

Nextgen_Voting_System/
│
├── src/main/java/com/votingsystem/
│   ├── AddCandidateServlet.java  
│   └── VoteServlet.java  
│
├── WebContent/
│   ├── index.jsp  
│   ├── about.jsp  
│   ├── logout.jsp  
│   ├── dbTest.jsp  
│
│   ├── Student Module
│   ├── studentRegister.jsp  
│   ├── studentRegisterProcess.jsp  
│   ├── studentLogin.jsp  
│   ├── studentLoginProcess.jsp  
│   ├── studentDashboard.jsp  
│   ├── viewCandidates.jsp  
│   ├── voteProcess.jsp  
│
│   ├── OTP & Password Module
│   ├── sendOtp.jsp  
│   ├── sendOtpRegister.jsp  
│   ├── verifyOtp.jsp  
│   ├── verifyOtpProcess.jsp  
│   ├── verifyOtpRegister.jsp  
│   ├── otp.jsp  
│   ├── setPassword.jsp  
│   ├── setPasswordProcess.jsp  
│   ├── forgotPassword.jsp  
│   ├── sendForgotOtp.jsp  
│   ├── verifyForgotOtp.jsp  
│   ├── verifyForgotOtpProcess.jsp  
│   ├── resetPassword.jsp  
│   ├── resetPasswordProcess.jsp  
│
│   ├── Admin Module
│   ├── adminLogin.jsp  
│   ├── adminLoginProcess.jsp  
│   ├── adminDashboard.jsp  
│   ├── adminLogout.jsp  
│   ├── electionControl.jsp  
│   ├── addCandidate.jsp  
│   ├── removeCandidate.jsp  
│   ├── addStudent.jsp  
│   ├── viewStudents.jsp  
│   ├── removeStudent.jsp  
│   ├── removeClass.jsp  
│   ├── viewResults.jsp  
│   ├── viewPositionResult.jsp  
│
│   ├── WEB-INF/
│   │   ├── web.xml  
│   │   └── lib/  
│   │
│   └── images/
│
├── build/classes/
├── .classpath
├── .project
└── .settings/

---

## 🗄️ Database Setup

SQL schema will be added soon.

Create database manually:

CREATE DATABASE votingdb;
USE votingdb;

Update DB connection in JSP:

Connection conn = DriverManager.getConnection(
"jdbc:mysql://localhost:3306/nextgen_voting_system",
"root",
"your_password"
);

---

## ⚙️ Installation & Setup

### Requirements

- Java JDK 17  
- Apache Tomcat 11  
- MySQL 8+  
- Eclipse IDE (Enterprise Edition)

This project does not use Maven or Gradle.

---

### Steps to Run

1. Clone repository

git clone https://github.com/Omkar030807/NextGen_Voting_System.git

2. Import into Eclipse  
File → Import → Existing Projects → Select folder

3. Add JARs to Build Path  
Right click project → Build Path → Add JARs → WEB-INF/lib

4. Configure Database  
Update DB credentials in JSP files

5. Configure Email OTP  
Update sender email & app password in:
- sendOtp.jsp  
- sendOtpRegister.jsp  
- sendForgotOtp.jsp  

SMTP settings:

props.put("mail.smtp.host", "smtp.gmail.com");
props.put("mail.smtp.port", "587");
props.put("mail.smtp.auth", "true");
props.put("mail.smtp.starttls.enable", "true");

String senderEmail = "your-email@gmail.com";
String senderPassword = "your-app-password";

Use Gmail App Password.

6. Add Tomcat Server in Eclipse  
Preferences → Server → Runtime → Add Tomcat 11

7. Run Project  
Right click project → Run on Server  
Open browser:

http://localhost:8080/NextGen_Voting_System/

---

## 🔄 How It Works

### Student Flow

1. Student registers  
2. OTP sent to email  
3. OTP verification  
4. Login  
5. Dashboard  
6. View candidates & vote  

### Admin Flow

1. Admin login  
2. Dashboard  
3. Manage students/classes  
4. Add/remove candidates  
5. Start/Stop/Reset election  
6. View results  

### Forgot Password Flow

1. Click forgot password  
2. Enter ID/email  
3. Receive OTP  
4. Verify OTP  
5. Set new password  

---

## 📸 Screenshots

Screenshots will be added soon.

- Home Page  
- Student Dashboard  
- Admin Dashboard  
- Candidate List  
- Results Page  

---

## 🤝 Contributing

1. Fork repository  
2. Create branch  
git checkout -b feature/your-feature  

3. Commit  
git commit -m "Added feature"  

4. Push  
git push origin feature/your-feature  

5. Open Pull Request  

---

## 📄 License

MIT License

---

## 👨‍💻 Author

Developed for secure and transparent college elections.

If you like this project, give it a star ⭐
