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


# 🚀 Getting Started
1️⃣ Clone the Repository
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>

2️⃣ Create & Activate Virtual Environment (Recommended)
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate

3️⃣ Install Dependencies

You mentioned you already have a requirements.txt file. Install all packages with:

pip install -r requirements.txt

4️⃣ Configure Environment Variables

Create a .env file (or export variables manually) with something like:

MONGO_URI="your_mongodb_atlas_connection_string"
SECRET_KEY="your_secret_key"
FLASK_ENV=development


If your app reads different variable names, edit them here accordingly.

5️⃣ Run the Application

Depending on how your app is structured:

Option A: Using flask run

# On Windows (PowerShell / CMD)
set FLASK_APP=app.py

# On macOS / Linux
export FLASK_APP=app.py

flask run


Option B: Using python directly

python app.py


Server will usually run at:

http://127.0.0.1:5000

🔐 Login Details

These are just the rules; actual usernames/passwords depend on your database entries.

Teacher

Username: eteacher (or whatever you set in DB)

Password: Set in the database (manually or via a seed script)

Student

Username: The name the teacher entered when creating the student.

Password: The USN the teacher entered for that student.

Make sure this convention is clearly communicated to teachers and students.

🧭 Basic Flow

Teacher logs in

Uses eteacher username & password.

Teacher adds students

Either upload a CSV file or add manually via form.

Teacher adds marks & notes

For each student and subject.

Student logs in

Username = name given by teacher.

Password = USN.

Student dashboard

View marks per subject.

Download marksheet.

Download notes per subject.

## 📁 CSV Format for Student Upload

When uploading students via CSV, follow this format (example):

```csv
name,usn,branch,year,semester
John Doe,1RV21CS001,CSE,2,4
Jane Smith,1RV21CS002,CSE,2,4
