Got it! Here's a **complete and self-contained `README.md`** that includes all code snippets, clear explanations, and setup steps so that you can **easily refer to or explain** it to someone else.

---

```markdown
# 💉 Vaccination Portal - React Frontend

This is a simple **React.js frontend** for a vaccination portal. It connects to a **Spring Boot backend** using REST APIs to perform full **CRUD operations** (Create, Read, Update, Delete) for **students** and **vaccination drives**.

---

## ✅ Prerequisites

Install the following tools before starting:

1. **Node.js (LTS)** – https://nodejs.org/  
2. **npm** – Comes with Node.js  
3. **VS Code** – For editing code  
4. **Spring Boot backend** – Must be running on `http://localhost:8080`

---

## 🚀 React Project Setup

### 📁 Step 1: Create React App

```bash
npx create-react-app vaccination-frontend
cd vaccination-frontend
```

---

### 📦 Step 2: Install Axios

```bash
npm install axios
```

---

## 🧠 Project Structure

```
vaccination-frontend/
│
├── src/
│   ├── components/
│   │   ├── StudentList.js
│   │   ├── StudentForm.js
│   │   └── DriveList.js
│   ├── api.js
│   └── App.js
```

---

## 🔌 API Integration - `api.js`

Create a new file `src/api.js` and add the following code:

```js
import axios from 'axios';

const BASE_URL = 'http://localhost:8080/api';

export const getAllStudents = () => axios.get(`${BASE_URL}/students`);
export const addStudent = (student) => axios.post(`${BASE_URL}/students`, student);
export const updateStudent = (id, student) => axios.put(`${BASE_URL}/students/${id}`, student);
export const deleteStudent = (id) => axios.delete(`${BASE_URL}/students/${id}`);

export const getAllDrives = () => axios.get(`${BASE_URL}/drives`);
export const addDrive = (drive) => axios.post(`${BASE_URL}/drives`, drive);
```

---

## 🧑‍🎓 Student List Component - `StudentList.js`

Create `src/components/StudentList.js`:

```js
import React, { useEffect, useState } from 'react';
import { getAllStudents, deleteStudent } from '../api';

const StudentList = () => {
    const [students, setStudents] = useState([]);

    useEffect(() => {
        loadStudents();
    }, []);

    const loadStudents = async () => {
        const response = await getAllStudents();
        setStudents(response.data);
    };

    const handleDelete = async (id) => {
        await deleteStudent(id);
        loadStudents();
    };

    return (
        <div>
            <h2>Student List</h2>
            <ul>
                {students.map((s) => (
                    <li key={s.id}>
                        {s.name} ({s.studentClass}) - Vaccinated: {s.isVaccinated ? 'Yes' : 'No'}
                        <button onClick={() => handleDelete(s.id)}>Delete</button>
                    </li>
                ))}
            </ul>
        </div>
    );
};

export default StudentList;
```

---

## ➕ Add Student Form - `StudentForm.js`

Create `src/components/StudentForm.js`:

```js
import React, { useState } from 'react';
import { addStudent } from '../api';

const StudentForm = () => {
    const [formData, setFormData] = useState({
        name: '',
        studentClass: '',
        isVaccinated: false,
    });

    const handleChange = (e) => {
        const { name, value, type, checked } = e.target;
        setFormData({
            ...formData,
            [name]: type === 'checkbox' ? checked : value,
        });
    };

    const handleSubmit = async (e) => {
        e.preventDefault();
        await addStudent(formData);
        alert('Student added successfully!');
        setFormData({ name: '', studentClass: '', isVaccinated: false });
    };

    return (
        <form onSubmit={handleSubmit}>
            <h2>Add Student</h2>
            <input
                type="text"
                name="name"
                value={formData.name}
                placeholder="Name"
                onChange={handleChange}
                required
            /><br />
            <input
                type="text"
                name="studentClass"
                value={formData.studentClass}
                placeholder="Class"
                onChange={handleChange}
                required
            /><br />
            <label>
                <input
                    type="checkbox"
                    name="isVaccinated"
                    checked={formData.isVaccinated}
                    onChange={handleChange}
                />
                Vaccinated
            </label><br />
            <button type="submit">Add Student</button>
        </form>
    );
};

export default StudentForm;
```

---

## 💉 Vaccination Drive List - `DriveList.js`

Create `src/components/DriveList.js`:

```js
import React, { useEffect, useState } from 'react';
import { getAllDrives } from '../api';

const DriveList = () => {
    const [drives, setDrives] = useState([]);

    useEffect(() => {
        const fetchDrives = async () => {
            const response = await getAllDrives();
            setDrives(response.data);
        };
        fetchDrives();
    }, []);

    return (
        <div>
            <h2>Vaccination Drives</h2>
            <ul>
                {drives.map((drive) => (
                    <li key={drive.id}>
                        {drive.location} - {drive.date}
                    </li>
                ))}
            </ul>
        </div>
    );
};

export default DriveList;
```

---

## ⚙️ App Component - `App.js`

Update `src/App.js`:

```js
import React from 'react';
import StudentList from './components/StudentList';
import StudentForm from './components/StudentForm';
import DriveList from './components/DriveList';

function App() {
    return (
        <div className="App">
            <h1>Vaccination Portal</h1>
            <StudentForm />
            <StudentList />
            <DriveList />
        </div>
    );
}

export default App;
```

---

## ▶️ Run the React App

Start the frontend:

```bash
npm start
```

Make sure the backend is running at:

```
http://localhost:8080
```

---

## 🎉 Result

You will see:

- A form to add a new student
- A list of existing students with vaccination status
- A list of all vaccination drives
- Delete button to remove students

---

## 🧑‍💻 Author

Made with 💙 by Siddarood
Open to improvements and contributions!

---

## 📜 License

MIT License
```

---

Let me know if you want this packed into a `.zip` or uploaded to GitHub — I can help with that too!
