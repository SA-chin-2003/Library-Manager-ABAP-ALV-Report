# 📚 SAP ABAP Library Manager

![SAP ABAP](https://img.shields.io/badge/SAP-ABAP-008FD3?style=for-the-badge&logo=sap&logoColor=white)
![Report Type](https://img.shields.io/badge/Report-ALV_Grid-success?style=for-the-badge)

A custom Library Management System developed in SAP ABAP using 
ALV Grid Display, Screen Painter, and custom GUI Status.

---

## 🚀 Features

- View all books in an interactive ALV Grid
- Add new books via custom input screen
- Delete existing records with confirmation popup
- Double-click a row to view book details
- Custom Toolbar with Add, Delete, Back, Exit buttons
- Direct Transaction Code (ZLIB) for quick access

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| SAP ABAP | Programming Language |
| SE38 | ABAP Editor |
| SE51 | Screen Painter (Custom UI) |
| SE41 | GUI Status & Toolbar |
| SE93 | Transaction Code Creation |
| SE11 | Database Table (ZLIBRARY_BOOKS) |
| REUSE_ALV_GRID_DISPLAY | ALV Grid Function Module |

---

## 📁 Project Structure
SAP-ABAP-Library-Manager/
│
├── src/
│   └── ZRP_LIBRARY_MANAGER.abap       # Main Report Program
│
├── docs/
│   ├── screenshots/                    # UI Screenshots
│   └── setup-guide.md                  # Step by step setup
│
└── README.md

---

## ⚙️ Setup Instructions

### 1. Create Database Table
- Go to **SE11**
- Create table `ZLIBRARY_BOOKS` with fields:
  
| Field | Type | Key |
|-------|------|-----|
| BOOK_ID | NUMC | ✅ Primary Key |
| TITLE | CHAR | |
| AUTHOR | CHAR | |
| GENRE | CHAR | |
| PRICE | CURR | |

### 2. Create the Report
- Go to **SE38**
- Create program `ZRP_LIBRARY_MANAGER`
- Copy code from `src/ZRP_LIBRARY_MANAGER.abap`
- Activate (Ctrl+F3)

### 3. Create GUI Status in SE41
- Program: `ZRP_LIBRARY_MANAGER`
- Status Name: `STATUS_100`
- Add buttons: `ADD_BOOK`, `DELETE`, `BACK`, `EXIT`
- Activate

### 4. Create Screen 100 in SE51
- Program: `ZRP_LIBRARY_MANAGER`
- Screen: `100`
- Add input fields from `ZLIBRARY_BOOKS`
- Add Flow Logic:
```abap
PROCESS BEFORE OUTPUT.
  MODULE STATUS_0100.
PROCESS AFTER INPUT.
  MODULE USER_COMMAND_0100.
```
- Activate

### 5. Create Transaction Code
- Go to **SE93**
- T-Code: `ZLIB`
- Type: Report Transaction
- Program: `ZRP_LIBRARY_MANAGER`
- Activate

### 6. Run
- Type `ZLIB` in SAP command bar
- Press Enter 🚀

---

## 📸 Screenshots

| Screen | Description |
|--------|-------------|
| ALV Grid | Main book list view |
| Screen 100 | Add new book input form |
| Delete Popup | Confirmation before delete |

---

## 📌 Transaction Codes Used

| T-Code | Purpose |
|--------|---------|
| SE38 | ABAP Editor |
| SE11 | Data Dictionary |
| SE51 | Screen Painter |
| SE41 | Menu Painter |
| SE93 | Transaction Maintenance |
| SM30 | Table Maintenance |
| ZLIB | Run Library Manager |

---

## 👨‍💻 Developer
**Sachidananda Mohanty**

Connect with me on [LinkedIn](https://linkedin.com/in/sachidananda-mohanty-2217as)  
Check out more projects on [GitHub](https://github.com/SA-chin-2003)

## Contributions are welcome!
don't forget to give the credits

## 📃 License

This project is open source and available under the [MIT License](LICENSE).

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
