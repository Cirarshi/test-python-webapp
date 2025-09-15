# 🐍 My Python WebApp (Flask)

A simple Python web application built with [Flask](https://flask.palletsprojects.com/).  
This project is for learning **CI/CD pipelines with GitHub and Jenkins**.

---

## 🚀 Features
- Basic Flask server with a single route (`/`)
- Simple HTML template (`index.html`)
- Easy to run locally
- Ready for GitHub + Jenkins integration

---

## 📂 Project Structure
```bash
my-python-webapp/
│── app.py # Main Flask application
│── requirements.txt # Python dependencies
│── templates/
│ └── index.html # Homepage template
│── README.md # Project documentation
│── Jenkinsfile # Jenkins pipeline (CI/CD)
```

---

## ⚡ Getting Started

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/YOUR_USERNAME/my-python-webapp.git
cd my-python-webapp
```

### 2️⃣ Install Dependencies
Make sure you have Python 3.9+ installed, then run:
```bash
pip install -r requirements.txt
```
### 3️⃣ Run the Application
```bash
python app.py
```

The app will be available at:
  - http://127.0.0.1:5000
  - http://localhost:5000

---

## 🧪 Running Tests
(Example test file can be added in tests/)
```bash
python -m unittest discover -s tests
```

---

## 🛠️ Jenkins Integration
This repo includes a Jenkinsfile with these stages:
  - Checkout – Pull code from GitHub
  - Install Dependencies – Install Flask and other requirements
  - Run Tests – Execute Python unit tests
  - Run App – Start the Flask app
Set up a Jenkins pipeline pointing to this repo, and it will build + test automatically on each push.

---

## 📦 Deployment
⚠️ Flask’s built-in server is only for development.
For production, use a WSGI server like Gunicorn or uWSGI, possibly inside Docker.

---

## 🤝 Contributing
Feel free to fork this repo and submit pull requests.
Suggestions and improvements are always welcome!

---

