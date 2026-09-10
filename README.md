# 🏥 Healthcare RPA Risk Analyzer System

An intelligent healthcare appointment management system that combines **ASP.NET Core Web API**, **UiPath RPA**, and **Python AI Risk Analysis** to automatically analyze patient appointments and classify medical priority levels.

The system helps healthcare providers identify emergency cases faster by analyzing patient information and updating appointment risk status automatically.

---

# 📌 Project Overview

Healthcare facilities receive many appointments daily, and some cases require immediate attention.

This project introduces an automated workflow where:

1. Patients book appointments through the system.
2. The RPA Bot collects pending appointments.
3. Python analyzes patient risk based on medical information.
4. The system classifies cases:
   - 🟢 Low Priority
   - 🟡 High Priority
   - 🔴 Emergency
5. Results are automatically sent back to the API and stored in the database.

---

# 🏗 System Architecture

```
                Patient
                   |
                   ↓
        ASP.NET Core Web API
                   |
                   ↓
             SQL Server DB
                   |
                   ↓
              UiPath RPA Bot
                   |
                   ↓
          Python Risk Analyzer
                   |
                   ↓
             Risk Evaluation
                   |
                   ↓
        Update Appointment API
                   |
                   ↓
             Database Updated
```

---

# 🚀 Technologies Used

## Backend Development

- ASP.NET Core Web API
- Entity Framework Core
- SQL Server
- ASP.NET Identity
- JWT Authentication
- REST API

## Automation

- UiPath RPA

## AI Risk Analysis

- Python
- JSON Processing

## Development Tools

- Visual Studio
- Visual Studio Code
- Postman
- Git & GitHub

---

# ✨ Main Features

## 👤 Patient Management

- User registration and authentication
- Patient profile management
- Appointment booking
- View patient appointments

---

## 📅 Appointment Management

- Create available appointments
- Book appointments
- Manage appointment availability
- Admin appointment management

---

## 🤖 RPA Automation Bot

The UiPath Bot automates the complete workflow:

- Retrieves pending appointments from the API
- Generates appointment data file
- Sends data to Python analyzer
- Reads risk analysis results
- Updates appointment records automatically

---

# 🧠 Python Risk Analyzer

The Python module analyzes patient information and calculates a risk score.

## Input Data:

- Patient age
- Visit reason
- Medical symptoms

## Risk Rules Example:

```
Age >= 60              → +3 Risk Score

Chest Pain             → +5 Risk Score

Shortness of Breath    → +5 Risk Score

Bleeding               → +5 Risk Score

Stroke Symptoms        → +5 Risk Score
```

---

# 🚦 Priority Classification

```
Risk Score >= 8

        ↓

    Emergency 🚨


Risk Score >= 4

        ↓

       High ⚠️


Risk Score < 4

        ↓

       Low ✅
```

---

# 🔄 Automation Workflow

```
GET Pending Appointments API

            ↓

        UiPath Bot

            ↓

     appointments.json

            ↓

    Python Risk Analyzer

            ↓

       result.json

            ↓

      UiPath Processing

            ↓

 PUT /api/Appointments/{id}/risk

            ↓

     SQL Server Database
```

---

# 📂 Project Structure

```
Healthcare-RPA-System

│
├── API
│
│   ├── MyApi.DAL
│   │      └── Database Models
│   │
│   ├── MyApi.BLL
│   │      └── Business Logic
│   │
│   └── MyApi.PLL
│          └── Controllers & API Endpoints
│
│
├── Healthcare-RPA-Python
│
│   ├── risk_analyzer.py
│   ├── appointments.json
│   └── result.json
│
│
└── UiPath
       └── HealthcareBot.xaml
```

---

# 🔌 API Endpoints

## Get Available Appointments

```
GET /api/Appointments/available
```

---

## Book Appointment

```
POST /api/Appointments/book
```

---

## Get Pending Appointments For RPA

```
GET /api/Appointments/pending
```

---

## Update Risk Result

```
PUT /api/Appointments/{id}/risk
```

Example Request:

```json
{
  "priority": "Emergency",
  "isEmergency": true,
  "riskScore": 10
}
```

Response:

```json
{
  "message": "Risk updated successfully",
  "appointmentId": 17
}
```

---

# 🧪 Example

## Input

```json
{
  "age": 71,
  "reason": "ألم صدر وضيق تنفس"
}
```

## Output

```json
{
  "priority": "Emergency",
  "isEmergency": true,
  "riskScore": 13
}
```

---

# ⚙️ Installation & Running

## 1. Run Backend API

Navigate to:

```
API/MyApi.PLL
```

Run:

```bash
dotnet run
```

API will start:

```
http://localhost:5120
```

---

## 2. Run Python Analyzer

Navigate to:

```
Healthcare-RPA-Python
```

Run:

```bash
python risk_analyzer.py
```

Output:

```
Result file created successfully
```

---

## 3. Run UiPath Bot

Open:

```
HealthcareBot.xaml
```

Run the workflow.

The bot will automatically:

- Collect appointments
- Analyze risk
- Update database records

---

# 🔐 Security

The system supports:

- JWT Authentication
- Role-based authorization
- Admin permissions
- Protected API endpoints

---

# 📈 Future Improvements

Future enhancements:

- Machine Learning based risk prediction
- Doctor notification system
- Emergency alerts
- Healthcare dashboard
- Patient medical history analysis
- Advanced triage algorithms

---

# 👨‍💻 Author

Healthcare Automation Project

Combining:

**Backend Development + RPA Automation + AI Risk Analysis**
