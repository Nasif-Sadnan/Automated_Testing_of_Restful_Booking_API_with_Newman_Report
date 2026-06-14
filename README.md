# Restful Booker API Testing with Postman & Newman

This project demonstrates end-to-end API testing of the [Restful Booker API](https://documenter.getpostman.com/view/45217466/2sBXwto8W5) using **Postman** for test design and **Newman** for automated command-line execution and HTML reporting.

## 📌 Overview

The collection covers the full booking lifecycle — create, retrieve, update, and delete — along with authentication, and validates each response against expected status codes and data fields using automated assertions.

## ✨ Features

- Full CRUD coverage: `POST`, `GET`, `PUT`, `DELETE` requests
- Token-based authentication flow
- Pre-request scripts for dynamic test data generation (random names, prices, dates, etc.)
- Response assertions on status codes and field-level data validation
- Environment file for easy switching between configurations
- Automated execution and HTML report generation via Newman

## 🛠️ Tech Stack

- **Postman** – test design and manual exploration
- **Newman** – CLI test runner
- **newman-reporter-htmlextra** – HTML report generation
- **Node.js** – runtime for Newman

## 📂 Test Scenarios

| # | Test Case | Method | Endpoint | Status Code |
|---|-----------|--------|----------|--------------|
| 1 | Create Booking | POST | `/booking` | 200 |
| 2 | Get Booking | GET | `/booking/{id}` | 200 |
| 3 | Generate Auth Token | POST | `/auth` | 200 |
| 4 | Update Booking | PUT | `/booking/{id}` | 200 |
| 5 | Verify Update | GET | `/booking/{id}` | 200 |
| 6 | Delete Booking | DELETE | `/booking/{id}` | 201 |
| 7 | Verify Deletion | GET | `/booking/{id}` | 404 |

### Validations Performed (on Get/Verify requests)
- First Name Validation
- Last Name Validation
- Total Price Validation
- Deposit Paid Validation
- Check-in Date Validation
- Check-out Date Validation

## 🚀 Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) installed
- [Postman](https://www.postman.com/downloads/) (optional, for manual testing)

### Installation

```bash
# Clone the repository
git clone https://github.com/Nasif-Sadnan/Automated_Testing_of_Restful_Booking_API_with_Newman_Report.git
cd Automated_Testing_of_Restful_Booking_API_with_Newman_Report

# Install Newman globally
npm install -g newman

# Install the HTML reporter
npm install -g newman-reporter-htmlextra
```

### Import into Postman (optional)
1. Open Postman → click **Import**
2. Select the collection JSON file from this repo
3. Import the environment JSON file as well (gear icon → Manage Environments → Import)

## ▶️ Running the Tests

**Run via CLI:**
```bash
newman run <collection-file>.postman_collection.json -e <environment-file>.postman_environment.json
```

**Run with HTML report:**
```bash
newman run Nasif_Sadnan_SQA_Restful_Booker_API_Testing.postman_collection.json -e Nasif_Sadnan_SQA_Restful_Booker_API_Testing.postman_environment.json -r cli,htmlextra
```

The generated report will be saved in the `newman/` folder.

## 📊 Test Results Summary

| Metric | Total | Failed |
|--------|-------|--------|
| Requests | 7 | 0 |
| Pre-request Scripts | 4 | 0 |
| Test Scripts | 6 | 0 |
| Assertions | 13 | 0 |

- **Total run duration:** ~3.8s
- **Average response time:** ~461ms
- **Total failures:** 0 ✅

All 13 assertions passed across the full booking lifecycle (create → read → update → delete → verify).

## 📁 Project Structure

```
├── *.postman_collection.json    # Postman collection with all test requests
├── *.postman_environment.json   # Environment variables
├── newman/                       # Generated HTML test reports
└── README.md
```
## 📊 Newman Report Summary:
<img width="467" height="682" alt="image" src="https://github.com/user-attachments/assets/52f85af9-241f-4bc1-a035-1bb98d64972b" /> </br>
<img width="457" height="322" alt="image" src="https://github.com/user-attachments/assets/27cbf299-9126-4770-957f-9f05ad8ffa0c" /> </br>
<img width="470" height="137" alt="image" src="https://github.com/user-attachments/assets/f272cdf3-1ee0-4ef4-b6ce-515e9372957a" /> </br>
<img width="467" height="137" alt="image" src="https://github.com/user-attachments/assets/d5ba67ca-30c5-463d-bb24-f4d74a251a96" /> </br>






## 👤 Author

**MD. Nasif Sadnan Chowdhury**
Software Quality Assurance | Full Stack SQA

## 📄 License

This project is open source and available for educational and testing purposes.
