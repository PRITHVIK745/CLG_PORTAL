# College Portal

A simple web-based college portal built with **Flask** and **MongoDB Atlas** where teachers can manage student data, upload marks and notes, and students can log in to view and download their marks and notes.

---

## 🔧 Tech Stack

- **Backend:** Flask (Python)
- **Database:** MongoDB Atlas
- **Templates:** Flask (Jinja2), HTML/CSS
- **Authentication:** Simple username/password based (separate for teachers and students)

---

## ✨ Features

### 👩‍🏫 Teacher Features

- Secure login with **teacher username & password** (pre-created in the database).
- Add students:
  - **Via CSV file upload** (bulk import).
  - **Manually** through a form.
- Enter **marks** for each student for each subject.
- Add **notes** for each subject.
- Edit/update students’:
  - Basic details
  - Marks
  - Notes

### 👨‍🎓 Student Features

- Login using:
  - **Username:** Name given by the teacher
  - **Password:** The **USN** entered by the teacher
- View:
  - All subjects and marks
  - Notes uploaded by the teacher
- Download:
  - **Marksheet** (e.g., as PDF/HTML export)
  - **Notes** for respective subjects

---

## 🗄️ Database (MongoDB Atlas)

The project uses **MongoDB Atlas** as the cloud database.

Typical collections (may vary based on your code):

- `teachers` – stores teacher login credentials and basic info.
- `students` – stores student details (name, USN, branch, year, semester, etc.).
- `marks` – stores marks per student per subject.
- `notes` – stores notes metadata/paths per subject.

Update the connection string in your config or environment variable (e.g. `MONGO_URI`).

---

## 📁 CSV Format for Student Upload

When uploading students via CSV, follow this format (example):

```csv
name,usn,branch,year,semester
John Doe,1RV21CS001,CSE,2,4
Jane Smith,1RV21CS002,CSE,2,4
