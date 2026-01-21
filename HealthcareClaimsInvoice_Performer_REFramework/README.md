# 🏥 Healthcare Invoice & Claims Automation (UiPath)

## 📌 Project Summary
This project demonstrates a **real-world healthcare document automation** built using **UiPath REFramework** and **UiPath Orchestrator Queues**.

It automates the intake, classification, extraction, validation, and archival of **healthcare invoices and insurance claim PDFs**, following **enterprise-grade RPA best practices**.

The solution is designed using a **Dispatcher–Performer architecture**, enabling scalability, reliability, and auditability.

---

## 🧠 Business Problem
Healthcare organizations process a large volume of invoice and claim documents manually, which often leads to:
- High processing time  
- Manual data entry errors  
- Limited traceability  
- Inefficient exception handling  

This automation addresses these challenges by **digitizing and standardizing healthcare document processing**.

---

## 🏗️ Solution Architecture
The automation follows a **queue-driven architecture**:

### 🔹 Dispatcher (Intake)
- Scans incoming Invoice and Claim folders  
- Identifies document type (Invoice / Claim)  
- Moves files to a controlled intake location  
- Pushes standardized metadata to **UiPath Orchestrator Queue**

### 🔹 Performer (REFramework)
- Retrieves transactions from Orchestrator queue  
- Reads PDFs using OCR / text extraction  
- Extracts key healthcare fields  
- Applies business validations  
- Writes structured output to Excel  
- Archives documents into Success / Failed folders  

---

## 🔄 End-to-End Workflow
1. PDFs are placed in input folders (Invoices / Claims)  
2. Dispatcher creates queue items with document metadata  
3. REFramework performer processes each transaction  
4. OCR extracts data from scanned or digital PDFs  
5. Business rules validate extracted fields  
6. Output is written to Excel  
7. Documents are archived with processing status  

---

## 📦 Queue Item Structure
Each transaction in Orchestrator contains the following metadata:

| Key | Description |
|-----|------------|
| DocumentPath | Full path of the PDF file |
| DocumentType | Invoice or Claim |
| FileName | Original PDF file name |
| ReceivedOn | Date and time of intake |

This structure ensures **traceability, retry support, and audit readiness**.

---

## 📊 Extracted Data
### Invoice Documents
- Invoice Number  
- Patient Name  
- Date of Service  
- Total Amount  

### Claim Documents
- Claim ID  
- Member ID  
- Provider NPI  
- CPT Code  
- ICD-10 Code  
- Claim Amount  

---

## ⚠️ Exception Handling Strategy
The automation follows an enterprise-grade exception handling approach:

### ✅ BusinessRuleException (No Retry)
- Missing mandatory fields  
- Invalid document format  
- File not found  

### 🔁 System Exception (Retry Enabled)
- OCR engine failures  
- Excel file lock issues  
- Temporary system or network errors  

Retries are managed using **UiPath Orchestrator Queue Retry Policy**.

---

## 📈 Outputs & Audit Trail
- Structured Excel output for reporting and analysis  
- Success / Failed document archival  
- Transaction status updates in Orchestrator  
- Detailed logs for audit and compliance  

---

## 🛠️ Technology Stack
- UiPath Studio  
- UiPath REFramework  
- UiPath Orchestrator  
- OCR (Read PDF with OCR)  
- Regex-based data extraction  
- Excel Automation  

---

## 🎯 Key Highlights
- Dispatcher–Performer architecture  
- Queue-based scalable processing  
- OCR-enabled document handling  
- Business vs System exception handling  
- Healthcare domain automation aligned with enterprise practices  

---

## 👤 Author
**Rangaswamy Reddy Kappeta**  
RPA / Automation Developer (UiPath)

---

## 📸 Architecture Diagram
<img width="2379" height="1380" alt="Architecture_B_Detailed_Interview" src="https://github.com/user-attachments/assets/e46f89a3-320f-449e-be1b-c6a532eacc76" />


