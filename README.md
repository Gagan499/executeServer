# 🚀 Code Execution Server (Sandboxed Runner)

A secure and scalable **code execution server** that runs user-submitted code in isolated environments using Docker. Designed for use in online compilers, coding platforms, and educational tools.

---

## ✨ Features

* 🔒 **Secure Execution** using Docker containers
* ⚡ Supports multiple languages (e.g., Python, JavaScript, C++, Java)
* 🧠 Resource limits (CPU, memory, process limits)
* 🌐 REST API for easy integration
* 🧹 Automatic cleanup of containers
* 🚫 Network isolation for security

---

## 🛠️ Tech Stack

* **Backend:** Node.js, Express.js
* **Containerization:** Docker
* **Execution Engine:** Custom runner scripts
* **Optional DB:** MongoDB / MySQL (for logs or history)

---

## 📂 Project Structure

```
.
├── backend/
│   ├── app.js
│   ├── routes/
│   ├── controllers/
│   └── utils/
├── temp/              # Temporary code files
├── Dockerfile
├── package.json
└── README.md
```

---

## ⚙️ How It Works

1. User sends code via API
2. Server creates a temporary file
3. Docker container runs the code
4. Output is captured and returned
5. Container is destroyed after execution

---

## 🚀 Getting Started

### 1. Clone the repository

```
git clone https://github.com/your-username/code-execution-server.git
cd code-execution-server
```

### 2. Install dependencies

```
npm install
```

### 3. Run the server

```
npm start
```

---

## 🐳 Docker Execution Example

```
docker run --rm \
  --memory="100m" \
  --cpus="0.5" \
  --pids-limit=50 \
  --network=none \
  --security-opt no-new-privileges \
  -v "$PWD/temp:/app" \
  runner-image
```

---

## 🔐 Security Measures

* No network access inside containers
* Limited memory & CPU usage
* No privilege escalation
* Temporary file cleanup

---

## 📡 API Example

### POST `/run`

**Request:**

```json
{
  "language": "python",
  "code": "print('Hello World')"
}
```

**Response:**

```json
{
  "output": "Hello World"
}
```

---

## 📌 Use Cases

* Online code editors
* Coding interview platforms
* Learning platforms
* Competitive programming tools

---

## 🧑‍💻 Future Improvements

* Add more languages
* Queue system (Redis / BullMQ)
* Rate limiting
* Execution logs dashboard

---

## 📄 License

MIT License

---

## 🤝 Contributing

Pull requests are welcome! Feel free to open issues for suggestions or improvements.
