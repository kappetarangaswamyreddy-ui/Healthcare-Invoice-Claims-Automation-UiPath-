# 🏥 Healthcare Invoice & Claims Automation using UiPath

## 🔍 What is this project?
This project is a **real-world healthcare document automation** built using **UiPath REFramework** and **UiPath Orchestrator Queues**.

It automates the processing of **healthcare invoices and insurance claims (PDFs)** by:
- reading documents automatically,
- extracting important billing and claim information,
- validating business rules,
- and generating structured output for reporting and audit.

The solution is designed the same way **enterprise RPA solutions are implemented in production environments**.

---

## 🎯 Why this project was built
In healthcare organizations, invoices and claim documents are often processed manually, which causes:
- delays in processing,
- data entry errors,
- lack of traceability,
- poor exception handling.

This automation reduces manual effort and improves **accuracy, reliability, and auditability** using UiPath best practices.

---

## ⚙️ How the project works (High-Level)
The automation follows a **Dispatcher–Performer architecture**:

### 1️⃣ Dispatcher (Intake)
- Scans incoming folders for **Invoice** and **Claim** PDF documents
- Identifies the document type
- Moves files to a controlled intake folder
- Creates a queue transaction in **UiPath Orchestrator** with document metadata

### 2️⃣ Orchestrator Queue
- Each document becomes **one queue item**
- Stores document details like file path and document type
- Handles retries for system failures

### 3️⃣ Performer (REFramework)
- Fetches queue items using REFramework
- Reads PDF content using **OCR**
- Extracts key healthcare fields
- Validates mandatory data
- Writes structured output to Excel
- Archives documents into **Success** or **Failed** folders

---

## 🧩 Key Features
- Dispatcher–Performer design pattern  
- Queue-driven processing for scalability  
- OCR support for scanned and digital PDFs  
- Business vs System exception handling  
- Structured output with audit trail  
- Production-ready REFramework implementation  

---

## 🛠️ Technologies Used
- UiPath Studio  
- UiPath REFramework  
- UiPath Orchestrator  
- OCR (Read PDF with OCR)  
- Regex-based data extraction  
- Excel Automation  

---

## 📌 Who this project is for
This project is relevant for:
- Healthcare RPA use cases  
- Invoice and claims automation  
- Enterprise document processing  
- UiPath REFramework learning and interviews  

---

