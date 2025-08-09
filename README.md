# 🏫 School Management API

A simple Node.js + Express.js REST API for managing schools, with MySQL database support.  
The API allows you to **add new schools** and **list schools by proximity** to a given location.  
Designed to be beginner-friendly but structured for growth.

---

## 📌 Features

- Add schools with name, address, latitude, and longitude
- List schools sorted by nearest to a given location
- MySQL database integration
- Dockerized setup for quick local development
- ES Modules for cleaner code structure

---

## 🛠️ Tech Stack

- **Node.js** (Express.js)
- **MySQL** (as database)
- **Docker & Docker Compose**
- **JavaScript (ES Modules)**

---

## 📂 Project Structure

```
project/
├── src/
│   ├── config/        # DB connection setup
│   ├── controllers/   # Request handlers
│   ├── routes/        # API routes
│   ├── utils/         # Helper functions
│   └── index.js       # App entry point
├── docker-compose.yml
├── Dockerfile
├── package.json
└── README.md
```

---

## ⚙️ Installation & Setup

### **1. Clone the repository**
```bash
git clone https://github.com/<your-username>/school-management-api.git
cd school-management-api
```

### **2. Environment Variables**
Create a `.env` file in the project root:
```env
DB_HOST=mysql
DB_USER=root
DB_PASSWORD=yourpassword
DB_NAME=school_db
DB_PORT=3306
PORT=3000
```

### **3. Run with Docker**
```bash
docker-compose up --build
```

The API will be available at:
```
http://localhost:3000
```

---

## 📌 API Endpoints

### **1. Add School**
**POST** `/addSchool`  
**Request Body:**
```json
{
  "name": "Delhi Public School, R.K. Puram",
  "address": "Sector XII, R.K. Puram, New Delhi, Delhi 110022",
  "latitude": 28.5665,
  "longitude": 77.1968
}
```
**Response:**
```json
{
  "message": "School added successfully"
}
```

---

### **2. List Schools by Proximity**
**GET** `/listSchools?latitude=28.6139&longitude=77.2090`  
**Response Example:**
```json
[
  {
    "id": 1,
    "name": "St. Columba's School",
    "address": "1, Ashok Place, New Delhi, Delhi 110001",
    "latitude": 28.6312,
    "longitude": 77.2102,
    "distance_km": 1.9
  }
]
```

---

## 🧪 Testing with Postman

- Import the included **Postman Collection** (`School Management API.postman_collection.json`)  
- Example requests for both endpoints are included
- You can easily switch between **local** and **hosted** environments in Postman

---

## 🚀 Deployment

You can deploy using:
- **Railway.app** (recommended for Docker + MySQL)
- **Render.com** (Node.js only, MySQL hosted separately)
- **Heroku** (requires external MySQL service)

---

## 📜 License
This project is licensed under the MIT License.

---

## 👨‍💻 Author
**Your Name**  
[GitHub](https://github.com/<your-username>)
